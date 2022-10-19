# clusterable

Clustering library that can be retrofitted into an application for easy clustering functionality.

## What it is

Clusterable is a library that is designed as a plugin for applications
that wish to have simple clustering functionality in a distributed
environment.

It is designed to be language independent, allowing for messages to
be passed between applications written in either the same or
differing languages.

As long as the messages sent between clusters is in a standard format,
the language should not matter.  Recommended payloads are JSON, but
they can be binary data format.

## Languages supported

- [ ] TypeScript/Node
- [ ] C
- [ ] C++
- [ ] Rust
- [ ] Go
- [ ] Python3

## Cluster events

`onClusterJoin`
- Contains the ID (UUID) of the cluster member
- Contains the IP address of the cluster member
- Contains a desired cluster election (leader/member)
- Broadcast to all members

`onClusterLeave`
- Contains the ID (UUID) of the cluster member
- Contains the IP address of the cluster member
- Broadcast to all members

`onClusterMessage`
- Contains the ID (UUID) of the cluster member
- Contains the IP address of the cluster member
- Message data

`onClusterPromotion`
- Contains the ID (UUID) of the cluster member that was promoted
- Contains the IP address of the cluster member that was promoted

### Data Specifics

Data payload format is sent as an HTTP Post message, as a REST
service call.  Data is sent in the post body as:

```
[length][encrypted payload][data CRC]
```

Data is checked and decrypted.  If the data payload does not match
the CRC, or the length of the request is too large, the payload
message is ignored, and an appropriate "Bad Request" HTTP code is
returned.
