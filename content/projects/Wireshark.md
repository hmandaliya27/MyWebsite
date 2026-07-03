---
title: "Network Traffic Analysis with Wireshark"
description: "Monitor, capture, and analyse network packets efficiently"
draft: false
dateString: April 2025
showToc: true
weight: 303
cover:
    image: "projects/wireshark/wiresharkcover.jpg"
--- 


# Overview
This project demonstrates practical use of Wireshark to inspect and interpret network traffic across several protocols — focusing on authentication flows and clear-text vulnerabilities. By capturing traffic such as RADIUS, HTTP Basic Authentication, HTTP Form-Based Authentication, and DNS queries, the project highlights critical areas where encryption is essential to maintain security and user privacy.

# Generating and Capturing RADIUS Traffic
This stage involved simulating RADIUS authentication traffic and analysing the captured packets to understand the underlying protocol and associated risks.

### Setup and Capture
Wireshark was launched with monitoring configured on the active network interface (Ethernet or Wi-Fi). A RADIUS client tool such as NTRadPing was used to send authentication requests to a RADIUS server, generating live traffic for analysis.

![](/projects/wireshark/radius1.jpg)

### Packet Analysis
Wireshark captured authentication exchanges, including Access-Request, Access-Accept, and Access-Reject packets. Fields such as User-Name and Reply-Message were examined to map the authentication process, including successful and failed attempts.

![](/projects/wireshark/radius2.jpg)


### Decrypting with Shared Secrets
To analyse encrypted password attributes, the RADIUS **shared secret** was added in Wireshark via **Preferences → Protocols → RADIUS**. This enabled decryption of obscured password fields, demonstrating how authentication data is obfuscated using the shared secret.

![](/projects/wireshark/radius3.jpg)

### Security Insight
Although RADIUS conceals passwords, the rest of the packet remains **unencrypted**. This exposes metadata and makes the protocol vulnerable to interception, highlighting the need for securing RADIUS communication using tunnelling protocols such as IPSec or RADSEC.

![](/projects/wireshark/radius4.jpg)

# Analysing HTTP Basic Authentication
This section focused on observing how HTTP Basic Authentication operates and identifying associated security flaws through packet capture.

### Traffic Generation
A test website requiring Basic Authentication was accessed via a browser. Upon login, the credentials were entered in the pop-up prompt, initiating an HTTP Authorization header exchange.

![](/projects/wireshark/http1.jpg)

### Packet Observation
Wireshark was filtered to capture traffic on **port 80** (default for HTTP). The HTTP request and response headers were reviewed, revealing the Authorization: Basic header containing credentials encoded in **Base64**.

![](/projects/wireshark/http2.jpg)

### Security Reflection
Base64 encoding is not encryption; it simply masks the credentials, which can be easily decoded. Because HTTP is inherently unencrypted, anyone with access to the network could retrieve and decode the username and password. This underscores the need to use **HTTPS** to secure authentication and session data.

# Inspecting HTTP Form-Based Authentication and DNS Traffic
The final segment examined a more common web authentication method form-based login  as well as the behaviour of DNS lookups over the network.

>Form-Based Authentication

### Testing Process
A login form was accessed on a test web application. Dummy credentials were entered (e.g., admin / 12345) and submitted to simulate user login.

![](/projects/wireshark/dns1.jpg)

### Traffic Review
Wireshark captured the outgoing POST request containing the submitted form data. The payload included the credentials in plaintext, as the website was served over HTTP rather than HTTPS.

![](/projects/wireshark/dns2.jpg)

### Security Implications
This method of login, without encryption, is extremely vulnerable to eavesdropping. The credentials were visible in clear text in the HTTP body. This highlights that without HTTPS, even modern form-based authentication mechanisms remain insecure.


# Conclusion
This project illustrates how powerful Wireshark is as a diagnostic and security auditing tool by exposing vulnerabilities in common network protocols. Through hands-on analysis of RADIUS, HTTP Basic, and form-based authentication traffic, along with DNS queries, it becomes evident that without encryption, credentials and user data are easily intercepted. The findings reinforce the need for secure network configurations, including the use of HTTPS, VPNs, and encrypted authentication mechanisms such as RADSEC. Proper implementation of these practices is essential to protect user privacy and maintain the integrity of digital communications.






