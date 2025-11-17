A firewall maybe a computer system or a software service that is running on an existing router or server.


Firewalls can be classified based on
- Processing modes
- development era
- structure

## Processing Modes
Depends on how it processes the traffic to block traffic

![600](https://i.sstatic.net/RVAeW.png)
### Packet Filtering
**Method** : Examines the
- header information of a packet.
- Source IP
- Destination
- Protocol
**Installed on** : TCP / IP based Network
**Functions on** : Network Layer ( OSI Model ) / IP Layer ( TCP IP )

A vague look at the packets:
![[Pasted image 20251110132348.png| 600]]


#### Types of Packet Filtering FW
There are **3 types**.
- Static Packet Filtering
	- Requires Rules to be developed and installed with the firewall
	- Any changes are to be done by human intervention
	- Common Easy to setup
	- Static allow entire set of one type of packets to enter in response to authorized reuests

- Dynamic Packet Filtering
	- Can react to new emerging situations and update and create rules to deal with the event itself.
	- Drops all packets from a particular address when a lot of them are *Malformed*.
	- Dynamic Packet filtering allows only a particular packet along with a particular source destination.

- Stateful Packet Inspection: 
	- Keeps track of each connection between internal and external system using a **state table**.
	- State table includes
		- Which : Station has sent the packet
		- What : Content of the packet
		- When : Time
	- Instead of checking an ACL I will check our history of receiving packets.
	- Additional Compute required to check the state table.
	- Without checks Vulnerable to DOS Atttack

---
### Application Layer Proxy Firewall
- Method : Receives requests from the external network and acts on behalf of internal network. (Proxy Server)
- Installed on : Dedicated Computer.
- Functions On : Application Layer ( Layer 7 in OSI model )
- **Limitations** : 
	- Cannot check encrypted traffic
	- Restricted to a single application.
- **Benefits:**
	- Can cache frequent requests making service faster.

---
### Media Access Control ( MAC ) Layer Firewall 
- Method : Filters based on MAC ID and NIC ID ( Network Interface Card ).
- Installed On : Specific Host Computer.
- Functions On : Media access control *SubLayer* of Network Datalink Layer ( Layer 2 OSI ) 
- Used commonly to deny some devices access to LAN or some features.

---


## Structure / Architecture
Configuration depends on three factors
- Objectives
- Organizations Ability
- Implementations
- Budget

### Types of Structured Based Firewalls
- Single Bastion Hosts
- Screen Host Firewalls
- Screen Subnet firewalls
- Dual Homed Firewall

### Single Bastion Host
Any system/router/firewall that is exposed to the untrusted network can be called bastion host (AKA Sacrificial Host). 

Implementation : 
- Uses
	- NAT : Network Address Translation
	- PAT : Port Address Translation

Characterstics:
- Single Protection Device on the network perimeter
	- Commonly used in Residential Soho Environments
	- Single Office Home Office

A **dual homed host** usually has a bastion host with two network interface. One for internal and one for external.

Limitations:
- Lacks defence in dept
- Complicated to implement ACL

---
### Screen Host Architecture
Method : Combines Packet Filtering and application proxy server.
Architecture : Packet filtering router is the method to deny or allow request. Proxy Server is the bastion. 
Benefits : Caching of frequently accessed pages

### Screened Subnet Architecture With DMZ
Dominant architecture in todays network. Basically a [[#Screen Host Architecture| Screened Host Architecture]] with a DMZ. 

Basically the webserver or the front endpoints are going to be exposed to the users. The DMZ sits between two firewalls and the internal network sits after the internal firewall. 
Refer Diagram





## Eras/ Generationon
- Generations
	- First Generation : Static Filtering 
	- Second Generation : Application Firewall
	- Third Generation : Stateful Inspection
	- Fourth Generation : Dynamic packet filtering
	- Fifth Generation : Kernel Proxies. Windows NT.
- These stacks are session dependent, which means that they are constructed on-the-fly when a new session request arrives at the firewall.

## Best Practices for Firewall
- All traffic from internal/trusted is allowed out. Allows member of the organization to access the services they need. Filtering and logging of outbound traffic can be implemented.
- The firewall device is never directly accessible from the public network for configuration or management purposes.
- Administrative access to firewall is denied to internal network as well. ( Excluding ADMINS & Preferably )
- SMTP Data is allowed to enter through the firewall but is routed to a well configured SMTP Gateway to filter phishing etc.
- ICMP Data should be denied on external interfaces. Example ping services. ICMP is a common method for hacker reconnaissance and should be turned off to prevent snooping.
- Telnet access Outwards to Inwards should be blocked from all Public Net
- Telnet Access to DNS should be blocked to prevent zone transfers


**Dictionary Attacks**

- **Method:** Trial-and-error using a list of potential passwords.
- **Off-line Attack:** Attacker knows the complementation function ($f$) and the stored complementary information ($C$'s), repeatedly trying different guesses ($g$) until the password is guessed.
    - _Examples:_ `crack`, `john-the-ripper`.
- **On-line Attack:** Attacker accesses the authentication functions ($L$) and tries guesses ($g$) until one succeeds.
    - _Example:_ Trying to log in by guessing a password.

### Andersons

The components of Anderson's formula are defined as follows:

- **P:** The **probability** of guessing a password in a specified period of time.
- **G:** The **number of guesses tested in 1 time unit**.
- **T:** The **number of time units**.
- **N:** The **number of possible passwords**. $N$ is also equal to $|A|^s$, where $A$ is the set of strings making up passwords, and $s$ is the length of the password.
- The relationship is expressed as: **$P \geq TG/N$**.

This formula is typically applied in the context of analyzing the minimum required password length to resist dictionary or brute-force attacks over a given period.

For instance, an example using this formula seeks to find the minimum password length ($s$) needed if:

1. Passwords are drawn from a 96-character alphabet (implying the size of the set $A$ is 96).
2. The system can test $10^4$ guesses per second ($G = 10^4$).
3. The probability of success ($P$) is set to 0.5 over a 365-day period ($T = 365 \times 24 \times 60 \times 60$ seconds).

The solution calculates $N \geq TG/P = (365 \times 24 \times 60 \times 60) \times 10^4 / 0.5 \approx 6.31 \times 10^{11}$. By then choosing the length ($s$) such that the sum of possible passwords ($\Sigma_{j=0}^{s} 96^j$) is greater than or equal to $N$, the result suggests that passwords must be at least 6 characters long ($s \geq 6$).