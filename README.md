    In this article, we’ll discuss the tools you’ll use everyday as a SOC analyst, common security definitions, MITRE ATT&CK framework, Cyber Kill Chain model, Incident Response, and Zero Trust.

Imagine badging into the front door of your office building and saying hello to the guard that you see everyday, wondering what you will get him for Christmas. You leave your badge at home more often than you should, so you’ve chit chatted a bit as he gets you a temporary badge. You know he has a little boy, and he really likes hot wheels. You think about this as you tell him to have a nice day, and you approach the elevator to go to your floor. You badge the elevator to get to your floor, because your floor is locked unless you are approved to get in. Then you get off the elevator at your destination and walk more toward the center of the floor where the SOC sits, and you badge one more door to get to the common areas, because you have access to this area, and this is where the sales and engineering teams sit in their cubicles. As you approach the center of the room where the SOC is, there are two security doors within a few feet from each other. This is called a mantrap and it allows security to trap someone in between the two doors for them to be escorted out of the building if they are not allowed to be there. You swipe your badge at the first door, and then briefly you get a little anxious if the locks broke or your badge suddenly didn’t work. You’d be trapped in the mantrap in some kind of horror experiment. You try your badge again and make it through the second door to the heart of security: the Security Operations Center! It is dark and there are windows, but there are blinds covering all of the windows. It is eerie because the only time the blinds seem to be opened are to let the window cleaners clean the windows. You look above your head around you, and you instantly are brought to the front lines as the TVs that line the ceiling are displaying what is going on in your global company, and in the world in real time. You are sucked into your role, and you say hello to your friends and then jump into action.

    Note

    This was an actual SOC for a Managed Security Services Provider that we worked for. They would periodically bring clients in to show them how serious they took security. It sometimes felt like being watched like fish in a tank, but it made me feel pride in what I was doing.

SIEM

The number one tool you will need to know as a security analyst in this decade is what a Security Incident and Event Management (SIEM) tool is and how it plays into your role. The SIEM is the heartbeat of the SOC. Everything that is done on a device can generate a log. Without logs there would not be a security analyst. Without logs there would not be security. When devices from all around the world generate logs, the idea is to send it to a single point where all of the logs can be observed and measured. This concept is called a “single pane of glass” and is ideally the one screen that the SOC can operate without having to chain multiple web browsers and sites together to accomplish the review of security events. The single pane of glass is the SIEM.

Other than collecting logs, the SIEM also normalizes logs, which means to put them into the correct chronological order. Because of the varying time zones across the world configured in your devices, the timestamps, or date and time, on each log need to be accounted for. Also in normalization, when the logs are ingested into the SIEM platform, they must meet a certain standard and format.

Each SIEM has a “special sauce” or proprietary technique that is used to take in billions of logs and pick out the things that are suspicious, but at a basic level, either the vendor or the users (or both) create rules that if any of the logs match a given criteria, it will sound the alarm. Next-generation SIEM platforms perform User Entity and Behavior Analytics (UEBA) which attempts to monitor all of your user generated logs and create a baseline of activity that is considered normal and then sound the alarm when someone is acting outside of their normal behavior.

Also in next-generation SIEM platforms, they are moving toward being a case manager as well. When there are multiple alarms that are seemingly related, they offer a way to combine them and track evidence and investigations in a way that is meaningful and easy to be used.

Lastly in next-generation SIEM platforms, they are moving toward integrated automation. Security Orchestration, Automation, and Response (SOAR) is rapidly gaining traction in the industry and is poised to be the next “single pane of glass.”
Firewalls

In addition to SIEM and SOAR, you will likely come across firewalls. Firewall and firewall engineering is a specialty all on its own, but it’s important to understand the biggest players in the firewall space are Cisco, Checkpoint, Fortinet, Palo Alto, Juniper, and SonicWall. As a security analyst, you might be responsible for performing a firewall block on an IP address, or requesting to have it done. What this means is you have used the tools and techniques of a security analyst and determined that it was bad, and you want to block that IP address from being communicated with from your internal network.
IDS/IPS

You will also need to know what an intrusion prevention system (IPS) and an intrusion detection system (IDS) is. A “protection” system allows actions to be taken by the device as the events happen. A “detection” system only allows for it to be detected, and not to interject with actions. Most intrusion prevention systems can act as intrusion detection systems and vice versa, and the main difference is where it is put on the network. Figure 5–1 is a basic illustration of two computers communicating and how the IDS would fit in, just monitoring passively.
Figure 5–1 Intrusion Detection System

Intrusion detection systems can either be placed “in-line” or through a network tap, the network tap as seen in Figure 5–1. Tapping the network allows the device to see the network traffic but not affect bandwidth. Intrusion detection systems placed through a tap cannot take preventative action because they cannot control the flow of traffic.

Figure 5–2 depicts two computers communicating and how an intrusion prevention system would fit into the network in an “active” scenario. The intrusion prevention system has the ability to change the flow of traffic between the two devices because of the way it sits in-line on the network.
Figure 5–2 Intrusion Protection System

Intrusion prevention systems must be placed as seen in Figure 5–2. Most modern intrusion prevention systems will have some rules set to “take action” and some set to monitor only. These are called intrusion detection and prevention systems (IDPS).
Sandboxing

Another tool you may come across is a sandbox. When you hear someone say, “Did you sandbox that?”, what they mean is have you executed the file or website in a protected environment to find out what it does. Quite a few endpoint detection softwares will detonate the file on your behalf so it can know whether it is bad or not, but nothing comes as close as a good report from Hybrid Analysis, or Joe Sandbox. These tools are designed to twist every knob and press every button to squeeze as much execution information as they can out of it. As a SOC analyst, you mainly use these tools to get out indicators of compromise like hashes of files that it drops, or IP addresses and domains it contacts to run these through your SIEM to see if there are any historical connections.
Terminology

As you go through your day as a SOC analyst, you will come across terms that aren’t always agreed on, and the meanings are a bit vague. From the best of our combined experience, these are the best definitions for these terms. Figure 5–3 is a chart of the order of volume from each class.
Figure 5–3 Volume Funnel Chart
Security Logs: Most Common

At the very base of a security program are security logs. These logs could be from anything and everything and about anything and everything. Once they are ingested into a SIEM, they become a security log. An example of important security logs that a SOC would want to capture are network flow logs, Windows Event Logs, Unix Syslogs, and firewall logs. Security events can string together many security logs.
Security Event: Common

Security events are the day-to-day routine security monitoring from the tooling. They are very common, and almost all security tooling notifications start as a security event generated from security logs, with the exception of vulnerability scanners, and are escalated as needed. A security event must be escalated to a security incident before becoming a breach. When a security event is escalated to become an incident, the incident response process triggers, and an incident handler is assigned.
Incident: Uncommon

Security incidents are uncommon but happen more frequently than a security breach. An incident is declared, and the incident response process starts if there is suspected loss of sensitive data.

What is not an incident: security events and vulnerabilities that have not been escalated.
Security Breaches: Rare

Security breaches are rare and contain a verified loss of data containing sensitive personal information. In most cases to utter the words something is a breach, it requires the legal department and the CISO to declare a breach. As a new analyst, it is good practice to not use this term anywhere unless told otherwise. In most cases, breaches require a breach notification to clients and sometimes the public and are handled with extra sensitivity.

All breaches start as incidents.
The Incident Response Process

As an analyst, you’ll typically be dealing with security events that you’ll be seeing through to closure, however, sometimes security events become larger than what the SOC typically deals with, requiring the Incident Response Plan (IRP) to be executed and the dedicated Incident Response Team (IRT) to take over the investigation. It is important for you to understand the incident response process.

The incident response process is a structured approach businesses develop to manage and mitigate the impact of security breaches. This critical process aims to minimize damage, reduce recovery time and costs, and prevent future incidents. By following a well-defined response plan, organizations can quickly address vulnerabilities, assess the extent of breaches, and implement effective countermeasures. This proactive and reactive strategy is essential in maintaining information assets’ integrity, confidentiality, and availability in today’s increasingly complex and evolving cyber threat landscape.

The National Institute of Standards and Technology (NIST) Incident Response Lifecycle is a common and widely recognized standard. It’s broken down into 4 phases: Preparation, Detection and Analysis, Containment, Eradication and Recovery, and Post-Incident Activity.
Figure 5–4 Incident Response Process

Preparation is the first and most impactful phase of the incident response lifecycle. This is where the groundwork for how an organization responds to a security breach is developed. Training and awareness programs are defined for the incident responders and the larger organization. By preparing for incidents before they happen, companies build resilience against cyber threats. This proactive approach means that the impact on operations, reputation, and finances can be minimized when incidents occur.

Detection and Analysis is where the SOC is focusing their efforts. It’s important to remember that early detection is critical, the sooner a security incident is detected, the more effectively it can be contained and remeditated. Having a detailed and comprehensive Incident Response Plan will also aid in developing rapid response capabilities. The plan should clearly specify how to prioritize security incidents, escalation procedures, and who to report confirmed security incidents to in the organization’s leadership.

Containment, Eradication, and Recovery begin once a security incident is declared. The first objective of this phase is to accurately identify the method of compromise and actions taken by the attacker post-compromise. A plan to “stop the bleeding” can be developed from there. This is how containment is achieved. Next, actions are taken to eradicate the access gained by the attacker. This could include removing an end-point infected with ransomware from the network, resetting compromised passwords, or adding a network block to the firewalls. The actions taken here vary incident by incident and require critical thinking to ensure nothing is missed.

Finally, a recovery plan is developed and executed. This usually involves identifying the initial method of compromise and plugging the hole to ensure it doesn’t happen again. For example, if a web server was compromised using SQL injection, the developer would be tasked with remediating the SQL injection vulnerability from the website. Recovery is considered complete once all affected systems, networks, and user accounts are returned to their operational state before the incident. Implementing new security detections for the SOC to monitor post-incidents is also essential. You can move into the final phase only after extensive testing of the latest security controls and detections.

Post-Incident Activity is when an analysis of the response process is conducted to identify any opportunities for improvement. This is where the After Action Review (AAR) would be conducted for the veterans out there. Usually, the Incident Commander/Manager will meet with everyone involved in the incident to talk through the steps taken, identify what worked and what needs improvement, and develop a report for executive leadership. This step might result in updates to the Incident Response Plan, strengthening security measures, or filling previously unknown security gaps with tooling or detections. Finally comes knowledge sharing. Many organizations are members of cybersecurity working groups. One example is the Defense Industrial Base (DIB) hosted by the Department of Defense. DIBnet is a secure portal for companies who are members of DIB to share incident reports, indicators of compromise, and lessons learned with one another to strengthen the entire community through collaboration.
MITRE ATT&CK Framework

Tactics, Techniques and Procedures (TTPs) describes three components in a process used to develop threats and plan cyberattacks. Tactics represent the “why” of an attack technique and the reason for performing an action. Techniques represent “how” an adversary achieves a tactical goal by performing an action. Procedures are the specific implementation the adversary uses for techniques.

    Note

    Tactics, Techniques and Procedures (TTPs) is a common industry term that you should know.

Developed by the MITRE Corporation, the ATT&CK framework is a knowledge base that describes cyber adversary tactics, techniques, and procedures based on real-world observations. It is most commonly used at a management level in metrics to categorize attacks seen in an organization to know where to make improvements to the security posture. It is also important for an analyst to be familiar with it so that you know how to categorize things when you need to. But you need not have to memorize everything, it’s there on the website for you to.
Figure 5–4 The ATT&CK for Enterprise Matrix

It’s OK if you’re not able to read figure 5–4 but that’s what it looks like if you visit the website. The key components of the MITRE ATT&CK framework are:

Tactics: High-level objectives or goals that adversaries seek to achieve during an attack. Examples include Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Exfiltration, and Impact. These are at the top of Figure 5–3.
Figure 5–5 MITRE ATT&CK Tactics

Techniques: Specific methods or approaches that adversaries use to accomplish a particular tactic. Techniques are more detailed and granular than tactics. For example, within the “Execution” tactic, there might be techniques like Command-Line Interface, Scripting, or Exploitation of Remote Services.
Figure 5–6 Mitre ATT&CK Techniques

Procedures: Specific instances or examples of how adversaries implement techniques in a real-world scenario. These are inside of each technique.
Figure 5–7 MITRE ATT&CK Procedures

Mitigations: Inside each technique are recommendations and best practices to defend against or minimize the impact of specific techniques.

Groups: Inside each technique are adversarial groups or threat actors that have been identified by researchers, along with information about their tactics, techniques, and procedures.

Software: Inside each technique is specific malware, tools, or software associated with adversary activity.

The MITRE ATT&CK framework is widely used in the cybersecurity community for threat intelligence, red teaming, blue teaming, and incident response.
Cyber Kill Chain

Another model like the MITRE ATT&CK framework that is used for mapping adversaries and developing countermeasures is the Cyber Kill Chain. The Cyber Kill Chain is a concept that describes the stages an adversary typically goes through to successfully execute a cyber attack. It was initially introduced by defense contractor Lockheed Martin and has since become a widely adopted framework in the field of cybersecurity. The Cyber Kill Chain helps organizations understand and analyze the various phases of a cyber attack, allowing them to implement effective defense mechanisms at each stage.

The traditional Cyber Kill Chain consists of the following stages:
Figure 5–8 Stages for Cyber Kill Chain

Reconnaissance: The attacker gathers information about the target, such as identifying potential vulnerabilities, employee names, and network architecture. This can involve both passive (e.g., online research) and active (e.g., scanning for open ports) methods.

Weaponization: The attacker creates or acquires a weapon, typically in the form of malware or a malicious payload, designed to exploit a specific vulnerability.

Delivery: The attacker delivers the weapon to the target environment. This could occur through various means, such as email attachments, malicious links, or exploiting software vulnerabilities.

Exploitation: The weapon is executed, taking advantage of vulnerabilities in the target system to achieve its malicious objectives. This stage often involves gaining unauthorized access or control over the targeted systems.

Installation: The attacker establishes a persistent presence in the target environment by installing additional tools, backdoors, or malware. This allows them to maintain access and control over the compromised system.

Command and Control (C2): The attacker establishes communication channels with the compromised system to remotely control and manage the attack. This can involve receiving instructions, exfiltrating data, or delivering additional payloads.

Actions on Objectives: The attacker achieves their ultimate goal, which could include data theft, system disruption, or other malicious activities. This stage may vary depending on the attacker’s motives, such as financial gain, espionage, or activism.

Not all attacks follow these stages in a fixed order, and defenders can disrupt the chain at various points to prevent or mitigate the impact of an attack. Understanding the Cyber Kill Chain is valuable because although the MITRE framework is more common, the Cyber Kill Chain is still referred to in some places and conceptually the kill chain can be easier to digest than the MITRE framework. Just know that it is another model like the MITRE ATT&CK framework to map attackers to help with countermeasures.
OWASP Top 10

OWASP stands for Open Wordwide Application Security Project. More commonly known as Open Web Application Security Project, it is a nonprofit foundation that works to improve the security of software. They have over 250 chapters that meet all over the world in person and it is likely they have one near you. You should consider attending sometime as it’s a great way to network with people.

OWASP publishes a Top 10 report which describes the top 10 web application security risks. It’s important for you to have familiarity with these risks. I have been asked in interviews before to describe Cross-Site Scripting (XSS) or SQL-Injection (SQLi). OWASP Top 10 skills are difficult to learn and it is not best taught through a book but best through hands-on practice. I would recommend that you check out TryHackMe’s OWASP Top 10 labs.

TryHackMe is both a free and subscription online platform that teaches cybersecurity through short, gamified real-world labs. If you’re new to TryHackMe, I recommend signing up for a free account and going over the platform to understand how the rooms/labs work. They have a discord chat but I would recommend skipping it. It’s over moderated and can distract you from your progress. TryHackMe is a great platform and I don’t want one overzealous chat moderator to ruin your experience with the company.
Zero Trust

Zero Trust is a security approach where you don’t automatically trust anyone or anything, whether they’re inside or outside your network. Instead of assuming everything is safe once inside, you constantly check and verify things like user identity, device health, and the context of the situation before allowing access to sensitive data. These are the basic principles of Zero Trust:

Verify Identity: Always check and make sure that people, devices, or systems are who or what they claim to be before letting them access important data.

Least Privilege Access: Only give people or things the minimum access they need to get their job done. Don’t give them more than necessary.

Micro-Segmentation: Divide your network into smaller parts and control how things communicate between them. This way, if one part is in trouble, it won’t affect everything else.

Continuous Monitoring: Keep an eye on what people and things are doing. If something seems weird or not right, check it out and take action.

Contextual Access Control: Decide who gets access based on the context, like where they are, what time it is, and how important the data is that they want.

Encryption: Make sure that information is protected by encrypting it, making it unreadable to anyone who shouldn’t see it.

Dynamic Policy Enforcement: Always be ready to adjust your security rules based on what’s happening. Stay flexible and adapt to new threats or situations.

These principles form the foundation of the Zero Trust model. It is quickly being adopted everywhere because your data is now everywhere. There isn’t a defined perimeter of most corporate networks anymore like there was in the past. The only way to defend authorized access to your data is to keep a closer eye on who accesses what and when, and we do this by implementing the Zero Trust model.
Zero Trust: NEVER trust, ALWAYS verify.
Summary

When you start your new job on day one, it will help you tremendously if you even have heard of some of these technologies, concepts, and methodologies, not to mention how much it will help you to understand them during the interview process. As I stated, the SIEM is the most important tool today to know as a SOC analyst. In the future, more single panes of glass are going to be driven by SOAR platforms, but they will likely be a combined product — A SIEM/SOAR product as a single pane of glass.
