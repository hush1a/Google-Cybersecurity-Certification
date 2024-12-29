# Cybersecurity incident Report 

## Scenario:
You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. 
The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 
One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, 
but you receive a connection timeout error message in your browser. You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number 
of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to 
respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. You take the server offline temporarily so that the machine 
can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. 
You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem 
quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.




## The Report
`Section 1`: Identify the type of attack that may have caused this 
network interruption

One potential explanation for the website's connection timeout error message is: the type of attack that may have caused the error in the website’s connection is a DoS attack, mainly in the form of a SYN flood.

The logs show that: There are a lot of packets being sent, using the TCP protocol, and then the HTTP protocol once the connection to the web server is established. The packets are sent to port 443 of the web server. The first few SYN attempts are responded by the server, but the user keeps sending more requests to the web server and after a while, the server could not respond to the abnormal amount of SYN requests

`Section 2`: Explain how the attack is causing the website to malfunction

When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. Explain the three steps of the handshake:
1. First, the user sends a SYN request to connect to the web page hosted on the web server.

2. Then, the server will return an ACK response that acknowledges the user request to connect to the web server, agreeing the connection.

3. Finally, the server will redirect the user to the website using the HTTP protocol.

What happens when a malicious actor sends a large number of SYN packets all at once: The server is able to respond to a few requests, but when there are too many of them, the server fails to respond to the requests and will malfunction.

What the logs indicate and how that affects the server: There are too many SYN requests coming from an employee’s computer, and that causes the server to not respond and struggle.

