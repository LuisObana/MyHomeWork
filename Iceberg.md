##  Hiding Behind the Keyboard: The Tor Browser

The Tor browser, derived from Firefox, significantly enhances anonymous Internet use by concealing the user's IP address. This modification makes it extremely difficult to trace or identify users without employing advanced methods. Tor ensures both ease of use and effective anonymity, making it accessible to a wide range of users without the need for technical expertise. Despite alternative methods for anonymous browsing, Tor stands out as one of the simplest and freely available options, allowing anyone with an Internet connection to surf and communicate online while remaining unidentified.

### History and Intended Use of The Onion Router

Tor aims to enable unrestricted and anonymous internet communication, providing access to blocked websites, facilitating anonymous communication for whistleblowers, and offering a secure means for private conversations. While initially developed by the US government in 2002, Tor is currently independent of any single entity and is open for global contributions to enhance its functionality. Despite its positive uses, like any tool, Tor can be misused for criminal activities. Interestingly, the US government, which created Tor, is also researching ways to deanonymize its users, adding an ironic twist to its history.

### How The Onion Router Works


In simple terms, Tor guides a user's internet traffic through random relays, applying layers of unbreakable elliptic curve cryptography. As the data passes through each relay (entry, middle, exit), one layer of encryption is removed, ensuring anonymity and security until the final relay connects to the user's intended destination with an unencrypted connection.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/1f8ae18d-7721-4310-bd82-f89065d7e4e5)

The exit relay does not know anything of the traffic route other than the single previous relay. Making Tor traffic even more difficult, if not impossible, to track is that this random route chooses a different entry, middle, and exit relay every 10 minutes or so. Fig. 2.1 shows a graphic from Tor Project (n.d.) visualizing this concept of Tor.

An analogy of Tor would be mailing a letter that is received and forwarded by different people. Let’s say Mary wants to mail Johnny a letter, but does not want Johnny to know where the letter originated. The steps Mary needs to take to remain anonymous would be as follows:

        1. Mary writes a letter and places it into an envelope addressed to Johnny in Boston.
        2. Mary places that envelope into another and addresses it to Susan in Seattle.
        3. Mary places that envelope into another and addresses it to Barry in Dallas.
        4. Mary places that envelope into another and addresses it to Bob in Denver.
        5. Mary places the letter in a mailbox from her home in San Francisco.

In this analogy, the Tor network is likened to sending letters in envelopes. Each envelope represents a layer of encryption, and each person in the process can only unwrap the outermost envelope. Bob (entry) receives the letter, removes the outer envelope, and sends it to Barry. Barry (middle) does the same and passes it on to Susan. Susan (exit) removes the final envelope and sends the letter to Johnny. The contents remain hidden until the last step, creating anonymity. The process, akin to peeling layers off an onion, ensures that the original sender's identity is concealed. This instantaneous and anonymous data transfer through Tor contrasts with traditional mail, which takes days. The name "The Onion Router" reflects this layered encryption process.

## I’m just an exit node! I’m just an exit node!

*Sometimes the IP address you get is not the IP address you need.*

In 2011, Immigration and Customs Enforcement (ICE) executed a search warrant on Nolan King’s home and seized his computers because an ICE investigation found that child pornography was being distributed from his home IP address (Hoffman, 2011). No child porn was found because King was simply operating a Tor exit node

### Tracking Criminals Using Tor

Tracking Tor users is challenging, and many government agencies are actively working to deanonymize Tor for various reasons, including identifying criminals and terrorists or restricting citizens' access to the internet. While some successes have been reported in the news, these often result from exploiting errors made by suspects rather than directly breaking Tor's encryption. Access to federal resources for investigating Tor users is likely limited for the majority of investigators unless the case involves a terrorist connection, leaving individuals to conduct their own investigations without assistance from the National Security Agency.

The FBI used a Firefox exploit to take down a child pornography hosting service on the Tor network. The exploit targeted a bug in Firefox (CVE-2013-1690) to capture the true IP address, MAC address, and Windows hostname of Tor browser users, sending the information to the FBI until the exploit was patched. Linux Tor users and those with updated Tor versions seemed unaffected.

The main weakness of the Tor browser is user behavior. While the browser is preconfigured for security, any customization, especially regarding geolocation settings or allowing scripts and plugins, can compromise anonymity. Researchers have explored various methods, such as attacking the Tor network, gaining control of entry and exit nodes, and man-in-the-middle attacks, to deanonymize users, but these methods require substantial resources and time.

Despite challenges, investigators seek the true IP address in internet-related investigations. Potential methods include seeding tracking codes in emails or documents sent to suspects, which, when opened, can reveal the true IP address. However, these methods carry risks of alerting suspects. Identifying Tor users outside the network may involve utilizing open-source and online investigative methods, leveraging information available on the open web to unveil details about suspects operating in the Dark Web.

The Silk Road case involving Ross Ulbricht highlights how a suspect's mistakes, such as using a personal email and real name on the open internet, can make investigations easier. In the context of internal corporate networks, if Tor is used, network administrators can identify Tor users by monitoring internet access, even though they can't see the content of messages or websites. This advantage becomes crucial in cases where a victim has an idea about the suspect's identity. By identifying the suspect's employment and tracking local users accessing the Tor network, investigators may link the suspect to specific actions, such as sending threatening emails, based on the timing of network access and email receipt.

In 2013, Harvard student Eldo Kim used Tor to send email bomb threats to Harvard staff in an attempt to avoid taking an exam. Harvard's IT staff identified Kim's Tor usage through their logs, and when questioned by FBI agents, Kim admitted to the act. This case exemplifies how breaks in investigations often occur due to mistakes made by suspects. In the context of Tor browser use, a suspect may unintentionally use a non-Tor browser, thinking it provides anonymity. However, any emails or internet connections through a non-Tor browser reveal the true IP address of the suspect, leading to their identification.

## 7 Things You Should Know About Tor

The author highlights their Tor Challenge, encouraging Tor usage, and reports having signed up over 1000 new Tor relays in two weeks. The post aims to address common myths and misconceptions about Tor, seeking to provide clarification on its functionality and purpose.

**1. Tor Still Works** - The NSA leaks revealed that Tor remains effective in providing anonymity, as indicated by the NSA's acknowledgment that "Tor Stinks" but also its inability to completely circumvent Tor's anonymity. While certain Tor users in specific situations have been compromised, historical compromises often resulted from exploiting Tor Browser Bundle vulnerabilities or misconfigurations by users. The FBI, possibly with NSA collaboration, exploited a Firefox vulnerability leading to the takedown of Freedom Hosting, but Firefox was promptly patched, and no major exploits affecting Tor users have been discovered since. Tor developers highlighted in 2004 that if both your network traffic and the service you're communicating with are actively monitored, Tor can't prevent detection. This suggests that Tor likely remains secure at a cryptographic level, with the primary vulnerabilities being side-channel attacks on browser bugs, user misconfigurations, and traffic correlation attacks.

**2. Tor is Not Only Used by Criminals** - The misconception that Tor is solely used by criminals and pedophiles is debunked in the assertion that Tor serves a diverse range of users. Activists employ it to bypass censorship and maintain anonymity, the military relies on it for secure communications, families use Tor to safeguard children and privacy, and journalists utilize it for secure research and source communication. The Tor Project website explains that Tor doesn't significantly aid criminals because those with malicious intent already have more effective tools at their disposal, such as botnets, stolen devices, and identity theft. In fact, using Tor can enhance personal protection against tactics like identity theft or online stalking employed by criminals. The message is clear: using Tor doesn't assist criminals any more than using the internet does.

**3. Tor Does Not Have a Military Backdoor** - A prevalent misconception suggests that Tor, having received initial funding from the US Navy, must have a military backdoor. This notion is dispelled by clarifying that there is no backdoor in the Tor software. Despite its origins in military funding, Tor has undergone audits by knowledgeable cryptographers and security professionals who confirmed its integrity. Being open source, the code is accessible for examination by any programmer, ensuring transparency and dispelling concerns about hidden vulnerabilities. Tor is actively developed by a dedicated team of activists committed to privacy and anonymity.

**4. No One in the US Has Been Prosecuted For Running a Tor Relay** - According to the Electronic Frontier Foundation (EFF), as of their knowledge, no one in the US has faced legal action for operating a Tor relay, and they do not believe that running a Tor relay is illegal under US law. While this doesn't guarantee immunity from law enforcement contact, especially for those running exit relays, the EFF is confident enough in the legality that they operate their own Tor relay. They encourage users to explore the legalities further through the Tor Challenge Legal FAQ. However, the EFF emphasizes that engaging in criminal activities using Tor can lead to legal consequences and increased scrutiny on the Tor network, negatively impacting the public as a whole.

**5. Tor is Easy to Use** - Contrary to the assumption that privacy software like Tor is difficult to use, it is, in fact, user-friendly. The simplest way to start using Tor is by downloading the Tor Browser Bundle, a pre-configured browser ensuring secure Tor usage. It's easy to use and sufficient for browsing with Tor. Another convenient option is Tails, a live operating system running from a DVD or thumb drive, which routes the entire internet connection through Tor. Notably, Tails forgets all activities once shut down, ensuring enhanced privacy.

**6. Tor is Not as Slow as You Think** - While Tor is slower than a standard internet connection, the Tor developers have been actively working to improve its speed, resulting in the network being faster than ever before. A key strategy to enhance Tor's speed is to create more relays.

**7. Tor is Not Foolproof** - Tor is not flawless, and incorrect usage can compromise anonymity. To mitigate risks, it's crucial to always use Tor Browser Bundle or Tails and keep the software up to date. Logging into services like Google and Facebook over Tor may expose your communications within their systems. Tor users should be cautious, considering that an adversary with visibility on both sides of the connection might conduct statistical analysis to confirm the user's identity.

Tor is some of the strongest anonymity software that exists. We think that it is important to dispel misconceptions about it so that the public can be more informed and confident in its usefulness. There are many great reasons to use Tor and very few reasons not to. So get started with Tor, and take back your privacy online.

## References:
    1. Shavers & Bair 2016: Hiding Behind the Keyboard: The Tor Browser Link: https://learning.oreilly.com/library/view/hiding-behind-the/9780128033524/XHTML/B9780128033401000021/B9780128033401000021.xhtml#s0020
    2. Quintin 2014: 7 Things You Should Know About Tor Link: https://www.eff.org/deeplinks/2014/07/7-things-you-should-know-about-tor 

## Install TOR Browser

Step 1. Open the Debian VM and do sudo update

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/3fa08dac-fa52-4708-bee7-9510df392444)

Step 2. Search for TOR within the VM environment and follow the instruction provided from the link. 
Link used: https://support.torproject.org/apt/tor-deb-repo/ 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/030c360a-7e66-4ae8-8592-eb5f0ebe5713)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/bccb15a9-4488-4eef-9c2f-f321b1337a2e)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/d185c9ac-84c6-4bcd-8993-58fef0e7a55a)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/816f9753-f8eb-4cbc-bd4d-e789cbda33dc)

Ste 3. Go to download file

Ste 4. Verify the File's signature

Ste 5. Extract the downloaded file

Step 6. Open the extracted folder and look for the start-to-browser file. Right click and choose run in terminal. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/0ad53f50-b76a-4b7e-b888-b8cb9e23e1a5)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/b6e326d3-1d9c-4017-a1cb-34a9be77f7c4)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/402283ed-fd20-46a5-94bd-d88edc661dac)

## Browse TOR network, find, take screenshots and comment

### Search Engine for Onion Sites 

Similar to the normal search engine though I am not really inclined to use because I am not that familiar with this and I dont want my network to be compromised. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/aa740c10-a151-4442-aeae-c7dabd81d06c)

### Marketplace

When I started the search engine, it was slower than usual speed using normal browser. When I saw the prompt allow cookies I declined all. As mentioned I am not familiar and I want to be cautious of all the sites I worked with on this assignment. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/69db4186-d6a0-4e31-8bad-0869ee578b57)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/30729b46-3e3a-43e4-8467-c050c3f5cfab)

### Fraud

The performance was the same, it was slower than usual. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/95589480-723a-473c-a8a2-17fa82fb241d)

### Forums

The performance was the same, slower than usual. I clicked one, as indicated on the screenshot below, they are asking for a donation so I close the browser. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/dc5789ed-4051-4754-af93-46bef333a27b)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/dc5d70d0-716b-4f10-a91f-b1f2146d8715)

### Well known Organization

The speed to load was a little faster compared to the rest. Though I see that the page is in TOR Circuit, I don't see any difference on the landing page when I clicked on the Accenture link. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/8a69f91d-7c3d-422b-ae78-fa84e915a937)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/f2eddff5-27bb-4cdb-92af-c738bb64785f)


## Reference:
        1. Tor Project. Link: https://www.torproject.org/download/

##  In your own words, how does anonymity work in TOR? (e.g. how does it use: public keys, encryption, what algorithms?

**Disclaimer!!** I am not familiar with TOR so I cannot provide an explanation. I researched and found one closer to answering the question above. Link indicated on the reference. 

### How does Tor, the dark web browser, work?

Tor uses onion routing to encrypt and reroute web traffic through Tor’s onion network. After your data is secured inside multiple layers of encryption, your web traffic is transmitted through a series of network nodes, called onion routers. Each router (or node) “peels away” a layer of encryption until the data reaches its final destination, fully decrypted.

Tor anonymously transmits encrypted data across three layers of international proxies that make up the Tor circuit. Let’s take a closer look at the three layers of network nodes:

        1. Entry/Guard node: First, Tor Browser randomly connects to a publicly known entry node. The entry node introduces your data into the Tor circuit.
        
        2. Middle nodes: Here your data is fully encrypted. Then it’s sent through a series of nodes which decrypt your data one layer at a time. To ensure anonymity, each middle node knows only the identity of            the preceding and the subsequent middle nodes.
        
        3. Exit node: Once the last layer of encryption is peeled off, the decrypted data leaves the Tor network via an exit node and reaches its final server destination.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/8a1ba5cb-df1c-4372-b1b3-2bcb91b3b8bb)

Sounds complicated, right? That’s because it is. But fortunately knowing how to use Tor Browser doesn’t require a PhD in computer science — it’s surprisingly easy and user-friendly.

### Does Tor Browser hide your IP and how?

Tor Browser employs onion routing technology to effectively conceal users' IP addresses from network surveillance and traffic analysis. This process involves relaying data through numerous network nodes to hide both location and identity. The multi-layered encryption used in onion routing enhances privacy protection. With over 7,000 independent network relays involved, Tor-encrypted data undergoes an elaborate "peeling" process before reaching its destination, ensuring the complete obscurity of its origin. This level of security makes Tor highly effective at protecting data and hiding IP addresses from websites, internet service providers (ISPs), and governmental entities.

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/b7c7defa-3f39-4766-b493-333e334c0a25)

### Is Tor Browser anonymous?

Tor Browser is anonymous in terms of hiding your location and browsing activity — but there are limits. Although they can’t see your browsing activity or Tor encrypted data, your ISP can still see that you’re using Tor. You can also be identified if you log in to an online account or provide details to a website while using Tor.

## Reference
        1. Avast Academy. The Dark Web Browser: What Is Tor, Is It Safe, and How to Use It Link: https://www.avast.com/c-tor-dark-web-                        
        browser#:~:text=The%20Tor%20Browser%20hides%20your,to%20protect%20their%20privacy%20online. 

## What kind of the threat models could TOR fit?

**Disclaimer!!** I tried to conduct a research on this but no success. There are those I was able to read but then I could not really understand it well. So I checked CHATGPT (someone advice). Here is what Chat GPT has to say about the question. 

Tor is designed to address specific threat models related to online privacy and anonymity. It is well-suited for users facing threats from various forms of surveillance, censorship, and identity exposure. Here are some threat models for which Tor can be a valuable tool:

Censorship and Surveillance:

        Threat Model: Users facing censorship or surveillance by authoritarian regimes or organizations.
        How Tor Helps: Tor enables users to bypass censorship and access information freely by routing traffic through a series of nodes, obscuring their identity and preventing direct 
        surveillance.

Privacy from ISPs:

        Threat Model: Users concerned about their internet service providers (ISPs) monitoring and logging their online activities.
        How Tor Helps: Tor encrypts the user's traffic and routes it through a network of nodes, preventing ISPs from easily tracking and analyzing their online behavior.

Whistleblowers and Journalists:

        Threat Model: Individuals sharing sensitive information or reporting on issues where revealing their identity could have serious consequences.
        How Tor Helps: Tor provides a means for whistleblowers and journalists to communicate and access information without revealing their identity or location, protecting them from             potential retaliation.

Anonymous Browsing:

        Threat Model: Users wanting to browse the internet without leaving a trace of their online activities.
        How Tor Helps: Tor helps users achieve a higher level of anonymity by concealing their IP address and making it challenging for websites to track and identify them.

Research and Activism:

        Threat Model: Researchers, activists, or individuals working on sensitive projects who need to protect their identity and communications.
        How Tor Helps: Tor offers a layer of protection for individuals engaged in research or activism by anonymizing their online presence and communications.

Protection from Traffic Analysis:

        Threat Model: Users concerned about adversaries analyzing their network traffic patterns to deduce sensitive information.
        How Tor Helps: The use of onion routing in Tor obscures traffic patterns, making it difficult for adversaries to perform effective traffic analysis and compromise user privacy.

## Reference: ChatGPT
