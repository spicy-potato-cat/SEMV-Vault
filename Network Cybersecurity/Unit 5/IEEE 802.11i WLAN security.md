2 characteristics of a wired LAN that are not inherent in a wireless LAN.
1. In order to transmit over a wired LAN, a station must be physically connected to the LAN. On the other hand, with a wireless LAN, any station within radio range of the other devices on the LAN can transmit. In a sense, ***there is a form of authentication with a wired LAN*** in that it requires some positive and presumably observable action to connect a station to a wired LAN.
2. Similarly, in order to receive a transmission from a station that is part of a wired LAN, the receiving station also must be attached to the wired LAN. On the other hand, with a wireless LAN, any station within radio range can receive. Thus, a ***wired LAN provides a degree of privacy***, limiting reception of data to stations connected to the LAN.

For privacy, IEEE 802.11 defined the [[Wired Equivalent Privacy (WEP)]] algorithm. WEP is now considered outdated and insecure due to its cryptographic weaknesses.
In order to accelerate the introduction of strong security into WLANs, the WIFI Alliance created WIFI Protected Access (WPA)


The final form of IEEE 802.11i is known as Robust Security Network (RSN) or WPA2

### IEEE 802.11i Services

1. Authentication: A protocol is used to define an exchange between the a user and an AS (Authentication Server) that provides mutual authentication and generates temporary keys that is used to authenticate user and AP over the wireless network.
2. Access Control: This function enforces the use of authentication services, routes the message properly, and facilitates key exchange.
3. Privacy with message integrity: MAC level data are encrypted along with a message integrity code that ensures that the data has not been altered.
   
### IEEE 802.11i Operations 

The operation of IEEE 802.11i RSN operation can be broken down into 5 distinct phases.

1. Phase 1 - Discovery
2. Phase 2 - Authentication
3. Phase 3 - Key Management
4. Phase 4 - Protected Data Transfer
5. Phase 5 - Connection Termination

#### Discovery Phase
#### Discovery Phase
- The client (supplicant) scans for available wireless networks.- Access Points (APs) advertise their capabilities, including support for Robust Security Network (RSN).
- The client selects an AP and initiates association based on RSN parameters.
#### Authentication Phase
- The client and AP perform mutual authentication to establish trust.- Typically uses IEEE 802.1X with an authentication server (e.g., RADIUS).
- Ensures that only authorized users gain access to the network.
#### Key Management Phase 
- After authentication, cryptographic keys are generated and distributed.- The [[4-Way Handshake]] protocol derives the Pairwise Transient Key (PTK) from the Master Session Key (MSK).
- Group keys (GTK) are also distributed for broadcast/multicast traffic
#### Transfer Phase
- Data is transmitted securely using encryption and integrity protection.- Commonly employs AES-CCMP (Counter Mode with Cipher Block Chaining Message Authentication Code Protocol).
- Protects against eavesdropping and tampering during communication.
#### Termination Phase
- Connection is gracefully closed when the client disconnects or moves out of range.- Keys are discarded to prevent reuse or compromise.
- Ensures proper cleanup of session state for security hygiene.