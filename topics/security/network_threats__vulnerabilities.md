# Common Network Threats and Vulnerabilities

## Overview
Understanding the landscape of network threats and vulnerabilities is crucial for securing IT systems. This section explores common types of network attacks, weaknesses that attackers exploit, and their relevance to networking and Linux environments. By identifying these risks, learners can better prepare to protect networks using tools and techniques covered in other sections.

## Topics

### Types of Threats
- **Distributed Denial of Service (DDoS)**: Overwhelms a network or server with traffic to disrupt availability (e.g., flooding a web server, impacting the Availability principle of the CIA triad).
- **Man-in-the-Middle (MITM)**: Intercepts communication between devices to steal data or manipulate traffic (e.g., intercepting unencrypted HTTP traffic, linking to Protocols: The Language of Networks).
- **Phishing**: Tricks users into revealing sensitive information through fraudulent emails or websites.
- **Malware**: Includes viruses, ransomware, and spyware that compromise network devices and data.
- Connection to Linux: Malware can target Linux systems if not properly secured (e.g., outdated packages, covered in Linux Package Management).

### Common Vulnerabilities
- **Misconfigurations**: Incorrectly configured firewalls, open ports, or default settings (e.g., leaving port 22 open for SSH without restrictions, referencing Ports and Network Communication).
- **Unpatched Systems**: Failure to update software leaves systems exposed to known exploits (linking to Best Practices for Network Security).
- **Weak Passwords**: Easily guessable credentials increase the risk of unauthorized access.
- **Unsecured Protocols**: Using outdated or unencrypted protocols like Telnet instead of SSH (referencing Protocols: The Language of Networks).

### Attack Vectors
- **Exploiting Open Ports**: Attackers scan for open ports (e.g., using Nmap, covered in Networking Tools and Troubleshooting) to gain unauthorized access.
- **Protocol Weaknesses**: Exploiting flaws in protocols like DNS (e.g., DNS spoofing) or TCP (e.g., session hijacking, linking to Understanding TCP and UDP).
- **Social Engineering**: Manipulating users to bypass technical controls (e.g., tricking an admin into running a malicious Linux command, referencing Linux Commands).
- **Insider Threats**: Employees or trusted users misusing access to harm the network.

### Case Studies of Notable Attacks
- **Example 1**: The 2017 WannaCry ransomware attack exploited unpatched Windows systems, spreading across networks and highlighting the need for timely updates (relevant to Linux Package Management for Linux systems).
- **Example 2**: A 2021 MITM attack on a corporate network used ARP spoofing to intercept sensitive data, emphasizing the importance of securing network communication (referencing Encryption and Secure Communication).
- These cases demonstrate real-world impacts of threats and vulnerabilities, motivating proactive defense strategies.

## Purpose
This section equips learners with the knowledge to identify and understand common network threats and vulnerabilities. By recognizing attack vectors and their consequences, learners can apply practical skills from other sections (e.g., configuring firewalls, monitoring traffic with tools like Wireshark, or securing Linux systems) to mitigate risks and strengthen network security.
