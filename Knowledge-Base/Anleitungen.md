# Cisco 

## Upgrade eines WLC Clusters im HA Setup

**Complete these steps**

After the WLCs are configured in the HA setup, the Standby WLC cannot be upgraded directly from the TFTP/FTP server.  
Initiate upgrade on the Active WLC in the HA setup via CLI/GUI, and wait for the upgrade to finish.  
Once the Active WLC executes all the upgrade scripts, it will transfer the entire image to the Standby WLC via the Redundant Port.  
When the Standby WLC receives the image from the Active WLC, it will start executing the upgrade scripts. The transfer of the image to standby and the execution of the upgrade scripts on the Standby WLC can be seen on the Active WLC Console/Telnet/SSH/Http connection.  
After a successful message of Standby Upgrade is observed on the Active WLC, it is important to issue the show boot command on the Active WLC in order to make sure the new image is set as the primary image.  
Once verified, initiate primary image pre-download on the Active WLC in order to transfer the new image to all the APs in the network.  
After pre-image is completed on all the APs, issue the show ap image all command in order to verify that the primary image on the WLC is set as the backup image on APs.  
Initiate swap option to interchange the backup image as primary on the APs. With this implementation, the WLC's and AP's primary image is set to the new image.  
Issue the schedule-reset command as per planned outage with the no swap option in order to reset the APs and WLCs so that they can boot with the new image.  
The Standby WLC will reset just one minute before the scheduled reset time to boot and come up first to take over the network with the new image.  
All the APs will reboot and join the new Active WLC, and the previous Active WLC will transition to the standby role.  
Issue the show boot, show sysinfo, show ap image all, and show redundancy summary commands in order to verify that both the WLCs and APs have booted with the new image.  
Important Guidelines before Initiating a WLC Upgrade in HA Setup
Service Upgrade is not supported in this release, so network downtime should be planned before you upgrade the WLCs in the HA setup.  
The peer should be in the Hot Standby state before you start the upgrade in the HA setup.  
It is recommended to reboot both the WLCs almost together after upgrade so that there is no software version mismatch.  
Schedule Reset applies to both the WLCs in the HA setup. The peer WLC reboots one minute before the scheduled timer expiry on the Active WLC.  
The Standby WLC can be rebooted from the Active WLC using the reset peer-system command if a scheduled reset is not planned.  
Debug transfer can be enabled on the Active WLC as well as the Standby WLC.  
If Active WLC unexpectedly reboot between software download and reboot both WLCs, you need to reboot both WLCs in order to complete software upgrade.

Verschiedene Konfigurationen für IP SLA (Cisco IOS)
------------------------------------------------

Generell bei jeglicher IP SLA Konfiguration benötigt man zwei Dinge:

-   Eine Quelle die Anfragen stellt: IP SLA Source
-   Einen Dienst der auf die Anfragen der Source antwortet. (IP SLA Responder bzw. Server)

Um eine Strecke mit VoIP Traffic auf Qualität zu überprüfen, könnte man das Beispielhaft anhand einer Jitter Kontrolle machen. Wie dies grundlegend konfiguriert wird, ergibt sich im folgenden:

### Schritt 1

Zu erst muss sichergestellt werden das irgendetwas auf die entsprechen Anfragen antwortet. Das kann entweder ein echter Server sein, oder - besser weil mehr Statistiken übertragen werden - ein echter IP SLA Responder (zum Beispiel der Router auf der Gegenseite)

### Setup für ip sla responder anhand eines Cisco Routers

Router2# configure terminal  
Router2# (config) ip sla responder  
Router2# (config) ^Z

### Kontrolle mit einem 'show' Befehl

Router2#  show ip sla responder

### Basic Setup für ip sla source

`Router1# ip sla <nummer>  
Router1# udp-jitter x.x.x.x <port> codec g711alaw  
Router1#   frequency <default 60>  
Router1#    #tag  
Router1#    #owner  
Router1#    #tos <nummer>`

### Konfiguration des Schedulers  
`ip sla schedule <nummer> start-time <now|timestamp> life <seconds|forever>  
ip sla schedule 1 start-time now life forever

ip sla statistics <nummer>`

---

# IPSEC - Notes


## ipsec tunnel consists of
- SA (security associations)
   - security algorithms and keys
   - protocol (transport or tunnel)
   - key-management (auto or manual)
   - SA lifetime
 - SPI (security parameter index)
 - Destination - IP
 - Security-Protcol - AH / ESP
 
 
## ipsec modes
### tunnel 
- endpoints: host, firewall, router 
- regular ipsec tunnel
- packet:
  original packet is encapsulated in another IP packet.
  new header is build for the new packet
  new packet and old packet can be authenticated and encrypted
  new header IPs are the endpoint-IPs
  original header IPs are the original IPs
	  
### transport
- endpoints: hosts only 
- l2tp-over-ipsec
- packet:
  original packet is not encapsulated
  original packet can be authenticated and encapsulated
 
## Authentication Header
 - MD5
 - SHA1
 - SHA2
 
## Encapsulating Security Payload
 - DES
 - 3DES
 - AES
 
## Key Management
 - auto IKE (maybe IKEv2)
   PHASE 1: - encryption algorithms (DES or 3DES) and authentication header (MD5...),
              diffie-hellman group (1,2,5,14 (19,20 ECDH)), preshared key
			 - main or aggressive mode
			   dailup has to use aggressivemode and email or FQDN or IP as IKE ID. if dynamic dail up
			   only email or FQDN can be used.
	PHASE 2: - SA negotiation to secure the data
			 - PROXY-ID
 - auto IKE with certificate
 - manual (face-to-face or email)
 
 
PKI (DSA/RSA/ECDSA)
IKE preshared key
VPN manual keys

---

# Create an SAN CSR

## Key erstellen
`openssl genrsa -out priv.key 4096`

## Vorlage erstellen oder Defaults in /etc/pki/tls/openssl.cnf anpassen
### Beispiel
```
cat server_cert.cnf
[req]
distinguished_name = req_distinguished_name
req_extensions = req_ext
prompt = no
[req_distinguished_name]
C   = IN
ST  = Karnataka
L   = Bengaluru
O   = GoLinuxCloud
OU  = R&D
CN  = ban21.example.com
[req_ext]
subjectAltName = @alt_names
[alt_names]
IP.1 = 10.10.10.13
IP.2 = 10.10.10.14
IP.3 = 10.10.10.17
DNS.1 = centos8-2.example.com
DNS.2 = centos8-3.example.com
```
## CSR erstellen
`openssl req -new -key priv.key -out ban21.csr -config server_cert.cnf`

## CSR überprüfen
`openssl req -noout -text -in ban21.csr`

