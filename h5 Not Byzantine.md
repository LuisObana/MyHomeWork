## Bitcoin: A Peer-to-Peer Electronic Cash System

The concept of a purely peer-to-peer electronic cash system that enables online payments directly between parties without the need for a financial institution. Digital signatures address part of the security challenge, but the issue of double-spending remains. The proposed solution involves a peer-to-peer network that timestamps transactions through a chain of hash-based proof-of-work, creating an unchangeable record. The longest chain, backed by the most CPU power, serves as proof of transaction sequence and is resistant to attacks as long as the majority of CPU power is controlled by non-cooperating nodes. The network is designed with minimal structure, allowing nodes to join or leave at will, accepting the longest proof-of-work chain as the authoritative record.

The reliance of online commerce on financial institutions as trusted third parties for electronic payments, highlighting the limitations of this trust-based model. The current system faces challenges such as non-reversibility of transactions, increased mediation costs, and the need for trust in various transactions. The paper suggests the need for an electronic payment system based on cryptographic proof rather than trust, enabling direct transactions between parties without intermediaries. The proposed solution involves a peer-to-peer distributed timestamp server to establish computational proof of transaction chronology, ensuring security as long as honest nodes collectively possess more CPU power than potential attacker nodes. This approach aims to address the double-spending problem and enhance security in online transactions.

### Transactions


The concept involves defining an electronic coin as a chain of digital signatures. The transfer of ownership occurs when the current owner digitally signs a hash of the previous transaction and the public key of the next owner. These signatures are added to the end of the coin, forming a chain. The payee can then verify the signatures to confirm the chain of ownership.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/1909982d-dc4c-42de-b45b-09a35e6a1a70)


The challenge is that a payee cannot verify if an owner has double-spent a coin. A common solution involves a trusted central authority or mint that checks transactions for double spending. However, this approach relies on the mint, and all transactions must go through them, similar to a bank, posing a risk to the entire money system. To address this, there's a need for a method to confirm that previous owners did not sign earlier transactions. This requires public announcement of transactions and a system for participants to unanimously agree on the order of transaction history without a trusted party. The payee needs proof that, at the time of each transaction, the majority of nodes acknowledged it as the first received.

### Timestamp Server

The proposed solution involves a timestamp server that takes a hash of a block of items to be timestamped and publicly publishes the hash. This timestamp demonstrates that the data must have existed at that time to be included in the hash. Additionally, each timestamp includes the previous one in its hash, forming a chain where each new timestamp strengthens the preceding ones.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/fd4ef509-3386-432c-bfd1-b66ad2c78f6d)

### Proof-of-Work


To establish a distributed timestamp server on a peer-to-peer basis, a proof-of-work system, similar to Hashcash by Adam Back, is proposed instead of traditional methods like newspaper or Usenet posts. This proof-of-work entails finding a value, achieved by scanning, such that when hashed (e.g., with SHA-256), the hash begins with a specified number of zero bits. The effort required is exponentially related to the number of zero bits, and its validity can be confirmed through a single hash. In the timestamp network, proof-of-work is implemented by incrementing a nonce in the block until a value is found that meets the zero bits requirement. Once the CPU effort is expended to satisfy the proof-of-work, the block becomes unchangeable without redoing the work, as subsequent blocks are linked to it, necessitating the redoing of all subsequent blocks to make any alterations

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/a690e842-c03f-49ce-82a6-b5007a20b556)


The proof-of-work mechanism addresses the challenge of determining representation in majority decision-making. Unlike a one-IP-address-one-vote system susceptible to manipulation, proof-of-work establishes a one-CPU-one-vote principle. The majority decision is reflected in the longest chain, indicating the highest proof-of-work effort invested. If a majority of CPU power is under the control of honest nodes, the honest chain grows the fastest, surpassing competing chains. Modifying a past block requires an attacker to redo the proof-of-work for that block and all subsequent blocks, overtaking the work of honest nodes. The probability of a slower attacker catching up diminishes exponentially with the addition of subsequent blocks. To adapt to changing hardware speed and node participation, the proof-of-work difficulty is regulated by a moving average, targeting a set number of blocks per hour, with increased difficulty if blocks are generated too quickly.

### Network

The steps to run the network are as follows:

    1) New transactions are broadcast to all nodes.
    2) Each node collects new transactions into a block. 
    3) Each node works on finding a difficult proof-of-work for its block.
    4) When a node finds a proof-of-work, it broadcasts the block to all nodes.
    5) Nodes accept the block only if all transactions in it are valid and not already spent.
    6) Nodes express their acceptance of the block by working on creating the next block in the
    chain, using the hash of the accepted block as the previous hash.

Nodes in the network always consider the longest chain as the correct one and continuously strive to extend it. If two nodes simultaneously broadcast different versions of the next block, some nodes may receive one version first and start working on it, keeping the alternative branch in case it becomes longer. The tie between branches is resolved when the next proof-of-work is found, and one branch becomes longer; nodes switch to the longer one. New transaction broadcasts don't have to reach all nodes but need to reach many to be included in a block eventually. Block broadcasts are resilient to dropped messages; if a node misses a block, it requests it when receiving the next one.

### Incentive

The first transaction in a block conventionally initiates a new coin owned by the block creator, creating an incentive for nodes to support the network and facilitating the initial distribution of coins without a central authority. This continual addition of new coins mirrors the idea of gold miners investing resources to introduce gold into circulation, with CPU time and electricity being the resources in this case. The incentive can also be supplemented with transaction fees, where the difference between input and output values becomes a transaction fee added to the block's incentive value. Once a set number of coins are in circulation, the incentive can shift entirely to transaction fees, making the system inflation-free. This incentive structure encourages nodes to remain honest, as an attacker with more CPU power than honest nodes must decide between defrauding people or generating new coins. It is more profitable for the attacker to follow the rules, which favor them with more new coins than undermining the system and devaluing their own wealth.

## References:
  1. Satoshi Nakamoto **Bitcoin: A Peer-to-Peer Electronic Cash System** Link: https://bitcoin.org/bitcoin.pdf

