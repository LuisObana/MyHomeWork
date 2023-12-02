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
