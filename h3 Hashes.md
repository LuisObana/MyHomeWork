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

## COMMUNICATIONS USING PUBLIC-KEY CRYPTOGRAPHY

Symmetric algorithms, likened to safes with a combination key, require both parties to share the same key for secure communication. In 1976, Whitfield Diffie and Martin Hellman introduced public-key cryptography, revolutionizing the field. This approach uses two distinct keys—one public and one private. While encryption with the public key is easy and accessible to anyone, only the holder of the private key can decrypt the message. The process is based on trap-door one-way functions, making encryption straightforward and decryption computationally hard without the private key. Public-key cryptography addresses the key-management problem by providing each user with a unique public and private key pair, facilitating secure communication in a network without the need for shared symmetric keys.

## Hybrid Cryptosystems

During the emergence of public-key algorithms, a period coinciding with the consideration of the Data Encryption Standard (DES), there was political tension within the cryptographic community. Despite generating excitement in the media and scientific circles, public-key cryptosystems faced resistance from the cryptographic establishment. Simultaneously, the National Security Agency (NSA) proposed DES, leading to criticism from experts such as Marty Hellman and Diffie, who argued that the proposed key size was inadequate. The criticism was met with skepticism, with some viewing it as an attempt to undermine the proposed standard for personal gain. Public-key cryptography itself was also subject to competitive attacks in sales literature and technical papers. Despite this, the NSA claimed credit for the discovery of two-key cryptography a decade earlier, although no supporting evidence was publicly provided.

In the real world, public-key algorithms are not a substitute for symmetric algorithms. They are not used to encrypt messages; they are used to encrypt keys. There are two reasons for this:
        1.	Public-key algorithms are slow. Symmetric algorithms are generally at least 1000 times faster than public-key algorithms. Yes, computers are getting faster and faster, and in 15 years computers will be              able to do public-key cryptography at speeds comparable to symmetric cryptography today. But bandwidth requirements are also increasing, and there will always be the need to encrypt data faster than                 public-key cryptography can manage.
        2.	Public-key cryptosystems are vulnerable to chosen-plaintext attacks. If C = E(P), when P is one plaintext out of a set of n possible plaintexts, then a cryptanalyst only has to encrypt all n possible                plaintexts and compare the results with C (remember, the encryption key is public). He won't be able to recover the decryption key this way, but he will be able to determine P.

A chosen-plaintext attack is effective when there are limited possible encrypted messages, allowing the cryptanalyst to systematically try various options. This vulnerability exists, for instance, if the plaintext (P) is a dollar amount below $1,000,000. Symmetric cryptosystems are not susceptible to this attack due to the inability to perform trial encryptions with an unknown key.

In practical implementations, public-key cryptography is often used to secure and distribute session keys, which, in turn, are employed with symmetric algorithms to secure message traffic—a setup referred to as a hybrid cryptosystem. This approach addresses a crucial key-management problem, as session keys are created when needed and destroyed when no longer required, minimizing the risk of compromise. While the private key is still vulnerable, its usage is limited to encrypting a session key once per communication, reducing the overall risk compared to symmetric cryptography.


## Cracking Passwords with Hashcat

Systems don't store original passwords, they store hashes. They look like this "f2477a144dff4f216ab81f2ac3e3207d". Hashing is a one way function, so you can't turn it back to password.

But you can make computer try every word in the dictionary, and tell if one matches.

Prior to working on an penetration testing techniques, ensure knowledge of legal and ethical considerations. Safe usage of these tools, tactics and procedure might need to obtain contracts and permissions and should posses adequate technical skills. Always <b>check the laws

Let us install Hashcat

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/6e04bb8c-0b3b-4f65-b8b2-c264ddc0e5b4)

Creating new directory specific for this work

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/6c9634e2-c59f-4d8f-83a5-fb516ece6254)

Get a big dictionary. Rockyou is probably the most popular

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/cc046dea-dd62-4244-93f7-1f247cb731bf)

It's just one word after another

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/cd033571-f591-4775-ad42-74bff661ce70)

### Identify Hash Type

Hashcat needs to know the type of the hash to crack, the number for the -m parameter. It's common to look at hashes really hard and compare them to 'hashcat --example-hashes'. However, there is an easy way

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/3506b9b1-1e5f-4c64-b1f7-3b57dda859a6)

In hashid, -m parameter shows the number that's used in the actual cracking, the hashcat parameter with the same name -m. Often, the right type is among top three candidates. If not, you can rule out many candidates based on where the hash was obtained (Windows, Linux...).

Note:
When I followed the instruction above, the first attempt I got the error below:

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/4ec9071f-7545-499f-837b-c358d489bb13)

I search for the error <b>"hashid: command not found" error in the web and found one solution provided that worked link: https://command-not-found.com/hashid
The advice was to install

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/2fb92121-21a2-4bb6-9b3b-6264637ed2b2)

After installation, I tried the command again and it worked

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/06a240dc-2216-4b64-b523-a582ae34993d)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/de6ae6f4-6bb2-4a04-b02b-f059b9c1ee88)

### Crack the Hash

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/a3c61e80-0087-409a-9cc2-d218ff96df5b)

After the first attempt, I got an error

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/9d0ebc2b-b778-479e-b13c-3fc58fe807b7)

I search the internet again and found similar error from others. Link: https://hashcat.net/forum/thread-10730.html  

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/e97452a3-a20b-462b-8bd6-d79357437590)

In logged off from my virtual machine and upgraded the RAM from 2000 MB to 4000MB. After that it worked

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/7b0e19b6-1e44-47d2-8d75-d5dc978d1ff8)

### What Did Hashcat Say?

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/05089610-5fdd-4ac9-a21a-0e59950413ab)

For the example in the image, the correct word was in RockYou dictionary, and you will crack it. For some, you might get "Status: Exhausted" instead of "Cracked". That would mean that all words in the dictionary were tried, but none of them worked.

### Where did the solution go?

If you said "-o solved", it's in that file. 'cat solved'.

If you already cracked it, but did not specify a file, you can see it with "--show":

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/0a5765aa-490c-4c94-b46f-719a9ab455e1)
