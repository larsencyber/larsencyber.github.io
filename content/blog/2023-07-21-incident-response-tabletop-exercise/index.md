---
title: Bolstering Your Incident Response Capability Using Tabletop Exercises
summary: This is a written version of the presentation I completed at AISA Cyber Conference Melbourne in October 2022, and AISA Cyber Conference Canberra in March 2023. 
date: 2023-07-21
authors:
  - admin
tags:
  - incident response
  - conference presentation
  - tabletop exercise
image:
  caption: 'Image credit: Australian Cyber Conference 2023 Canberra'
---
## Context
This is a written version of the presentation I completed at AISA Cyber Conference Melbourne in October 2022, and AISA Cyber Conference Canberra in March 2023. 

## Agenda
Everyone has rehearsed procedures for real emergencies before, whether that's first aid training or fire drills. Cyber security incidents are no exception. Your company may have extensive strategies in place, but if your team lacks experience, they will struggle to stay organised when a real crisis occurs. To improve your organisation's incident response capability, this presentation presents a method for planning, structuring and running tabletop exercises. 
![](/blog/2023-07-21-incident-response-tabletop-exercise/img1.png)

To begin this presentation, I'll talk more about my own background. Next we will go through the things you should have in place before conducting an exercise. Then we will go through scenario development, structuring the exercises, running the simulation on the day, and post-exercise improvements.

## About Me
![](/blog/2023-07-21-incident-response-tabletop-exercise/img2.png)

My name is Jacob Larsen and I work at CyberCX as a manager in GRC. This slide has information about my formal education and training. However, what you should really know is that I am passionate about making a real difference. I thrive when helping organisations make a shift in their security operating model. That is, a shift from being reactive, driven by audits, and the tick-box style of cyber security management, to proactive threat and risk-based control implementation. As such, this presentation not only exceeds compliance obligations, but focuses on developing a robust incident response capability. Now let's jump into the prerequisites before running incident response exercises. 

## Exercise Pre-Requisites
![](/blog/2023-07-21-incident-response-tabletop-exercise/img3.png)

The one "must have" is a Cyber Security Incident Response Plan. This plan will guide your team when responding to an incident. There are a variety of components which are important to include in the plan:

**Defined Roles and Responsibilities**
* Who provides the strategic direction?
* Who leads the effort of the incident response team?
* Who is responsible for escalation to executives?

**Initial Preparation Activities**
* These completed activities provide context of what the current state is when an incident occurs.
* The last thing we want to be doing is identifying what are our assets are, or what our attack surface is, whilst responding to the incident.

**Detection and Analysis Capabilities**
* Define the detection technologies that provides the alerts.
* The incident raising process, for example internal employees raising issues.
* Defined incident categories.
* An incident assessment criteria is one of the most important things. This includes a matrix for incident level, impact, action required, and which role handles communication.

**Containment, Eradication and Recovery Processes**
* This gives an understanding of how the incident response team is activated and the role it plays.
* It should also include description for each incident type alongside a standard initial response.
* For example, there might be a standard response for phishing, or signs of advanced persistence.
* Incident escalation criteria between tactical, operational and strategic teams.

**Post-Incident Improvements**
* The incident response process must operate on a continually improving model.
* This is achieved by lessons learned, improvement metrics and corrective actions.

Now let's jump into the scenario development of incident response exercises.

## Scenario Development
![](/blog/2023-07-21-incident-response-tabletop-exercise/img4.png)

To develop the incident response scenario, there are a few questions we must answer.

First, what type of incident will occur?
* Let's consider the Confidentiality, Integrity and Availability triad
* Is it a breach of confidentiality, such as unauthorised exposure?
* Is it a loss of integrity?
* Or is there disruption to the availability of an asset?

Second, what assets are involved?
* Assets can be data, processes, software, hardware, networks, site, organisations and even people.

Third, what is the attack chain?
* How was initial access obtained or persistence achieved?
* Was there privilege escalation and lateral movement?
* What was the final impact of the attack chain?

Fourth, what is the threat?
* Is an adversary involved, such as organised crime or a malicious insider?
* Is it accidental, has someone accidentally made a misconfiguration?
* Is it structural, has hardware reached resource depletion and failed?
* Is it environmental, such as a natural disaster?

Finally, which stakeholders will be involved in the exercise?
* Which parts of the organisations are we wanting to test response processes with?
* Is it tactical or operational teams such as engineers?
* Or is it more strategic leaders such as executives?

![](/blog/2023-07-21-incident-response-tabletop-exercise/img5.png)

To answer these questions and begin developing a scenario, we need to derive context from our organisation.

First we can conduct crown jewel analysis on our assets. We can do this by creating an information asset inventory and reviewing each asset against the CIA triad.
* Which asset, if it had unauthorised exposure, would cause brand and reputation issues? For example, a customer database. 
* Which asset must have no inaccuracies in terms of integrity? For example, the infrastructure controlling the temperature of a kiln in a refinery.
* Which asset must have absolute availability, implying recovery is virtually instantaneous? For example, critical infrastructure of a gas pipeline connecting to a residential area.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img6.png)

Second, we need to review our risk assessment findings.
* Is there a repeating theme of causes for our risks in our risk registers?
* Is there any particular risk scenario in the register which if it did occur would have a catastrophic impact? Even if the likelihood is rare or unlikely.
* Is there any relevant findings from recent penetration tests we can use to build an attack chain?

![](/blog/2023-07-21-incident-response-tabletop-exercise/img7.png)

Third, and most importantly, reviewing cyber threat intelligence to understand what is actually occurring in the threat landscape. 
* Is there any historical evidence of threat groups attacking organisations in our sector?
* Can we observe techniques, tools or procedures that were used? For example, we know that the Lazarus Group has been observed targeting financial institutions using spear phishing as a method for initial compromise. 

Finally, once our scenario is developed, we need to validate that it is practical with a technical stakeholder in the organisation who is not participating in the exercise.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img8.png)

Now for the sake of this presentation, we will create a mock company profile that has been breached. This company is called "Fintech.AU" and offers financial products to it's customers. Hypothetically, we have completed the following:
* Conducted threat intelligence and found that in our sector, similar organisations have been targeted for data breaches and extortion.
* Reviewed our assets, and found that a file server was likely used to facilitate compromise, with a workstation being used as a point of entry, and a shared RDP server as a point of privilege escalation. 
* Reviewed our previous penetration tests and identified a feasible attack chain, which will be discussed in detail in later slides.
* Given the size of our organisation and operating in the financial services sector, it is likely we would be targeted by adversaries in organised crime.
* Finally, given the widespread impact of the attack when responding to the incident, we will involve both operational and strategic stakeholders in the tabletop exercise.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img9.png)

Now that we have developed our scenario, we need to consider how we will structure the tabletop exercise on the day. When a real incident occurs, we don't have a full understanding of the incident timeline straight away. We typically only have awareness, of the final step and impact of the attack chain. 

So for example in this scenario, we are only aware that the final exfiltration of sensitive files has occurred. As time progresses, we discover more information, by reviewing logs and collecting forensic evidence. This allows us to build a timeline of events. So when we conduct our incident response exercise, we must reverse the attack timeline to create a realistic simulation. 

In this attack chain, the following steps occur:
1. An adversary performs a password spray attack and compromises a staff member's Microsoft365 account.
2. This Microsoft 365 account is used to gain a legitimate remote access connection to virtual desktop infrastructure. This is possible as Active Directory authentication can be used for the VPN connection.
3. The adversary discovers they are able to access a shared RDP server running Windows Server 2008 R2.
4. This is vulnerable to CVE-2019-1388, which allows them to bypass Windows user access controls and privilege escalate to SYSTEM.
5. With SYSTEM access, they deploy a cobalt strike implant to maintain persistence.
6. Using the obtained privileged access, they dump operating system credentials and discover a local administrator password hash.
7. As no Windows LAPS (Local Account Password Solution) is in place, the adversary is able to perform a local admin password hash spray against the environment, and discovers a local admin hash has been re-used on a file server.
8. The adversary laterally moves to file servers and ex filtrates sensitive files.

There are logs, alerts and detections which exist at each step of this attack chain which can be used in our tabletop exercise.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img10.png)

To simulate a real incident we must reverse the incident timeline. We can do this by drip feeding context through information injections over the session.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img11.png)

This slide provides a visual representation of how the incident response simulation occurs on the day. As discussed earlier, the organiser will slowly drip feed information injections to give context of the incident to participants. As an organiser, it is also important to keep note of the following:
* When providing context, the organsier must not answer questions related to the information injections. Think about it, when in a real incident, do the security analysts get the opportunity to ask the threat actor what is going on?
* Also, the scenario cannot be moved to further injections until the team reaches a resolution in terms of actions or decisions.

Now using the scenario developed earlier, let's run an incident response exercise ourselves.

## Incident Response Tabletop Exercise
![](/blog/2023-07-21-incident-response-tabletop-exercise/img12.png)

**Initial Brief**

To set the scene, a system administrator performs routine checks in the Microsoft Azure Security Centre and notices alerts for sign-ins from IP addresses related to suspicious activity.

This is the only information which is provided to participants. At this point, participants are left to coordinate with themselves and discover how they would respond given the initial brief.

As an organiser, we can use the following questions in the orange box on the slide to observe and take notes on how our participants respond. We wouldn't share this information with participants on the slide in real time. 
* Q1 - Participants can't rely purely on memory on how to respond, they must use a plan to determine next steps.
* Q2 - A step in the plan is performing an impact assessment. This will analyse the impact, and determine what the initial response should be.
* Q3 - Incident tracking allows us to be organised and coordinated in our response. This could be in an ITSM tool for tracking.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img13.png)

**Information Injection #1**

The first information injection confirms to the team that a real security incident has occurred. The CEO receives an extortion email demanding the business pays a ransom of 50 Bitcoins. If the ransom is not paid, the entire customer database has been threatened to be leaked to the public. The email also contains a sample of the stolen data.
* Q1 - At this point, we need to observer if the participants have escalated the incident to the appropriate level of authority as per the plan. Is the CISO involved? This is no longer just a tactical response.
* Q2 - Has the Incident Response Team (IRT) formed according to the cyber security incident response plan? This establishes the roles and responsibilities to ensure an organised response.
* Q3 - Has the IRT engaged the legal and public relations team? This is important to consider, to ensure there is transparency to customers and shareholders.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img14.png)

**Information Injection #2**

Next, the incident response team matches the sample data from the extortion email with a customer database which is stored on a Windows Server 2019 file server. After reviewing the windows event logs, it is confirmed that a security administrator account was compromised to exfiltrate 15GB of sensitive files.

At this point, participants should start connecting the information injections to build context of the incident timeline. This should make the actionable steps required to respond much clearer. 
* Q1 - Next the organiser will need to observe if the team is taking appropriate measures to contain the compromise. For example, this could include disabling accounts and resetting passwords.
* Q2 - Next the organiser will need to observer what investigative techniques are being used to discover how the file server was compromised. For example, event log reviews and network traffic analysis.
* Q3 - Finally, observer what actions the legal and public relations teams are taking to inform customers of the breach. The response is not just technical, but must also consider internal and external communication. There will now be two response teams, one investigating the incident, and one handling customer communication.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img15.png)

**Information Injection #3**

Usually between the second and third information injection, the organiser should encourage participants to take a 10 minute break. Being a participant in these types of sessions can be quite draining and fasted paced, with a lot of condensed information in a short time frame. As the organiser, you still want long term buy-in from participants to conduct more tabletop exercises in the future.

The third information injection reveals the incident response team discovered a Windows Defender for Endpoint alert of suspicious access to the LSASS service on a shared RDP server. Now participants should have a strong understanding of the incident timeline. The LSASS service is likely dumped to obtain credentials stored in the operating system.

Therefore, actions to contain, eradicate and recover from the incident should be clear.

![](/blog/2023-07-21-incident-response-tabletop-exercise/img16.png)

**Information Injection #4**

The fourth information injection will allow participant to have a strong understanding of the incident timeline.

The incident response team have discovered a Cobalt Strike implant in a temporary folder on a shared RDP server. This gives a strong indication to participants of where the threat actor performs action remotely and maintains persistence from.
* Q1 - It is important to observe how participant take steps to eliminate the threat's persistence from the environment.
* Q2 - Another interesting question is to observe if participants would plan to investigate any closed alerts as false positives that might be related to the incident. 

![](/blog/2023-07-21-incident-response-tabletop-exercise/img17.png)

**Scenario Debrief**

Finally before the tabletop exercise can be completed, the organiser should reveal to participants the full scenario. For example, in our scenario, the initial brief provided context that a M365 account had been compromised. Then the first injection provided context by confirming an incident had occurred, through the extortion email mentioning exfiltration of sensitive files. The second injection provided weak context of the incident timeline, confirming a file server had been compromised. The third information injection provided fair context, confirming lateral movement through the shared RDP server. The fourth information injection provided strong context, confirming persistence occurred through the Cobalt Strike implant.

At this point, the tabletop exercise is concluded and the organiser can commence the evaluation.

## Evaluation
![](/blog/2023-07-21-incident-response-tabletop-exercise/img18.png)

The evaluation section is the most important component of running the incident response simulation. This is where the organiser will examine how participants engaged in the scenario. Questions to ask include:
* Q1 - Was knowledge of internal processes demonstrated? For example, incident tracking tools.
* Q2 - Was the Cyber Security Incident Response Plan even used? I have performed exercises previously where at the final information injection, someone asked "don't we have a plan for how to respond?". 
* Q3 - Were roles and responsibilities clear? What was the role of each person involved? Was it clear? How were other teams involved, for example legal or public relations?
* Q4 - Was there strong communication between operational and strategic teams?
* Q5 - Did any stakeholders demonstrate leadership? It is important to highlight in the final evaluation report any strong leaders for recognition.
* Q6 - Was feedback captured from all participants? Feedback must be captured from all who participated on the structure of the exercise and scenario for future improvement.

## Post-Exercise Improvement
![](/blog/2023-07-21-incident-response-tabletop-exercise/img19.png)

Finally, there will be action post-exercise to improve the organisation's incident response capability. These primarily focus on the domains of people, process and technology.
* People: improvements include leadership training, communication, roles and responsibilities, and decision criteria.
* Process: improvements include updating the CSIRP, developing playbooks, or creating an incident reporting process.
* Technology: improvements could include improving detection technologies to cover suspected blind spots, new use cases for log correlation, and updating asset inventories.

## Conclusion
![](/blog/2023-07-21-incident-response-tabletop-exercise/img20.png)

In summary, we have discussed:
1. The content required to have in a Cyber Security Incident Response Plan.
2. How to create an incident response scenario specific to your organisation.
3. How to simulate an incident on the day with information injections.
4. How to integrate improvements into your incident response capability post-exercise. 