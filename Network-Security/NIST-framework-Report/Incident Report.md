# Applying the NIST framework for a Report ❗

This is the final activity in the *`Connect and Protect: Networks and Network Security`* Course. In this activity, I created an incident report using the knowledge I’ve gained about networks throughout this course to analyze a network incident. I used the National Institute of Standards and Technology's Cybersecurity Framework (NIST CSF). The CSF is a voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk.

## Scenario:

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack.

## The Incident Report Analysis:

[Google Docs Report Link](https://docs.google.com/document/d/18tSxze3bEGa7qiQUKUEai_5DbU4NFZFoArlCKOZTc0g/edit?usp=sharing)

1. `Summary`
   
The organization’s network recently experienced a DDoS attack which compromised the internal network for 2 hours and normal internal network traffic could not access any network resources. The attack was caused by an incoming flood of ICMP packets. After the cybersecurity team’s investigation, it was discovered that a malicious hacker had sent the ICMP flood through a vulnerability which is an unconfigured firewall. The team responded by blocking the attack and stopping all non-critical network services.

2. `Identify`

From the threat, the affected systems were the internal network. And the attack was a form of DDoS attack, which is an ICMP flood. The impact of the attack was that the network and servers stopped responding to requests and traffic could not be accessed. 

3. `Protect`

The team has implemented new implementations to prevent further attacks, such as a new firewall rule to limit the rate of incoming ICMP packets, Source IP address verification to check for spoofed IP addresses on incoming ICMP packets, Network monitoring software to detect abnormal traffic patterns, and an IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics
  
4. `Detect`

To detect more attacks in the future, the firewall in the network should be configured and regulated to make sure that it continuously monitors network traffic on network devices to check for suspicious activity, such as incoming external ICMP packets from non-trusted IP addresses attempting to pass through the organization’s network firewall.

5. `Respond`

The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

6. `Recover`

The team will need to recover the network services to come back online and restored to a functioning state. 
