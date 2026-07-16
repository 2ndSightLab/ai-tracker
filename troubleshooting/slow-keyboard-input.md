# Troubleshooting slow keyboard input

Tonight my keyboard input ws so slow. Everything was lagging. My first thought as a security nerd is...key logger?

Don't ask me to tell you if this is all accurate but I hope someone at Apple or Google will see this and look into it.

It's easy when things are slow to blame the model or the cloud or whatever you want to point your finger at.

The other day I discovered that there was a rogue orphan process on my EC2 instance causing the lag.

Since then I have experienced slowness I could not quite pinpoint. By asking the agent over and over I was able to narrow it down to something on my local Laptop.

With the help of Google AI, which has been wrong a lot lately when I get Google and Anthropic models to argue with each other so take this with a grain of salt...

It pinpointed this log entry as the problem.

2026-07-15 19:28:19.231154-0400 0x90c      Default     0x0                  171    0    WindowServer: (SkyLight) [com.apple.SkyLight.processes:Focus] a3ee7[DoDeferredOrdering]: [DeferringManager] Deferring events from frontmost process PSN 0x0-0x28028 (Google Chrome) -> <pid: 948>
    [171-BC]; <keyboardFocus; Google Chrome:0x0-0x28028>; () -> <pid: 948>; reason: frontmost PSN --> outbound target,
    [171-BC]; <keyboardFocus; Google Chrome:0x0-0x28028>; () -> <pid: 948>; reason: frontmost PSN --> outbound target,
    <pid: 948>,
    <token: viewbridge-key-window; pid: 948>
2026-07-15 19:28:19.260042-0400 0x1036b    Default     0x0                  784    0    CursorUIViewService: (libxpc.dylib) [com.apple.xpc:connection] [0x71ccdd080] activating connection: mach=false listener=false peer=true name=com.apple.TextInputUI.xpc.CursorUIViewService.peer[948].0x71ccdd080
2026-07-15 19:28:19.263102-0400 0x10257    Default     0x0                  716    0    ViewBridgeAuxiliary: (libxpc.dylib) [com.apple.xpc:connection] [0x8110a9680] activating connection: mach=false listener=false peer=true name=com.apple.xpc.anonymous.0x810c80640.peer[948].0x8110a9680
2026-07-15 19:28:19.268232-0400 0x1036b    Default     0x0                  784    0    CursorUIViewService: (libxpc.dylib) [com.apple.xpc:connection] [0x71ccdd080] activating connection: mach=false listener=false peer=true name=com.apple.xpc.anonymous.0x71cc64780.peer[948].0x71ccdd080
2026-07-15 19:28:19.291947-0400 0x1034c    Default     0x0                  171    0    WindowServer: (BackBoardHIDEventFoundation) [com.apple.BackBoard:EventDelivery] new deferring rules for pid:948: [[948-63]; <keyboardFocus>; () -> <token: viewbridge-key-window; pid: 948>; reason: …RemoteView deferKeyboardEventsToParticularWindow:forReason:]]
2026-07-15 19:28:19.291962-0400 0x1034c    Default     0x0                  171    0    WindowServer: (BackBoardHIDEventFoundation) [com.apple.BackBoard:EventDelivery] [keyboardFocus 0xaab47ec60] setRules:forPID(948): [[948-63]; <keyboardFocus>; () -> <token: viewbridge-key-window; pid: 948>; reason: -[NSRemoteView deferKeyboardEventsToParticularWindow:forReason:]]

It gave me a repoort and description but it keeps changing the output. Temperature in Google aimode must be far from zero.

So anyway, it gave me a report but it keeps saying it's normal. But it's not. I refer you to how I got into cybersecurity on my blog. I don't buy it. But I'll let some Mac or Google Engineer figure it out. 

Here's the thing that doesn't make sense. It's telling me this is a race condition between Google Chrome and Mac OS and is no way a Key Logger. But it has to do with a queue if I understand correctly where keystrokes are captured. At one point I got this diagram. Is this right?

[Your Keyboard] 
       │
       ▼
[BackBoardHIDEventFoundation] (The OS Gatekeeper)
       │
 ┌─────┴────────────────────────────────────────┐
 │ Is there a "viewbridge-key-window" token?    │
 └─────┬────────────────────────────────────────┘
       │
       ├─► YES (Stalled): Hold all keystrokes in a queue. <─── (YOU ARE HERE)
       │
       └─► NO (Normal): Pass keystrokes immediately to Terminal.


That queue is interesting. Google aimode is telling me it's super secure. Don't worry about it. If someone could get at that they would already have complete access to your system. 

Well that's comforting.

But the thing is, it keeps telling me it's a Google event. Someting to do with a text box or similar in Google Chrome. It's pushing my keystrokes to some window.

Summary: The log is simply stating: "The operating system is securely pushing the keystrokes outbound from the hardware layer, targeting Google Chrome's text box."

The other weird thing is that I was asking Google aimode for commands to figure out what it was and I told it twice not to kill it. And I didn't notice it hid a kill in a log command so it killed it before I could figure out exactly what the pid was and take a look.

So let's just say theoretically that someone wanted to get at my keystrokes in a terminal? Why? Beause that's where I type my MFA codes. So that's why I'm a little wary of this whole thing.

Maybe it is "just a race condition" but race conditions have caused a whole lot of problems over the years. 

Here's another snippet:

WindowServer Focus Shift: The log starts with WindowServer (the macOS display engine) noting that Google Chrome is the frontmost application. 
It prepares to "defer" (route) keyboard events from the main app container to a specific sub-component or process 
(pid: 948).

Cursor and Text Input Services: The lines mentioning CursorUIViewService and com.apple.TextInputUI show
macOS activating background connections to manage text input features. This often handles things like the typing cursor animation, autocorrect popups, inline spellcheck, or smart inline text suggestions.

ViewBridge Connections: ViewBridgeAuxiliary handles communication between different process windows. 
It ensures that even if a UI element runs in a separate background helper process, your keystrokes land exactly where your cursor is flashing.

Event Delivery Rules: The final lines show BackBoardHIDEventFoundation establishing the precise rules for this interaction. It explicitly states it is routing keyboard focus to a remote view window (NSRemoteView).
