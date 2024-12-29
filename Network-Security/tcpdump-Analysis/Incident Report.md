# Security Incident Report

## Scenario:

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A former employee has decided to lure users to a fake website with malware. 

The former employee/ hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After embedding the malware, the hacker changed the password to the administrative account. When customers download the file, they are redirected to a fake version of the website that contains the malware. 

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack. 

## The Report 

`Section 1`: Identify the network protocol involved in the incident.

The network protocol involved in the incident is the HTTP protocol. because requests to web servers for web pages involve http traffic, the tcpdump traffic log showed the usage of the http protocol when contacting the server. The malicious file is being transported to the users’ computers at the application layer.

`Section 2`: Document the incident

The incident was discovered after the helpdesk received a lot of complaints from customers using the website. When the user wants to connect to the website, the user is prompted to download a malware, advertised as free recipes, and when the user clicks it, they will be redirected to another similar website that contains the malware. If the malware is downloaded, the user’s computer begins to run a lot slower. 

The Cybersecurity team analysed the attack and reported that the web server was impacted by a brute force attack, after using a sandbox environment to open the website and analysing the tcpdump logs. 

`Section 3`: Recommend one remediation for brute force attacks

A recommendation for remediating brute force attacks is to disallow previous passwords from being used. Also making passwords more complex and strong will be beneficial so that malicious attackers in the future will not be able to brute force the account admin in the web server to cause more severe damages.
