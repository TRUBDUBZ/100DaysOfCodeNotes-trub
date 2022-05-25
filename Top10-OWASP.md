# [OWASP Top 10](https://www.youtube.com/watch?v=3Zxuhwct9uk&ab_channel=Nahamsec)

##  1. Broken Access Control
	
	- shouldn’t be able to see any private info about employees within an enterprise
	- being able to access data that doesn’t belong to your user/user group
	- fuzz api with brute force/ tampering with JSON web token

##   2. Cryptographic Failures
	
	- errors and vulnerabilities within cyphers

##   3. Injections 
	
	- SQL injection
	- XSS cross site scripting
	- anything that allows you to execute code on the host server/address
	- only on the server nothing that the users are hiding 
	- XSS scripting with a phishing attack does allow you to target users

##   4. Insecure Design
	
	- popular category focused on flaws in design logic
	- loop holes, tricks, anything that uses the design of website to use for your own purposes
	- changing the price of items would count here
	- very common vulnerabilities
	- ask yourself what is the function and can you bend it to your use
	- cost the company money resources, or anything that effects day to day ops

##   5. Security Misconfiguration
	
	- leaving flaws/vulnerabilities that leave unintended security holes
	- it’s possible to add a user with admin credentials vs brute forcing someones password
	- leaving any files that expose your private data

##   6. Vulnerable & Outdate Concepts
 	
	- hackers finding applications that have known vulnerabilities and leveraging them to exploit and gain access.
	- can automate a lot of the work involved for this, vulnerability scanning, recon, info gathering

##   7. Identification & Authentication Failures
	
	- most common is when an attacker obtains working credentials
	- first way is brute forcing the password
	- second way is “credential stuffing”
	  - relies on a previously known about breach 
	- session fixations, exposing web tokens, allowing to use previous cookies

##   8. Software & Data Integrity Failures

	- beware of GitHub repos that allow any people to push code to 
	- verify updates
	- want to understand how the target deploys code 
	- tamper with CIC pipeline
	- find a way to upload malicious code to a target

##   9.  Security Logging & Monitor Failures

	- not an actual attack but the capability for a company to find and locate malicious activity
	- monitoring traffic 
	- seeing the attack, detecting and preparing, and ultimately defending

##   10. Server Side Request Forgery SSRF

	- SSRF is having access to a computer within a network of a target
	- using the specific target can only be accessed within the targets infrastructure
	- could be web services, could be local files, could be api, could be cloud infrastructure
	- allows attacker to interact with target and pull credentials, info, data that is meant to be hidden within vulnerable network
	- SSRFs are very common, important one to know
	
