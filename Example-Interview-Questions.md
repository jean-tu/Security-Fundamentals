# Example Interview Questions 

## What happens when you type something into a search bar and hit "enter"? 

1. The DNS (Domain Name system) converts the plain text into an IP address 
	* DNS - stores a table between the URL and IP address (kind of like a phonebook)
	* Order: 
		*  Browser Cache 
		*  OS Cache 
		*  Router Cache 
		*  ISP (Internet Service Provider) Cache 
2. If URL is not in cache, then ISP DNS server initiates a DNS query to find the IP address of the server that hosts the website 
3. Browser initiates a TCP connection with the requested website server (3 Way Handshake)
4. After the connection has been established, the browser will send an HTTP request to the web server
5. Server handles the request and sends back a response in the specified format (JSON, XML, HTML) along with a status code 

	*  Response Codes Explained 
		*  1XX - Informational 
		*  2XX - Success 
		*  3XX - Redirect
		*  4XX - Error on Client End 
		*  5XX - Error on Server End 
6. Browser receives the information and displays it

Source [Maneesha Wijesinghe's Medium Article](https://medium.com/@maneesha.wijesinghe1/what-happens-when-you-type-an-url-in-the-browser-and-press-enter-bb0aa2449c1a)

## What is HSTS 

HTTP Strict Transport Security - mechanism that protects websites against protocol downgrade attacks and cookie hijacking. Can enforce web browsers to only use HTTPS connections. 

This is done by using the header `Strict-Transport-Security`. The information that's included along with this header is **max-age** and **includeSubDomains**.

Ex: `Strict-Transport-Security: max-age=31536000 ; includeSubDomains`

Source: [OWASP Secure Headers Project](https://owasp.org/www-project-secure-headers/)

## Encryption and Authentication

* How do cookies work?
	* Cookies are used to track website activity, it acts as your "ID Card" 
	* Small bits of information that a website stores on your computer 
	* Commonly used for online shopping to know what items you've added to your cart, etc.  
	* There are 2 different types: session & non-persistent cookie 
* How do sessions work?
	* Server-side storage information that is desired to be persistent throughout the user's interaction with the website
* Explain how OAuth works. This information is stored with the session id 
	* OAuth is an open-standard auth protocol/framework that provides applications the ability for "secure designated access". Provides authorization tokens to prove an identity between consumers and service providers. Allows you to approve an application interacting with another on your behalf without giving away your password. 
		* Ex: Log in with Google, Apple, Facebook, etc. 
	* There are 3 players: user, consumer, service provider 
		* Consumer = The website that you're trying to log into 
		* Service Provider = Facebook, Google, (the website that you're already authenticated to/have an account for)
* What is a public key infrastructure flow and how would I diagram it?
* Describe the difference between synchronous and asynchronous encryption.
* Describe SSL handshake.
* How does HMAC work?
    * Why HMAC is designed in that way?
* What is the difference between authentication vs authorization name spaces?
* What’s the difference between Diffie-Hellman and RSA?
* How does Kerberos work?
* If you're going to compress and encrypt a file, which do you do first and why?
* What is the difference between encryption and encoding?
* What is the difference between 128 and 256?
* How do I authenticate you and know you sent the message?
* Should you encrypt all data at rest?

## Network Level

* What are common ports involving security, what are the risks and mitigations?
* Which one for DNS?
    * AH
    * ESP
* Describe HTTPs and how it is used.
* What is the difference between HTTPS and SSL?
* How does threat modeling work?
* What is a subnet and how is it useful in security?
* What is subnet mask?
* Explain what traceroute is.
* Draw a network, then expect them to raise an issue and have to figure out where it happened.
* Write out a Cisco ASA firewall configuration on the white board to allow three networks unfiltered access, 12 networks limited access to different resources on different networks, and 8 networks to be blocked altogether.
* Explain TCP/IP concepts.
* What is OSI model?
* How does a router differ from a switch?
* Describe the Risk Management Framework process and a project where you successfully implemented compliance with RMF.
* How does a packet travel between two hosts connected in same network?
* Explain the difference between TCP and UDP. 
    * Which is more secure? 
    * Why?
    * What is the TCP three way handshake?
* What is the difference between IPSEC Phase 1 and Phase 2?
* What are biggest AWS security vulnerabilities?
* How do web certificates for HTTPS work?
* What is the purpose of TLS?
* Is ARP UDP or TCP?
* Explain what information is added to a packet at each stop of the 7 layer OSI model.
* Walk through a whiteboard scenario for your environment of choice (Win/Linux) in which compromising the network is the goal without use of social engineering techniques (phishing for credential harvesting, etc).
* Explain how you would build a web site that could secure communications between a client and a server and allow an authorized user to read the communications securely.
* How does an active directory work?
    * Do you know how Single Sign-On works?
* What is a firewall?
    * How does it work?
    * How does it work in cloud computing?
    * Difference between IPS and IDS?
* How do you build a tool to protect the entire Apple infra?
* How do you harden a system?
* How to you elevate permissions?


## Databases

* How would you secure a Mongo database?
	* Postgres?
* Our DB was stolen/exfiltrated. It was secured with one round of sha256 with a static salt. 
    * What do we do now?
    * Are we at risk?
    * What do we change?
* What are the 6 aggregate functions of SQL?

## Tools and Games

* Have I played CTF?
* How would you decrypt a steganography image? 
* You're given an ip-based phone and asked me to decrypt the message in the phone.
* What CND tools do you knowledge or experience with?
* What is the difference between nmap -ss and nmap -st?
* How would you filter xyz in Wireshark?
* Given a sample packet capture - Identify the protocol, the traffic, and the likelihood of malicious intent.
* If left alone in office with access to a computer, how would you exploit it? 
* How do you fingerprint an iPhone like Uber did so you can monitor it even after wiping it?

## Programming

* Code review a project and look for the vulnerability.
* How would you conduct a security code review?
* How can Github webhooks be used in a malicious way?
* If I hand you a repo of source code to security audit what’s the first few things you would do?
* Can I write a tool that would search our Github repos for secrets, keys, etc.?
    * Slack?
        * https://arstechnica.com/security/2016/04/hacking-slack-accounts-as-easy-as-searching-github/
    * AWS?
    * Etc.

## Compliance

* Explain SOC 2?
	* Auditing procedure that ensures that your service providers security manage your data to protect the interests of your organization and the privacy of its clients 
	* Minimum level of requirement when considering a SaaS provider
* What are the five trust criteria of SOC 2?
	1. Security - system is protected from unauthorized access 
	2. Availability - system is available for operation as determined by SLA 
	3. Processing Integrity - system processing is complete, accurate, timely, and authorized 
	4. Confidentiality - information designated as confidential is protected and committed/agreed 
	5. Privacy - personal information is collected, used, retained, disclosed, and destroyed with the criteria set in Generally Accepted Privacy Principles (GAPP)

* How is ISO27001 different from SOC 2?
	* 	ISO wants you to provide proof that you have an ISMS (Information Security Management System) in place to manage InfoSec Program on an ongoing basis
	*  
* Can you list examples of controls these frameworks require?
* What is the difference between Governance, Risk and Compliance?  
* What does Zero Trust mean?


## Sources 

[Tad Whitaker's List of Questions](https://github.com/tadwhitaker/Security_Engineer_Interview_Questions/blob/master/security-interview-questions)