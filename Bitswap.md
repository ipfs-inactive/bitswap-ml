Bitswap Description (WIP)
===

Bitswap is a protocol for the exchange of data blocks between peers.  

Peers
-----
Peers have access to information about the network (e.g. latency of connections to peers).  Each peer also maintains information about their interactions with other peers (ledgers) and the hashes of the blocks it currently has and wants.

Exchanging Blocks
----
Peers should be able to request blocks from other peers and respond to requests themselves.  

When a peer opens a connection with another peer, it receives the ledger of the other peer.  Using this information, the peer can determine whether the other peer is malicious and can choose to ignore the request.  

If a peer opens a connection with another peer, they exchange want lists.  Want lists are then exchanged again on updates or specified time intervals.  If a peer has a block wanted by another peer, the block is sent probabilistically according to a strategy which is a function of the information the peer has access to.

If a block is sent, the receiving peer moves it from its want list to its have list, and the ledgers of both peers are updated.

Strategies
----
Each peer should utilize the information about the network to make trades that will maximize the data throughput to all peers in the system.

Thus, a good strategy should (taken from ipfs paper):
1. maximize the trade performance for the node, and the
whole exchange
2. prevent freeloaders from exploiting and degrading the
exchange
3. be effective with and resistant to other, unknown strategies
4. be lenient to trusted peers



