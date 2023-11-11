## Protocol Building Blocks

### INTRODUCTION TO PROTOCOLS

The whole point of cryptography is to solve problems. (Actually, that's the whole point of computers—something many people tend to forget.) Cryptography solves problems that involve secrecy, authentication, integrity, and dishonest people.

A protocol is a series of steps, involving two or more parties, designed to accomplish a task. A “series of steps” means that the protocol has a sequence, from start to finish. Every step must be executed in turn, and no step can be taken before the previous step is finished. “Involving two or more parties” means that at least two people are required to complete the protocol; one person alone does not make a protocol. The action has to be completed inorder for it to be called as protocol. If someone bakes a cake, completing the baking is not a protocol someone has to eat it. if it does not accomplish a task, it is not a protocol it is a waste of time. 

Characteristics of a protocol:

    •	Everyone involved in the protocol must know the protocol and all of the steps to follow in advance.
    •	Everyone involved in the protocol must agree to follow it.
    •	The protocol must be unambiguous; each step must be well defined and there must be no chance of a misunderstanding.
    •	The protocol must be complete; there must be a specified action for every possible situation.

A cryptographic protocol employs cryptography in interactions between parties, whether trusting or adversarial. Beyond simple secrecy, the protocol's goals often include sharing secrets for computations, jointly generating random sequences, proving identity, or simultaneous contract signing. The use of cryptography in these protocols aims to prevent eavesdropping and cheating, showcasing their transformative potential for achieving secure communication and collaboration among mutually distrustful parties on a computer network.

The difficulty of designing secure protocols is highlighted as the author delves into numerous examples in the upcoming chapters. Certain protocols allow participants to cheat, while others may be susceptible to eavesdropping or the disclosure of secret information. Failures often result from inadequate requirements definitions or insufficient analysis by the designers, underscoring the challenge of proving security compared to demonstrating insecurity, a similarity to the complexity found in algorithm design.

#### The Purpose of Protocols

In daily life, informal protocols govern various activities seamlessly, from ordering goods to playing poker, relying on people's familiarity and adaptation. However, as more human interactions shift to computer networks, formal protocols become essential to replicate these processes. Unlike face-to-face interactions, computer protocols must address issues of honesty, security, and fairness, acknowledging the potential for dishonesty among network users, managers, or designers. By formalizing protocols, examining vulnerabilities, and abstracting tasks from specific implementations, a more robust foundation is established to ensure the integrity and security of computer-mediated interactions across diverse devices.

##### Arbitrated Protocols

An arbitrator is an impartial third party without a vested interest in a protocol, entrusted by all involved parties to ensure its completion. This concept, rooted in the history of society, involves individuals with authority and a social role to act fairly. While lawyers often serve as arbitrators in the real world, the ideal involves a high level of trust, where the arbitrator's actions and decisions are accepted as true and correct by all parties, with a recognition that betraying this trust could have severe consequences, such as disbarment for lawyers.

This ideal can translate to the computer world, but there are several problems with computer arbitrators:
    •	It is easier to find and trust a neutral third party if you know who the party is and can see his face. Two parties suspicious of each other are also likely to be suspicious of a faceless arbitrator somewhere else on the network.
    •	The computer network must bear the cost of maintaining an arbitrator. We all know what lawyers charge; who wants to bear that kind of network overhead?
    •	There is a delay inherent in any arbitrated protocol.
    •	The arbitrator must deal with every transaction; he is a bottleneck in large-scale implementations of any protocol. Increasing the number of arbitrators in the implementation can mitigate this problem, but that increases the cost.
    •	Since everyone on the network must trust the arbitrator, he represents a vulnerable point for anyone trying to subvert the network.

###### Adjudicated Protocols

Arbitrated protocols, due to the high cost of arbitrators, consist of two subprotocols: a nonarbitrated subprotocol for regular use and an arbitrated subprotocol for dispute resolution, involving a special type of arbitrator called an adjudicator. Unlike arbitrators, adjudicators are only involved in exceptional circumstances to determine the fairness of protocol execution. Adjudicators, similar to judges, are called in only when there's a dispute, distinguishing them from arbitrators. Adjudicated computer protocols, relying on honesty but enabling the detection of cheating, discourage dishonest behavior through the inevitability of detection rather than prevention.

###### Self-Enforcing Protocols

A self-enforcing protocol is ideal as it ensures fairness without the need for an arbitrator or adjudicator. The protocol is designed to prevent disputes by immediately detecting and stopping cheating. In the best-case scenario, all protocols would be self-enforcing, but not every situation has a suitable self-enforcing protocol.

###### Attacks against Protocols

Cryptographic attacks can target algorithms, techniques, or the protocols themselves. Assuming secure cryptographic algorithms and techniques, the focus is on examining attacks against protocols. Passive attacks, involving eavesdropping without affecting the protocol, aim to gain information and are challenging to detect. In contrast, active attacks involve altering the protocol to the attacker's advantage and can include impersonation, message manipulation, or interruption, posing more serious threats, especially in protocols where trust among parties is not assured. Active attackers may include legitimate users or even the system administrator, and detecting active cheating in a protocol can be challenging but crucial for maintaining security.

###### COMMUNICATIONS USING SYMMETRIC CRYPTOGRAPHY

How do two parties communicate securely? They encrypt their communications, of course. The complete protocol is more complicated than that. 

In summary, symmetric cryptosystems have the following problems:
    •	Keys must be distributed in secret. They are as valuable as all the messages they encrypt, since knowledge of the key gives knowledge of all the messages. For encryption systems that span the world, this can be a daunting task. Often couriers hand-carry keys to their destinations.
    •	If a key is compromised (stolen, guessed, extorted, bribed, etc.), then Eve can decrypt all message traffic encrypted with that key. She can also pretend to be one of the parties and produce false messages to fool the other party.
    •	Assuming a separate key is used for each pair of users in a network, the total number of keys increases rapidly as the number of users increases. A network of n users requires n(n − l)/2 keys. For example, 10 users require 45 different keys to talk with one another and 100 users require 4950 keys. This problem can be minimized by keeping the number of users small, but that is not always possible.

###### ONE-WAY FUNCTIONS

The concept of one-way functions is pivotal in public-key cryptography, serving as a foundational element for many protocols. One-way functions are computationally easy in one direction but significantly harder to reverse. While their existence lacks strict mathematical proof, many functions exhibit one-way characteristics. Unlike traditional one-way functions, trapdoor one-way functions incorporate a secret trapdoor, allowing efficient computation in one direction and challenging computation in the reverse direction. Analogously, disassembling and reassembling a watch illustrates the idea of a trapdoor one-way function, where the secret information functions as the "trapdoor" facilitating the inverse computation.

## ONE-WAY HASH FUNCTIONS

A one-way hash function, known by various names such as compression function, message digest, or cryptographic checksum, is a crucial element in modern cryptography and many protocols. Unlike traditional hash functions, a one-way hash function is designed to be computationally easy in one direction, generating a hash value from a pre-image, but difficult in the reverse direction, making it hard to create a pre-image that hashes to a specific value. The security of a one-way hash function lies in its one-way nature and collision-free property, where changing a single bit in the input significantly alters half of the bits in the hash value. Publicly accessible, one-way hash functions are useful for fingerprinting files and ensuring data integrity in various applications, such as financial transactions

## Message Authentication Codes

A Message Authentication Code (MAC), also referred to as a Data Authentication Code (DAC), is a one-way hash function enhanced with a secret key, where the hash value is derived from both the pre-image and the key. Similar to traditional hash functions, the primary difference lies in the inclusion of a secret key, ensuring that only individuals possessing the key can verify the hash value. MACs can be constructed from hash functions, block encryption algorithms, or dedicated MACs, providing a secure means of ensuring data integrity and authenticity in various cryptographic applications.
