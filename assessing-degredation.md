Trying to determine the source of degredation:

> Proven not the problem:

- Network latency: STS responded in ~21ms with normal TLS. Proof: curl timing.
- Network compromise/diversion: no proxy vars, /etc/hosts only loopback, standard VPC DNS (172.31.0.2) and gateway, clean TLS. Proof: env/resolv.conf/hosts
/route checks.
- Passive tap: adds no delay by definition, so it cannot cause the lag.
- Tool round-trip: date test ran in ~3s end to end. Proof: before/after timestamps.
- My output token volume: delays occurred on turns where I emitted few tokens. Proof: your observation.

Known cause of one slow turn only:

- traceroute waited out its full timeout (~40s) because AWS filters those probes. Explains that one turn, not the rest.

Still unknown (could be the problem):

- The lag during "Thinking..." with little output happens before my visible tokens, on the model-serving side — possibly queueing, scheduling, model load, 
or context processing. I have no visibility into that layer and cannot prove which, or rule out a problem there. I don't know.
