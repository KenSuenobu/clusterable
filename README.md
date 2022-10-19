# clusterable

Clustering library that can be retrofitted into an application for easy clustering functionality.

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

