# Summary of articles

## Hutchins et al 2011: Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains

•	According to the article, as long as global computer networks have existed, so have malicious users’ intent on exploiting vulnerabilities. Early evolutions of threats to computer networks involved self-propagating code. Advancements over time in anti-virus technology significantly reduced this automated risk. This sentiment I totally agree with since I remember the first time I bought my personal computer, the first thing that I wanted to learn was how to secure all the information I am saving on my desktop as well as everything that I do in the internet (transactions, personal information among others). 

•	Furthermore, as the article mentioned, most organizations have relied on the technologies and processes implemented to mitigate risks associated with automated viruses and worms which do not sufficiently address focused, manually operated APT intrusions. This, I might say, is not only applicable with APT intrusions, in my previous company, we take security as a very serious matter. Mitigations are in place to ensure that we protect the data that we have and resources working for the company is continuously trained to spot security breaches. 

•	Conventional incident response methods fail to mitigate the risk posed by APTs because they make two flawed assumptions: response should happen after the point of compromise, and the compromise was the result of a fixable flaw (Mitropoulos et al., 2006; National Institute of Standards and Technology, 2008) the author of the article added. As technology evolves everyday so as the method to infiltrate or attack our security defenses, so IT resources or people working securities should always be ready and up to date with the current trends hence the need to continuously learn is eminent. I usually suggest, from experience of working on risk management, that we should always question our actions or defenses against threats everyday. We should always ask “Am I putting enough effort or is my defenses up to date?” which I believe is not just applicable to online threats but can also be applied to our daily life. 

•	In June and July 2005, the U.K. National Infrastructure Security Co-ordination Centre (UK-NISCC) and the U.S. Computer Emergency Response Team (US-CERT) issued technical alert bulletins describing targeted, socially-engineered emails dropping trojans to exfiltrate sensitive information. This content from the author caught my attention since I am able to relate this to our previous topic which was discussed in Helsec and we have this also at Accenture which was my previous company. We should always have an eye for abnormalities in emails that we read. We should not fall to the trap of attackers so as not to compromise the information that we hold on. I am a firm believer that more than money, information is always a reason for this kind of actions or attacks. 

•	In February 2010, iSec Partners noted that current approaches such as anti-virus and patching are not sufficient, end users are directly targeted, and threat actors are after sensitive intellectual property (Stamos, 2010). This is what I was referring to on my previous bullet point, threat actors are not just after money but intellectual property or information. Sometimes if we are not careful and always trustful on the things sent to us, we often just install them at our workstations or personal desktop without validating the authenticity of the software, this makes as an easy target. Our anti-virus and the updates on it is not always sufficient hence the need for us to be have knowledge about threats, be careful and always validate the authenticity of what we download, what we click or what we install. 

•	Adversaries were motivated by a desire to collect sensitive information (U.S.-China Economic and Security Review Commission, 2008, 2009). Finally, a report prepared for the U.S.-China Economic and Security Review Commission, Krekel (2009) profiles an advanced intrusion with extensive detail demonstrating the patience and calculated nature of APT.

•	Advances in infrastructure management tools have enabled best practices of enterprise-wide patching and hardening, reducing the most easily accessible vulnerabilities in networked services. Yet APT actors continually demonstrate the capability to compromise systems by using advanced tools, customized malware, and “zero-day” exploits that anti-virus and patching cannot detect or mitigate. Responses to APT intrusions require an evolution in analysis, process, and technology; it is possible to anticipate and mitigate future intrusions based on knowledge of the threat.

•	Each discrete phase of the intrusion is mapped to courses of action for detection, mitigation and response. The phrase “kill chain” describes the structure of the intrusion, and the corresponding model guides analysis to inform actionable security intelligence.

•	I would agree with the author that the most effective way for defenders to have an advantage or edge against attackers is always to use a intelligence driven response. It is always an edge to think, learn and prepare before we act and not just act. It is imperative that we know more of what we are dealing with before we take actions so that we can prepare and be more proactive rather than reactive.

•	Intelligence-driven computer network defense is a risk management strategy that addresses the threat component of risk, incorporating analysis of adversaries, their capabilities, objectives, doctrine and limitations. This is necessarily a continuous process, leveraging indicators to discover new activity with yet more indicators to leverage. It requires a new understanding of the intrusions themselves, not as singular events, but rather as phased progressions.

•	The effect of intelligence-driven CND is a more resilient security posture. APT actors, by their nature, attempt intrusion after intrusion, adjusting their operations based on the success or failure of each attempt. In a kill chain model, just one mitigation breaks the chain and thwarts the adversary, therefore any repetition by the adversary is a liability that defenders must recognize and leverage. If defenders implement countermeasures faster than adversaries evolve, it raises the costs an adversary must expend to achieve their objectives. This model shows, contrary to conventional wisdom, such aggressors have no inherent advantage over defenders.

•	Indicators or hints or signals are pieces of information that objectively describes an intrusion. It can be atomic (cannot be broken down), computed (derived from data involved in an incident), and behavioral (a collection of computed and atomic indicators). Analysts will reveal indicators through analysis or collaboration, mature these indicators by leveraging them in their tools, and then utilize them when matching activity is discovered.

•	Kill chain is a systematic process to target and engage an adversary to create desired effects. Find adversary targets suitable for engagement; fix their location; track and observe; target with suitable weapon or asset to create desired effects; engage adversary; assess effects (U.S. Department of Defense, 2007). This is an integrated, end-to-end process described as a “chain” because any one deficiency will interrupt the entire process. Essence of an intrusion is that the aggressor must develop a payload to breach a trusted boundary, establish a presence inside a trusted environment, and from that presence, take actions towards their objectives, be they moving laterally inside the environment or violating the confidentiality, integrity, or availability of a system in the environment. The intrusion kill chain is defined as reconnaissance, weaponization, delivery, exploitation, installation, command and control (C2), and actions on objectives. The definition of kill chain from computer network attack (CNA) or computer network espionage (CNE) are; Reconnaissance (identification and selection of targets), Weaponization (a remote access trojan with an exploit into a deliverable payload), Delivery (transmission of the weapon to the targeted environment), Exploitation (triggers intruders’ code), Installation (installation of a remote access trojan or backdoor on the victim system allows the adversary to maintain persistence inside the environment), Command and Control (C2) (compromised hosts must beacon outbound to an Internet controller server to establish a C2 channel) and lastly, Actions on Objectives (data exfiltration which involves collecting, encrypting and extracting information from the victim environment; violations of data integrity or availability are potential objectives, which is done after the first six phases). 

•	Intrusion kill chain becomes a model for actionable intelligence when defenders align enterprise defensive capabilities to the specific processes an adversary undertakes to target that enterprise. Defenders can measure the performance as well as the effectiveness of these actions, and plan investment roadmaps to rectify any capability gaps. Fundamentally, this approach is the essence of intelligence-driven CND: basing security decisions and measurements on a keen understanding of the adversary. A course of action matrix using the actions of detect, deny, disrupt, degrade, deceive, and destroy from DoD information operations (IO) doctrine (U.S. Department of Defense, 2006). Completeness equates to resiliency, which is the defender’s primary goal when faced with persistent adversaries that continually adapt their operations over time. Defenders can generate metrics of this resiliency by measuring the performance and effectiveness of defensive actions against the intruders.

•	Kill chain analysis is a guide for analysts to understand what information is, and may be, available for defensive courses of action. It is a model to analyze the intrusions in a new way. Analysts must still discover many other attributes for each phase to enumerate the maximum set of options for courses of action. Defenders must be able to move their detection and analysis up the kill chain and more importantly to implement courses of actions across the kill chain. In order for an intrusion to be economical, adversaries must re-use tools and infrastructure. Here, we have to take note that as defenders we should be practice being proactive and not reactive. Using the information that we have, experience and knowledge we can predict or create counter measures that will help us be more proactive in anticipating the attackers’ actions. In this way, network defenders use the persistence of adversaries’ intrusions against them to achieve a level of resilience. Synthesis of unsuccessful intrusions. As defenders collect data on adversaries, they will push detection from the latter phases of the kill chain into earlier ones. Detection and prevention at pre-compromise phases also necessitates a response. Defenders must collect as much information on the mitigated intrusion as possible, so that they may synthesize what might have happened should future intrusions circumvent the currently effective protections and detections. Having this thought in mind, defenders should have enough and relevant information to support their analysis in advancing their defenses to earlier stages of intrusion or kill chain. Having more information of what they are up against gives them the edge to catch the intrusion before it can achieve a damage or obtain its goal (information or money). 

•	At a strategic level, analyzing multiple intrusion kill chains over time will identify commonalities and overlapping indicators. Having historical data, defenders are able to link years of attack to current attempts and make the relationship giving them the edge to easily detect, compare and mitigate. The principle goal of campaign analysis is to determine the patterns and behaviors of the intruders, their tactics, techniques, and procedures (TTP), to detect “how” they operate rather than specifically “what” they do. The defender’s objective is less to positively attribute the identity of the intruders than to evaluate their capabilities, doctrine, objectives and limitations; intruder attribution, however, may well be a side product of this level of analysis. I understand the notion that it is important to know who we are up against but it is also equally important, if not more important, to know what we are up against since defending something starts with what are we defending it from. We will not blindly implement security measures since we know what we are dealing with. 

•	Overall, especially after running through the case examples, I can say that preventive measure is always the best approach hence the need for us to know what we are up against. Studying the actions of intruders helps us gain knowledge, insight, experience and expertise to deal with them. 

### Chapter 1 Dive In and Threat Model!

•	Using a model means abstracting away a lot of details to provide a look at a bigger picture, rather than the code itself. It enables us to be prepared or anticipate something before it actually hits us. For practical purposes, it is actually like a disaster preparation. When we know a typhoon is about to hit us, we anticipate the damage and prepare for it to 100% avoid it or minimize the impact. Threat modeling is first and foremost a practical discipline. It is an action that is hard at the first attempt. It is a simple as “practice makes perfect” though in this case it will not be a perfect outcome, still we have to try and practice it for it to get easier and for it to become a daily part of our life. The book Dive In and Threat Model is designed for us to find security flaws that might, the keyword is might, exist in a design hence gives us the opportunity to prepare for it. 

•	The threat model is a direct approach. It helps us address four key questions: What are you building? What can go wrong?, What should you do about those things that can go wrong?, and What should you do about those things that can go wrong?. Beginning this study or journey requires us to start with the basic, which I also learned at work, going back to the white board and layout to manage the bugs. 

•	The activity always starts with knowing what you are building hence the need for us to draw a diagram of what we are trying to do. Having a good visual of what we are working on enables us to find flaws at a high level. It is easy to spot where or which part of the process something might actually go wrong. Let us also add boundaries, as the word itself, it gives as the location as to where stuff and people are allowed to go. Boundaries can be, access levels and other specific privileges we. Remember that as the diagram grow larger so as the complexity of hence the chances of missing a part of it or it becomes more confusing through its labels on the data flows. So one tip the author provided is to number the sequence of the diagram or the flow of data. You should think of threat model diagrams as part of the development process. 

•	Threat modelling is not a rocket science, it is something we learn based on experience. 

•	STRIDE is a mnemonic for things that go wrong in security. It stands for Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege. 

•	Having the tool, it enables us to identify possible threats. When identifying remember key things:
    o	Start with external entities
    o	Never ignore a threat because it's not what you're looking for right now
    o	Focus on feasible threats

•	Knowing the threats is the first part, addressing them is the next one:
    o	Mitigating threats
    o	Eliminating threats
    o	Transferring threats
    o	Accepting the risk
    o	Validate don’t sanitize
    o	Trust the operating system
    o	File bugs

•	Remember that it may not always be complete at first run that is why it is a continuous learning. Take note of:
    o	Checking your work
    o	Checking the model
    o	Updating the diagram as needed (don’t flood with too much information)
    o	Check each threat
    o	Check your tests
    o	Threat modelling your own


----------------------------------------------------------------------------------------------------------------------------------------------------------------

### Create a treath model for imaginary company

Sample Diagram

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/a69ba520-3b97-40a4-b5b2-feefdc68a820)

Using Stride Model below are the identified risks:

STRIDE is a mnemonic for things that go wrong in security. It stands for Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege according to Dive In and Threat Model! Book from Oreilly. 

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/6fd15345-bd98-4310-8245-248095adbf01)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/b71c5ea6-fe80-4a81-9cca-ad59b03051a9)

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/d8e1b7f8-beb4-4e81-a386-20ec7e89494c)

Note:
It's important to conduct a thorough security assessment and implement appropriate security measures to mitigate these threats when deploying RPA in the cloud. Security best practices, regular audits, and strong access controls are essential for maintaining a secure RPA environment in the cloud

Prioritization of the identified risks:

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/4fde97f1-8eb6-49ae-a297-eecfa750d78d)

TTP identification sample:

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/dfdf4fec-6b09-4c3c-bbde-81438946b816)

Actions for the RISK:

![image](https://github.com/LuisObana/MyHomeWork/assets/149092789/ebe85c3d-b5f5-436a-99d4-5db66ba1d5b1)


-------------------------------------------------------------------------------------------------------------------------------------------------------------------

##### Incident Analysis

Security Incident Sample:

“In January 2023, Mailchimp, a prominent platform for email marketing and newsletters, detected an unauthorized user within their infrastructure. They stated that an intruder gained access to one of the tools Mailchimp uses for user account administration and customer support.  The intruder had previously targeted Mailchimp employees and managed to gain their account credentials through social engineering techniques. Afterwards, the malicious actor used the compromised credentials to access data on 133 Mailchimp accounts. Mailchimp claimed that no sensitive information was stolen, but the breach may have disclosed customers’ names and email addresses” [1].

What happened:

According to Zack Whittaker Email marketing and newsletter giant Mailchimp says it was hacked and that dozens of customers’ data was exposed. It’s the second time the company was hacked in the past six months. Worse, this breach appears to be almost identical to a previous incident [2]. The security team of Mailchimp detected an intruder on January 11, 2023, accessing one of its internal tools used by Mailchimp customer support and account administration [1], though no indication was provided as to how long the intrusion lasted. The unauthorized actor conducted a social engineering attack on Mailchimp employees and contractors, and obtained access to select Mailchimp accounts using employee credentials compromised in that attack [3]. Social engineering involves using manipulative techniques, such as phone, email, or text-based methods, to obtain sensitive information like passwords [2]. Subsequently, the hacker leveraged these pilfered employee passwords to infiltrate 133 Mailchimp accounts, leading the company to promptly inform the affected accounts of the breach [2].

Who was impacted and the possible impact?

Among the affected accounts, there is one belonging to the prominent e-commerce platform WooCommerce (Z. Whittaker, 2023). WooCommerce, which builds and maintains popular open-source e-commerce tools for small businesses, relies on Mailchimp for sending emails to its customers. WooCommerce is said to have more than five million customers [2]. WooCommerce informed its customers through a message that it received notification from Mailchimp a day after the incident, indicating that the security breach might have exposed customer names, store website URLs, and email addresses [2]. However, WooCommerce assured its customers that no sensitive data, including customer passwords, had been compromised [2]. According to Mailchimp investigation based on the official statement released by the company, this targeted incident has been limited to 133 Mailchimp accounts. There is no evidence that this compromise affected Intuit systems or customer data beyond these Mailchimp accounts [3]. Another company impacted by the attack was Fantom. Officials at Fantom, a smart contract platform, confirmed they were impacted by the attack and said there was an unauthorized export of audience data on Jan. 10, according to a blog post. Fantom said that Mailchimp was still investigating whether the actor actually downloaded the data [5]. 

What went wrong?

Prior to the recent incident, a similar attack was done to Mailchimp where they said that they already added security measures to ensure the attack will not happen again but since it happened earlier this 2023, it is not clear if the added security measures were properly implemented or if it failed [2]. Another angle that was looked at, according to David Jones a journalist from Cybersecurity Dive on his article, a certain Ant Allan VP analyst at Gartner, blamed the repeated attacks on an over reliance on passwords as the sole authentication method. He further elaborated that “Stolen credentials are the major cause of data breaches,” Allan said via email. “MFA is no longer a best practice approach; it is a minimum good practice [5].” Social media engineering attack seems to be the main cause of the intrusion. It serves as the entry point of the attacker to the environment of Mailchimp. 

Historical incident:

The same incident happened to Mailchimp the year before to a different customer, last August, Mailchimp said it was the victim of a social engineering attack that compromised credentials of its customer support staff, granting the intruder access to Mailchimp’s internal tools [2] In that breach, data on some 214 Mailchimp accounts were compromised, mostly of cryptocurrency and finance-related accounts [2]. Cloud giant DigitalOcean confirmed that its account was compromised in the incident, and harshly criticized Mailchimp’s handling of the breach[2]. 

What they did to resolve the incident?

The previous incident, according to the blog, was resolved via implementation of additional set of enhanced security measures but declined to further elaborate the measures set [2]. After the incident was isolated and the evidence was identified of the intrusion, according to the official statement from Mailchimp they temporarily suspended account access for Mailchimp accounts where we detected suspicious activity to protect our users’ data. We notified the primary contacts for all affected accounts on January 12, less than 24 hours after initial discovery [3] and on the same day sent an email to the customers on how to access again their accounts with Mailchimp.

What they implement to secure themselves from hackers?

Though the company Mailchimp never revealed the actions they took to prevent the attack from happening again, here are ways to strengthen security measures from Indusface:
    •	Multi-Factor Authentication (MFA)
    •	Continuously Monitor Critical System
    •	Utilize Next-Gen cloud-based WAF
    •	Verify Email Sender’s Identity
    •	Identify your critical assets which attract criminals
    •	Check for SSL Certificate
    •	Penetration Testing
    •	Check and Update your Security Patches
    •	Enable Spam Filter
    •	Pay Attention to Your Digital Footprint
    
From Kaspersky, they noted some ways to prevent Social Engineering Hacking
    •	Check the source
    •	What do they know
    •	Break the loop
    •	Ask for ID
    •	Use a good spam filter
    •	Is this realistic
    •	Don’t go to fast
    •	Secure your devices
    •	Think about your digital footprint

What could be done, if not yet implemented?

According to According to Patrick Wragg, cyber-incident response manager at Integrity360, the hack is a reminder that social engineering attacks can be very effective, and it is important for companies to have proper security protocols in place and for employees to be aware of these types of attacks [4]. "Seeing as phishing emails are still the most successful initial access vector for breaches, the compromise of a company that bases its business around email marketing is bad," Wragg told Infosecurity in an email. Employees are your first line of defense against a cyber-attack, and education and awareness are still critical in tackling even basic phishing emails [4].

Personal Note:

Overall, it’s not really the most robust measure that we need to implement. Sometimes we are looking at it in a different perspective. Like we try to install the best software for security there could ever be which costs millions of dollars but then we fail to educate our people on the simple cyber security threats done through email (something to ponder on). 

###### References

1.	Top 10 Best-Known Cybersecurity Incidents and What to Learn from Them, Ekran Link: https://www.ekransystem.com/en/blog/top-10-cyber-security-breaches#:~:text=Top%2010%20Best-Known%20Cybersecurity%20Incidents%20and%20What%20to,Prevent%20devastating%20cybersecurity%20incidents%20with%20Ekran%20System%20 
2.	Zack Whittaker , Mailchimp says it was hacked — again (January 18, 2023) Link: https://techcrunch.com/2023/01/18/mailchimp-hacked/?guccounter=1  
3.	Mailchimp Information About a Recent Mailchimp Security Incident January 13, 2023 Link: https://mailchimp.com/newsroom/january-2023-security-incident/ 
4.	Infosecurity Magazine Mailchimp Hit By Another Data Breach Following Employee Hack Alessandro Mascellino (January 19, 2023) Link: https://www.infosecurity-magazine.com/news/mailchimp-hit-another-data-breach/#:~:text=Employees%20are%20your%20first%20line,separate%20hack%20in%20April%202022. 
5.	Cybersecurity Dive Mailchimp hit by second cyberattack in 6 months, 133 customers impacted David Jones (January 19, 2023) Link: https://www.cybersecuritydive.com/news/mailchimp-cyberattack-breach-social-engineering/640743/ 
6.	Vinugayathri Chinnasamy 10 Ways Businesses Can Prevent Social Engineering Attacks (September 24, 2020) Link: https://www.indusface.com/blog/10-ways-businesses-can-prevent-social-engineering-attacks/ 
7.	Kaspersky Ways to avoid social engineering attacks  Link: https://www.kaspersky.com/resource-center/threats/how-to-avoid-social-engineering-attacks 

-----------------------------------------------------------------------------------------------------------------------------------------------------------------
###### Step by Step process on Debian Installation
Note:
Environment OS: Debian 64 bit
Host OS: Windows 11 version 22H2 (OS Build 22621.2428)
Hardware: Processor 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz   2.42 GHz and RAM: 8.00 GB
Version of Oracle Virtual Box Used: VirtualBox 6.1

1.	Search the Download Debian ISO image and the Virtual Box to be installed
2.	Downloaded the Debian ISO image and the Virtual Box
3.	Installed the virtual box “VirtualBox 7.0.12 platform packages” while waiting for Debian ISO image to be downloaded
4.	Created a virtual machine and follow the instructions given
a.	Because the background image was different, I uninstalled “VirtualBox 7.0.12 platform packages” and search for “VirtualBox 6.1.48 (released October 17 2023)” then install it
5.	Then I created a new machine following the instruction given
6.	Following the instruction on selecting ISO Image, I inserted the image that was downloaded “Debian ISO image”
7.	When I first booted the desktop, I got confused with the loader hence I thought I made a mistake but then I went back to the instruction and noticed that it was the same. So I waited for the actual VM to load up
8.	I followed the testing instruction and it was successful though there a prompt regarding the usage of mouse
9.	I also noticed that when navigating the VM and the actual laptop, there was a delay on response hence I have to pause working on my report and just focus on the instruction
10.	I have created a user account and followed the instruction provided as well as choosing the strong password
11.	I did not encounter the black screen issue hence I have skipped that one
12.	I restarted and log in back again
13.	I tested the emulator for the installation of firewall and enablement as well as for all updates. 
