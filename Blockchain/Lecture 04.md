Pay to script hash

Requires that in order to unlock it, you need to provide a script with hash

==Soft fork== - when a transaction is accepted by a new implementation, it is also accepted by a old implementation

take a new element -> hash it -> run it as a program (something like that)

locking <-> unlocking (not clear)

Changing data in one block (left most) would change the hash for all the blocks next to it. That's kinda how it's tamper resistant.

In Merkel tree, to check whether two blocks contain the same tranactions, we can just check the root. The hash of the root is the certificate of all transactions.

Bitcoin P2P network

Nodes are connected over a network

But not sure whther a node is connected or not, a problem that needs to be solved

It all started with one node, running on the creators computer. Other nodes connected to that over a network.

In bitcoin, we use UTXO (Unspent transaction) mode to verify the transactions

90% of the nodes run bitcoin core

