Does the world need another eventing platform and the answer is no.  However that reality should not stop us from playing, exploring and learning through rolling our own.

`aevents` is a small, cheap yet robust platform built entirely on Azure using native services.  The idea behind `aevents` is that we often need a stream of events within an application boundary and deloying one of the "big" solutions is complex and expensive.

Characteristics:

- The events are persisted and can be replayed
- Listeners of events are considered transient and, when connecting, must declare what their last consumed event was
- If a listener is unavailable or errors it will be forgotten and not communicated to `aevents` againt; the listener will need to re-register itself as a listener
- `aevents` will periodically send a heartbeat to a listener to confirm that the listener is active and responsive.  Should the listener not respond then that listener will be considered unavailable
