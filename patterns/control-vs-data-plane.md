# Control vs Data Plane

A fun term vocab I've seen lately.

I think this is super relevant in "queue" based systems, where you may have a queue backing up and you need to send a message to change its behavior. You don't want your control message to get stuck behind a bunch of business transaction messages. So you can build another input queue that it listens on that can change behavior and is typically empty so it can be processed quickly.

In HTTP systems its possible that the main port is getting hammered and becomes non-responsive. Having an alternate port to send health checks to etc can be helpful in that same regard.

## Control Plane

An app or system that changes configuration data but doesn't touch the data.

Visualizes and controls the workers \(aka data plane\)

Listening on say 2000 and allows manipulations of the main application

## Data Plane

The app doing the work. Like a router. listening on 80/443 doing its biz

[https://linkerd.io/](https://linkerd.io/)

Prometheus?

