# Domain 4 - Communication and Network Security

### OSI Model

* Application (PDU)
* Presentation (PDU)
* Session (PDU)
* Transport (TCP / UDP)
* Network (Packet)
* Data Link (Frame)
* Physical (Bits)

---

* Carrier-Sense Multiple Access (CSMA)
* Carrier-Sense Multiple Access (CSMA/CA)
* Carrier-Sense Multiple Access (CSMA/CD)

----

### TCP/IP

* 3-Way-Handshake (SYN / SYN-ACK / ACK)
* Header is 20 - 60 bytes long
  * 16 bit Source Port
  * 16 bit Destination Port
  * 32 bit Sequence Number
  * 4 bit Data Offset
  * 4 bit Reserved
  * 8 bit Flags
  * 16 bit Window Size
  * 16 bit Checksum
  * 16 bit Urgent pointer
  * Variable (multiple of 32bit)

#### IP Classes

##### IPv4

* Class A / B / D (multicast) / E (reserved)

#### DNS

* FQDN consists of:
  * top-level-domain
  * registered domain name
  * subdomain or hostname
* Attacks 
  * DNS Poisoning
  * Alter the HOSTS file
  * Corrupt the IP configuration
  * USe proxy falsification
  * Domain hijacking

### Wireless Networks

* SSID , BSSID, ESSID
* Attacks
  * War Driving
  * War Chalking
  * Replay
  * IV
  * Rogue Access Points
  * Evil Twin

##### Frequencies

* Frequency Hopping Spread Spectrum
* Direct Sequence Spread Spectrum
* Orthogonal Frequency-Division Multiplexing



## Network Authentication Protocols

### PAP
- Client sends packet with cred (username and password) at the beginning of connection
- Plain Text

### CHAP
- protected against replay-attacks by incrementally changing identifier and variable challenge-value
- requires both sides know plain-text shared secret
- Used by PPP
- Stores plain-text passwords

### 802.1X (EAP) 
- supplicant, authenticator, and authentication server
- AS is RADIUS or AD
  
#### PEAP	
- EAP with TLS Tunnel
  
#### EAP-MD5
- weak form of EAP.
  
#### LEAP

#### EAP-TLS
- Uses PKI, requires client and server certificates
- Establishes a tunnel for authentication very secure, complex and expensive
  
#### EAP-TTLS
- Simpler by dropping the client certificate requirement, allowing other methods for client authentication

#### PANA
- devices authenticates itself by using EAP as protocol for key distribution, key agreement and key derivation.

### Secure Network Components

#### Firewalls

* Application-Layer Gateway Firewall
  * also proxy firewall
  * affect network performance
* Circuit-Level Gateway Firewall
  * operate at Session layer (Layer 5)
  * SOCKS is a common implementation
* Stateful Inspection Firewalls
  * evaluate the state or context of the traffic
  * operate on layer-3 and layer-4
* Deep Packet Inspection Firewalls
  *  
* Next-Gen Firewalls
  * Multifunction Device
  * Integrates Firewall, IDS, IPS, TLS Proxy, web filtering, QoS, NATing, VPN and antivirus.



