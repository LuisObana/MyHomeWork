# Protocol Building Blocks

## INTRODUCTION TO PROTOCOLS

The whole point of cryptography is to solve problems. (Actually, that's the whole point of computers—something many people tend to forget.) Cryptography solves problems that involve secrecy, authentication, integrity, and dishonest people.

A protocol is a series of steps, involving two or more parties, designed to accomplish a task. A “series of steps” means that the protocol has a sequence, from start to finish. Every step must be executed in turn, and no step can be taken before the previous step is finished. “Involving two or more parties” means that at least two people are required to complete the protocol; one person alone does not make a protocol. The action has to be completed inorder for it to be called as protocol. If someone bakes a cake, completing the baking is not a protocol someone has to eat it. if it does not accomplish a task, it is not a protocol it is a waste of time. 

Characteristics of a protocol:

    •	Everyone involved in the protocol must know the protocol and all of the steps to follow in advance.
    •	Everyone involved in the protocol must agree to follow it.
    •	The protocol must be unambiguous; each step must be well defined and there must be no chance of a misunderstanding.
    •	The protocol must be complete; there must be a specified action for every possible situation.

A cryptographic protocol employs cryptography in interactions between parties, whether trusting or adversarial. Beyond simple secrecy, the protocol's goals often include sharing secrets for computations, jointly generating random sequences, proving identity, or simultaneous contract signing. The use of cryptography in these protocols aims to prevent eavesdropping and cheating, showcasing their transformative potential for achieving secure communication and collaboration among mutually distrustful parties on a computer network.

The difficulty of designing secure protocols is highlighted as the author delves into numerous examples in the upcoming chapters. Certain protocols allow participants to cheat, while others may be susceptible to eavesdropping or the disclosure of secret information. Failures often result from inadequate requirements definitions or insufficient analysis by the designers, underscoring the challenge of proving security compared to demonstrating insecurity, a similarity to the complexity found in algorithm design.

### The Purpose of Protocols

In daily life, informal protocols govern various activities seamlessly, from ordering goods to playing poker, relying on people's familiarity and adaptation. However, as more human interactions shift to computer networks, formal protocols become essential to replicate these processes. Unlike face-to-face interactions, computer protocols must address issues of honesty, security, and fairness, acknowledging the potential for dishonesty among network users, managers, or designers. By formalizing protocols, examining vulnerabilities, and abstracting tasks from specific implementations, a more robust foundation is established to ensure the integrity and security of computer-mediated interactions across diverse devices.

### Arbitrated Protocols

An arbitrator is an impartial third party without a vested interest in a protocol, entrusted by all involved parties to ensure its completion. This concept, rooted in the history of society, involves individuals with authority and a social role to act fairly. While lawyers often serve as arbitrators in the real world, the ideal involves a high level of trust, where the arbitrator's actions and decisions are accepted as true and correct by all parties, with a recognition that betraying this trust could have severe consequences, such as disbarment for lawyers.

This ideal can translate to the computer world, but there are several problems with computer arbitrators:
    •	It is easier to find and trust a neutral third party if you know who the party is and can see his face. Two parties suspicious of each other are also likely to be suspicious of a faceless arbitrator                somewhere else on the network.
    •	The computer network must bear the cost of maintaining an arbitrator. We all know what lawyers charge; who wants to bear that kind of network overhead?
    •	There is a delay inherent in any arbitrated protocol.
    •	The arbitrator must deal with every transaction; he is a bottleneck in large-scale implementations of any protocol. Increasing the number of arbitrators in the implementation can mitigate this problem, but         that increases the cost.
    •	Since everyone on the network must trust the arbitrator, he represents a vulnerable point for anyone trying to subvert the network.

### Adjudicated Protocols

Arbitrated protocols, due to the high cost of arbitrators, consist of two subprotocols: a nonarbitrated subprotocol for regular use and an arbitrated subprotocol for dispute resolution, involving a special type of arbitrator called an adjudicator. Unlike arbitrators, adjudicators are only involved in exceptional circumstances to determine the fairness of protocol execution. Adjudicators, similar to judges, are called in only when there's a dispute, distinguishing them from arbitrators. Adjudicated computer protocols, relying on honesty but enabling the detection of cheating, discourage dishonest behavior through the inevitability of detection rather than prevention.

### Self-Enforcing Protocols

A self-enforcing protocol is ideal as it ensures fairness without the need for an arbitrator or adjudicator. The protocol is designed to prevent disputes by immediately detecting and stopping cheating. In the best-case scenario, all protocols would be self-enforcing, but not every situation has a suitable self-enforcing protocol.

### Attacks against Protocols

Cryptographic attacks can target algorithms, techniques, or the protocols themselves. Assuming secure cryptographic algorithms and techniques, the focus is on examining attacks against protocols. Passive attacks, involving eavesdropping without affecting the protocol, aim to gain information and are challenging to detect. In contrast, active attacks involve altering the protocol to the attacker's advantage and can include impersonation, message manipulation, or interruption, posing more serious threats, especially in protocols where trust among parties is not assured. Active attackers may include legitimate users or even the system administrator, and detecting active cheating in a protocol can be challenging but crucial for maintaining security.

### COMMUNICATIONS USING SYMMETRIC CRYPTOGRAPHY

How do two parties communicate securely? They encrypt their communications, of course. The complete protocol is more complicated than that. 

In summary, symmetric cryptosystems have the following problems:

    •	Keys must be distributed in secret. They are as valuable as all the messages they encrypt, since knowledge of the key gives knowledge of all the messages. For encryption systems that span the world, this           can be a daunting task. Often couriers hand-carry keys to their destinations.
    •	If a key is compromised (stolen, guessed, extorted, bribed, etc.), then Eve can decrypt all message traffic encrypted with that key. She can also pretend to be one of the parties and produce false messages         to fool the other party.
    •	Assuming a separate key is used for each pair of users in a network, the total number of keys increases rapidly as the number of users increases. A network of n users requires n(n − l)/2 keys. For example,         10 users require 45 different keys to talk with one another and 100 users require 4950 keys. This problem can be minimized by keeping the number of users small, but that is not always possible.

### ONE-WAY FUNCTIONS

The concept of one-way functions is pivotal in public-key cryptography, serving as a foundational element for many protocols. One-way functions are computationally easy in one direction but significantly harder to reverse. While their existence lacks strict mathematical proof, many functions exhibit one-way characteristics. Unlike traditional one-way functions, trapdoor one-way functions incorporate a secret trapdoor, allowing efficient computation in one direction and challenging computation in the reverse direction. Analogously, disassembling and reassembling a watch illustrates the idea of a trapdoor one-way function, where the secret information functions as the "trapdoor" facilitating the inverse computation.

### ONE-WAY HASH FUNCTIONS

A one-way hash function, known by various names such as compression function, message digest, or cryptographic checksum, is a crucial element in modern cryptography and many protocols. Unlike traditional hash functions, a one-way hash function is designed to be computationally easy in one direction, generating a hash value from a pre-image, but difficult in the reverse direction, making it hard to create a pre-image that hashes to a specific value. The security of a one-way hash function lies in its one-way nature and collision-free property, where changing a single bit in the input significantly alters half of the bits in the hash value. Publicly accessible, one-way hash functions are useful for fingerprinting files and ensuring data integrity in various applications, such as financial transactions

### Message Authentication Codes

A Message Authentication Code (MAC), also referred to as a Data Authentication Code (DAC), is a one-way hash function enhanced with a secret key, where the hash value is derived from both the pre-image and the key. Similar to traditional hash functions, the primary difference lies in the inclusion of a secret key, ensuring that only individuals possessing the key can verify the hash value. MACs can be constructed from hash functions, block encryption algorithms, or dedicated MACs, providing a secure means of ensuring data integrity and authenticity in various cryptographic applications.

### COMMUNICATIONS USING PUBLIC-KEY CRYPTOGRAPHY

Symmetric algorithms, likened to safes with a combination key, require both parties to share the same key for secure communication. In 1976, Whitfield Diffie and Martin Hellman introduced public-key cryptography, revolutionizing the field. This approach uses two distinct keys—one public and one private. While encryption with the public key is easy and accessible to anyone, only the holder of the private key can decrypt the message. The process is based on trap-door one-way functions, making encryption straightforward and decryption computationally hard without the private key. Public-key cryptography addresses the key-management problem by providing each user with a unique public and private key pair, facilitating secure communication in a network without the need for shared symmetric keys.

### Hybrid Cryptosystems

During the emergence of public-key algorithms, a period coinciding with the consideration of the Data Encryption Standard (DES), there was political tension within the cryptographic community. Despite generating excitement in the media and scientific circles, public-key cryptosystems faced resistance from the cryptographic establishment. Simultaneously, the National Security Agency (NSA) proposed DES, leading to criticism from experts such as Marty Hellman and Diffie, who argued that the proposed key size was inadequate. The criticism was met with skepticism, with some viewing it as an attempt to undermine the proposed standard for personal gain. Public-key cryptography itself was also subject to competitive attacks in sales literature and technical papers. Despite this, the NSA claimed credit for the discovery of two-key cryptography a decade earlier, although no supporting evidence was publicly provided.

In the real world, public-key algorithms are not a substitute for symmetric algorithms. They are not used to encrypt messages; they are used to encrypt keys. There are two reasons for this:

        1.	Public-key algorithms are slow. Symmetric algorithms are generally at least 1000 times faster than public-key algorithms. Yes, computers are getting faster and faster, and in 15 years computers will be              able to do public-key cryptography at speeds comparable to symmetric cryptography today. But bandwidth requirements are also increasing, and there will always be the need to encrypt data faster than                 public-key cryptography can manage.
        2.	Public-key cryptosystems are vulnerable to chosen-plaintext attacks. If C = E(P), when P is one plaintext out of a set of n possible plaintexts, then a cryptanalyst only has to encrypt all n possible                plaintexts and compare the results with C (remember, the encryption key is public). He won't be able to recover the decryption key this way, but he will be able to determine P.

A chosen-plaintext attack is effective when there are limited possible encrypted messages, allowing the cryptanalyst to systematically try various options. This vulnerability exists, for instance, if the plaintext (P) is a dollar amount below $1,000,000. Symmetric cryptosystems are not susceptible to this attack due to the inability to perform trial encryptions with an unknown key.

In practical implementations, public-key cryptography is often used to secure and distribute session keys, which, in turn, are employed with symmetric algorithms to secure message traffic—a setup referred to as a hybrid cryptosystem. This approach addresses a crucial key-management problem, as session keys are created when needed and destroyed when no longer required, minimizing the risk of compromise. While the private key is still vulnerable, its usage is limited to encrypting a session key once per communication, reducing the overall risk compared to symmetric cryptography.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Cracking Passwords with Hashcat

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

## Command Line Basics Revisited

Checking the current directory

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/4a36a9ca-a692-4f81-b502-00e9c75d84be)

Note: *Dollar sign “$” is the normal user command prompt, user does not write that. After a command, hash mark “#” is comment character, rest of the line is ignored.*

When working on a terminal, you are always on a directory. Current directory is the *working directory*. The code <b>pwd prints the working directory. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/7d5baec5-716d-4a63-87ec-1c7d28764d9d)

To check the list of files we can manipulate, the code to use is *ls*. If the shell says *No such file or directory* means it does not exist but it is always wise to check.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/10694a08-bf66-46f4-9291-efca693c1887)

The command to use when changing directory is *cd*. See image below for the change from being on the main directory to the Newfolder directory

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/e07ec7e7-4ca9-40ff-a5a5-d31572fd6fb9)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/14829c39-04aa-4560-be0e-814cda14b465)

To go back to the previous directory, you can type *cd ..*

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/799600a5-98d0-45c8-a4fa-433e93f277cb)

Creating a new file in terminal we can use pico and nano (popular codes) and use CTRL+X y then ENter to save and exit. You can also see this commands at the bottom of the screen. Example Ctrl + X is the same as ^X. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/05685be7-080e-4a86-b495-d772a0be7c22)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/7e6a2164-f3d5-4f4f-8e1c-193c2d73bae0)

To check if file was saved, type ls or list of files

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/3f0e3004-3c30-4e5e-a893-ca2292a94ae4)

Making a new directory, the code is mkdir Newfolder(foldername)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/a086ba0d-1ff4-453d-adaa-f0b0adddbf49)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/cd5b855a-de80-4056-b63b-9c2e1b2cd398)

Note: I have used ls to check if the new folder was created

Moving files between directories or renaming files the command is mv oldname newname

    1. If Newname does not exist, oldname is renamed to Newname
    2. If both parameters are files, Newname is overwritten
    3. If target is directory, oldname is moved there

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/3d5cbf3b-0c84-437d-bbd7-46eb96b5768c)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/42078489-d12e-469f-9fbe-dc5a3597706c)

## SSH Remote Control

To open a remote command shell in avery secure way, we use ssh. 

On my first attempt, it did not went trough because ssh was not installed yet. Hence I installed ssh. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/031a053b-079f-4b15-9936-6a5aa109799c)

Tried connecting to gmail using ssh but did not work

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/4648ae95-1e81-4c32-aaf6-dfe402091843)

Some Useful Helps

    1. To show manual use the command $ man ls
    2. Short built in help
        2.1. $ ls --help
        2.2. $ wget -h

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/006832ab-b18b-484f-bf7c-646b5824f0be)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/0099dd3f-cd42-4dd9-86b1-9a34b25e23f3)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/0d667add-e783-4b6c-9732-a64d844d4f0f)

## History and Guessing

Tab (above caps lock) can be used to show what needs to be type next. 
History command can also be use to check all the commands used in the terminal.

## Important Directories

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/6268cdf5-e061-4317-bc41-afe19c73f374)

## Administrative Commands

Minimum privilege principle states that we do operations with the lowest level of privileges possible. Only operations requiring high privileges are run with 'sudo'. These commands gain unlimited privileges.

Commands affecting the whole system require higher privileges. Such operations include installing and removing software, creating users and managing privileges.

### Package Management - Installing Software

Package mangement is a safe and convenient way of installing software.

Update list of available packages. Run apt-get update before giving other apt commands.

=============================================================================================================================================================================================================================================================

## Password Attack

Major companies being attacked (LinkedIn)

    Store user credentials in SQL database or text file
    Web app SQL DB, active directory Proprietary database

Recent Petya ransomware attack
    Exploited the system initially using the EternalBlue Exploit and then what the payload did is to use a tool          called Mimikatz (what this tool do is to dump the credentials out of memory) and from there they utilize the         credentials to steal and attack other systems on the network using well known protocols like PsExec and WMI that     are used all the time in windows so the attack would look like a normal traffic. 

Defending against this type of attacks
    It is very difficult and usually it seems like a mouse and cat game, where we work on it from the defense side.
        •	Two ways to defend from password attack
            o	Protect both the storage side and while they are being transmitted over the network. For the storage                 there are various ways to defend, Operating Systems (OS) have their own protective measures. 
                    1. Limit the access to these storage mechanisms to people who only needs the access
                    2. Have intrusion detection and Endpoint protection
                    3. Auditing is also a good approach so you would be able to see if anything looks fishy or if                           people are accessing it in ways that they shouldn’t be
            o	While password is being transmitted over the network, we have to use encryption to ensure that                       people listening over the network traffic cannot intercept that information
            o	From an end user standpoint, to protect your own account, it is highly recommended to:
                    1. Make your passwords longer
                    2. Enable two-factor authentication (when possible)

Understanding Authentication and Authorization Attacks

    o	Easy way to hack passwords – often referred to as cheating.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/e948fe25-59a2-4e3e-9769-c53a1a521192)

Vendors often use default passwords and users of software’s/hardware’s often does not change their passwords like they should. As an attacker these can be used against them

    •	A number of websites, when we search, can provide us a list of default passwords based on what we are trying         to attack
            o	Example if you are looking for a specific type of router, then you can simply look it up on the                      router list
    •	We live in a world, where we often need to remember a lot of different passwords. To solve this issue what           we do is one password for all (not the best resolution). 
    •	If we are to find the administrator account password, it would be easy to compromise the rest of the                 computers on the network

Easiest ways to capture credentials
    The first goal of credential attacks is to actually identify valid users and then attack the passwords. There        are some methods to use in identifying the valid users

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/af175bb5-3f3a-4904-8a0a-d3023c7436bc)

Sniffing them right out of thin air
    Using a hotspot in common areas like coffeeshops or hotels, since they don’t have the security mechanism which       is built into them, or enabled, to encrypt the traffic between network nodes which means that once you are           connected to that network, one can sniff the traffic of any user that’s connected. So make sure that the next        time you connect to a public hotspot you are connected or using a VPN.  This is a similar scenario when              connected to a physical network which is of course dependent on the switch configuration, which can be difficult     but there tools available to get around it. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/c54ede63-b151-485d-80a4-f06e7ebb7126)

Man in the middle attack is another way of capturing credentials.

    Man in the middle attack means that essentially you own the traffic that’s passing through you so you can            capture it and pull out the credentials from that traffic.

Ways in attacking encryption to steal passwords (Complex types of attacks)
    1. SSL Certificate spoofing
    2. SSH Downgrade and key spoofing

Stealing credentials directly from the network device
    Compromising a router or switch or a wireless access point you can easily own the traffic and harvest the            credentials directly from that device

If all else fails, you can brute force your way in. There are a lot of tools we can use but most of them work by loading in some kind of dictionary or table of credentials or hashes. Then use these loaded credentials in an automated way to basically test the credentials against whatever your target is. 

    1. It will iterate through the list of credentials that it has until it finds the one that works
    2. You can use brute forcing other than capturing credentials
        o	For instance, the tool called Dirbuster, which is built in to Kali Linux, which is used to discovering               directories and files on web servers. It uses a dictionary of well-known website files and directories.              The same process is used, it iterates through the list of finds the one that actually respond. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/c3c65c0a-e579-4c87-8d63-22ec27bf4590)

Exploring Password Storage Mechanisms 
    1. Encryption has been part of signals intelligence for quite some time.
    2. If you want to protect a secret, encrypt it. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/bb625345-8f78-4782-83d2-b74c0e7cfeb9)

One way hashing is not an encryption but it is used to protect passwords, though it is not reversible, its algorithms is designed to be computed quickly. So you can compute many hashes from a dynamic source like word list or permutations, brute force and compare the result to find a match. 

How hashing works

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/82376aa0-bac2-4407-a626-361aa3099a3d)

Start with the words, on this example we use Pearson, then send it through a hash function, for this example we use MD5. Since it applies one way algorithm, the output is a string of characters which is unique to a specific clear text (input). Now the string can be used in various ways to verify the integrity of the clear text that was provided. 

We can also use SHA256 aside from MD5 which is a better algorithm. 

Understanding Password Storage Vulnerability
    Why is it easy to crack passwords? If passwords are not encrypted, it is easy to crack. 

   ![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/2768dc9b-432a-4cd4-ae1d-27ecafd5d783)

 It is easier to crack passwords even if encrypted for several reasons:

    1. We used to rely only on CPU’s, even though it gets faster and faster which in turn results to cracking               password faster, now we also have GPU’s are used to crack password as well. GPU’s are often much faster than         relying on CPU. Another is you can distribute the computation across CPU and GPU to crack the same password          set which often increases the speed of cracking the password. There are also weak algorithms which makes it          easier to crack the password. 

    2. Cracking Window’s LanMan and NT passwords are slightly different, it is easily spot on how the LanMan                passwords are easy to crack that the NT for several reasons:
            2.1 LanMan – automatically takes your password and makes it all upper case and then it splits it into                    two seven – character passwords and so you can crack all upper case passwords and two sub seven-                     character sets which makes it easy to crack. Windows does not have salting and algorithms which is                   much easier to crack passwords

                2.1.1. So to explain, in Windows if two different individuals have the same password their hash                             would look exactly the same, in Linux because of salting, it would be two different hashes.                          So weak algorithms is a big issue
                        2.1.1.1. Password breaches – you can look up previous breaches online since there is a                                        tendency for people to use same password over and over again, it can help you with                                   cracking ability
                        2.1.1.2. Rainbow Tables – don’t have all the combinations of a password, they use a                                           reduction function to actually get a large number of passwords, upwards of 99% of                                    the passwords per certain sets within smaller files
                2.1.2. There are dictionaries which have been built over time based off of rainbow tables or                                password breaches

                ![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/7563d2e9-2afe-48e6-ae05-b237d3f881d2)

## Cracking Password with John The Reaper

    1. Comes with Kali Linux and one of the standard ways of cracking password. Very easy to crack
    2. Install John in terminal

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/731cf527-176d-40e9-9a7c-180e81eb4396)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/b9b68f56-f1f9-45a9-a8f5-b0ab679bc5f3)

Type john on the terminal to see the menu 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/52b530eb-1b76-4d87-8777-11c69a60a69e)

Got an error when trying to execute the commands for John the Ripper

<b> Command not Found

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/2b4a4470-62ce-4425-813f-b31a2af4fc5f)

===================================================================================================================

## Billion dollar busywork. Command 'echo -n 'Tero'|sha256sum' prints hash "ba2addbf481bdf4a0178cbf5608e681cb9af519d85fe4d51efe88a4eed9673ed". Try adding something to the string, e.g. 'echo -n 'Tero asdf'|sha256sum'. What do you have to add to get a hash that starts with a zero? (Voluntary bonus: How is this related to Bitcoin? Voluntary difficult bonus: How many zeros can you get to the beginning?)

To add zero I used python to check combinations I can use. Note: that finding a nonce that satisfies the difficulty criteria requires significant computational effort and is not a straightforward task. I use nonce (a number used only once) to the input string until you achieve the desired hash. The process of finding the nonce to produce a hash with a specific property is known as "proof of work." In the context of Bitcoin, this process is central to mining.

Sample:

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/8ab14583-31f3-48ba-bb16-e61a59ab458c)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/92a5b9f9-e823-4f7c-9b59-55622378f95f)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/c0f109e2-81aa-4107-862d-c5d81b8f3070)

In Context to Bitcoin

**Proof of Work (PoW)**: Bitcoin miners compete to find a nonce that, when combined with the block's data, produces a hash that starts with a certain number of leading zeros. The difficulty of finding this nonce is adjusted regularly to maintain a consistent block time (approximately 10 minutes).

**Mining Reward**: Miners who successfully find the correct nonce and validate a block are rewarded with newly created bitcoins. This process secures the Bitcoin network and ensures the chronological order of transactions.

**Bitcoin Hash Rate**: The total computational power of the Bitcoin network, measured in hashes per second, determines how quickly new blocks can be mined. As more miners join the network, the difficulty increases to maintain the target block time.

====================================================================================================================
## Compare hash. Create a small text file. Take it's hash (e.g. 'sha256sum tero.txt'). Change one letter. Take the hash again. Compare hashes. What do you notice?

If you create a small text file, take its hash (e.g., sha256sum tero.txt), change one letter in the file, and then take the hash again, you will observe that the hashes are substantially different. Even **a small change in the input data should result in a significantly different hash output**. This property is known as the **avalanche effect in cryptographic hash functions**.

I have created my initial hash

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/9995fec9-4a92-45d6-9109-47d5ab4841f8)

Change one letter from the initial hash

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/cc1666b4-26f4-4851-a619-9ba1633909e6)

You can see that the hash has changed. Even a slight change on the original word the hash result has completely changed. 

================================================================================================================

## Installing Hashcat

As a personal step, I update the Debian terminal first before I do the installation. Next is to type the code to be use for the download and install. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/6d58027e-84fc-4252-a55b-c17b9a2e7836)

Test if Working

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/b2e67cfb-5702-4a39-9aaf-0de97115494d)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/a8d96151-7aad-43b2-8ee6-5d84186b900d)

For this testing, the installation of hashcat was successful and it is working. 

==================================================================================================================
## Crack this hash: 21232f297a57a5a743894a0e4a801fc3

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/f5c84823-0065-4edb-8273-fc455227e85d)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/a815c5ce-45a4-4a7f-a247-444012882504)

=================================================================================================================
## Crack this Windows NTLM hash: f2477a144dff4f216ab81f2ac3e3207d

We'll use the same command as we did for the MD5 hashes, but we will **swap the -m 0 for -m 1000**..

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/28fbd496-f7ca-4bdf-a8b3-1186e877d99b)

We can see that the NTLM hash was successfully cracked! This a perfect example of why everyone should use a secure password.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/73d1b5b4-c349-44f8-b266-caec748d8f9d)

===================================================================================================================
## Try cracking this hash and comment on your hash rate $2y$18$axMtQ4N8j/NQVItQJed9uORfsUK667RAWfycwFMtDBD6zAo1Se2eu . This subtask d does not require actually cracking the hash, just trying it and commenting on the hash rate.

It was faster but I did not actually crack the hash.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/674aa7c3-d4d6-48e3-b164-25f7957e99d9)

