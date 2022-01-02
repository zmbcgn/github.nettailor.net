# Domain 3 - Security Architecture and Engineering

## Threat modeling

### Process for Attack Simulation and Threat Analysis (PASTA)

- seven-step process

1. Definition of the Objectives (DO)
2. Definition of the Technical Scope (DTS)
3. Application Decomposition and Analysis (ADA)
4. Threat Analysis (TA)
5. Weakness and Vulnerability Analysis (WVA)
6. Attack Modeling & Simulation (AMS)
7. Risk Analysis & Management (RAM)

- dynamic threat identification, enumeration and scoring process
- risk-centric

### STRIDE

- developer focused

1. spoofing
   - threat to authenticity
2. tampering
   - threat to integrity
3. repudiation
   - threat to non-repudiation
4. information disclosure
   - threat to confidentiality
5. denial of service
   - threat to availability
6. elevation of privilege
   - threat to authorization

### Trike

 - acceptable risk focused

### DREAD

 - Disaster/Damage, Reproducibility, Exploitability, Affected Users, and Discoverability
 - each of them is scored from 1 to 10

### Trust but verify

- implicit trust, but verify
- perimeterbased security

### Zero Trust

- never trust, always verify
- [NIST.SP.800-207](../../files/NIST/NIST.SP.800-207.pdf)
- change defense from static to users, assets and ressources
- we use authentication and authorization

### Privacy by design

- proactive not reactive
- privacy as the default
- end-to-end security

### Shared responsibility

- found in cloud computing
- security responsibility is shared between customer and provider

### Secure defaults

 Software should be implemented as secure as possible
 Do risk analysis and usibility test to find the right balance between security and useability

### fail securely

 The system should fail securely. A firewall should not be open when under heavy load. 
 Open/safe vs. closed/secure

### keep it simple

 Keep the security simple to make it better understandable and accepted
 the more complex the security is the more unsecure and harder to manage



## Security Models

### DAC

- Discretionary Access Control
  - Full access to objects the subject has created or given access to.

### MAC

- Mandatory Access Control

### Bell-LaPadula

- Only focused on confidentiality
- Simple Security Property "No READ UP"
- \* Security Property "No WRITE DOWN"
- Strong Property "No read or write UP and DOWN"

### BIBA

- Only focused on Integrity
- Simple Integrity Axiom: "No READ DOWN"
- \* Integrity Axiom: "No WRITE UP"
- Invocation Property: "No READ or WRITE UP"

### Lattice Based Access Control

- 



### Graham-Denning

- used in distribution systems
- focused on relationship between subject and object
- 8 rules that a specific subject can execute

1. Transfer Access
2. Grant Access
3. Delete Access
4. Read Object
5. Create Object
6. Destory Object
7. Create Subject
8. Destroy Subject

### HRU Model

- focused on integrity
- Extension of Graham-Denning Model
- considers subjects can be objects
- 6 operations:

1. Create Object
2. Create Subject
3. Destroy Subject
4. Destroy Object
5. Enter right into access matrix
6. Delete right from access matrix

### Clark-Wilson

- focused on integrity
- seperates end users from backend data through well-formed transactions and 'Seperation of Duties'
- puts program between the two (object/subject)
- seperation of duties
  - person who makes purchase is not allowed to pay the invoice

### Brewer-Nash

- focused on information barriers
-  designed to mitigate conflicts of interest

### TAKE-GRANT Protection Model

- governs the interactions between subjects and objects
- 4 rules

1. TAKE
2. GRANT
3. CREATE
4. REMOVE

### Access Control Matrix

- like an Excel sheet
  - one row per subjects
  - one column per object

### Zachmann-Framework

- Frameworks
  - What?
  - How?
  - Where?
  - Who?
  - When?
  - Why?
- Rule
  - Planner
  - Owner
  - Designer
  - User
  - Programmer
  - Builder

### Security Mode

- can be MAC or DAC
- Dedicated Security Mode
  - formal access approval for **all**
  - need-to-know for **all**
  - all users need to sign a NDA
  - all users have access to **all** data
  - proper clearance for **all** data
- System high Security Mode
  - signed NDA for **all**
  - proper clearance for **all**
  - formal access for **all**
  - need-to-know for **some**
  - all users can access **some** data
-  Compartmented security mode
  - signed NDA for **all**
  - proper clearance for **all**
  - formal access for **some**
  - need-to-know for **some**
  - all users can access **some** data
- Multilevel security mode
  - signed NDA for **all**
  - proper clearance for **some**
  - formal access for **some**
  - need-to-know for **some**
  - all users can access **some** data

## Evaluation Methods / Qualification / Accreditation

### Red Book

- Trusted Networking

### Orange Book

- retired

### ITSEC

- European IT Security Evaluation Criteria
- retired

### ISO/IEC 15408

- common criteria eval are performed on computer security products and systems
- target of evaluation (TOE)
- protection profile (PP)
- Security Target (ST)
- Evaluation Assurance Level (EAL)
  1. Functionally tested
  2. Structurally tested
  3. Methodically tested
  4. Methodically designed, tested and reviewed
  5. Semi-formally designed and tested
  6. Semi-formally verified design and tested
  7. Formally verified design and tested

## Secure System Design Concepts

### Layering

- Only neighbor layers are affected
  - Application <-> OS <-> Kernel and Drivers <-> Hardware

### Security Domains

- Kernel mode
- User mode
- Open and closed Systems
  - open
    - hardware built, evaluated to a standard
  - closed
    - proprietary hardware
    - "security-by-obscurity"

### The ring model

- 4 rings
  - user (ring 3) untrusted
  - kernel (ring 0) trusted
  - hypervisor/vm (ring -1)

## Hardware Architecture

- NorthBridge connects: CPU, GPU, RAM, CPU(ALU/CU)
- SouthBridge connects: USB, MOUSE, CD/DVD, HDD
- North- and SouthBridge are interconnected
- CPU
  - Multitasking
    - Handle multiple Tasks at the same Time
  - Multicore
    - Every CPU has multiple independent execution cores
  - Multiprocessing
    - Multiple CPU inside the same System. Hence more Multitasking capabilities.
    - SMP - Symmetric Multiprocessing (MP handled by one single OS for all Processor)
    - MMP - Massively Parallell processing (MP handled by one OS per Processor)
  - Multiprogramming
    - Similar to Multitasking.
  - Multithreading
    - Perform multiple concurrent tasks within a single process. 
- Memory protection
- process isolation
- hardware segmentation
- Secondary Memory
  - Any additional memory which is not directly available to the CPU (hard-disk, DVD, USB-Sticks etc.)
- virtual memory
- swapping
- paging
- TPM
  - Trusted Platform Module
  - Encryption and Random Number Generation
- DEP
  - Data Execution Program
- ASLR
  - Address Space Layout Randomization
  - Memory protection

## Virtualization, Cloud and Distributed Computing

### Benefits

- less cost (environment and power/cooling)
- easier to maintain
- easier to backup (snapshots)

### Hypervisor

- Type 1 (Bare Metal)
- Type 2 (Runs on your PC)

### Vulnerabilities

- should be on the same network segment
- VM's should be seperated
- VM Escape
- Hypervisor Security
- Ressource Exhaustion

### Cloud Computing

#### Private Cloud

- Oranization run their own infrastructure

#### Public Cloud

- Shared tenancy -> AWS, Google Cloud

#### Hybrid Cloud

- Mix of public/private

#### Community Cloud

- Only for use by a specific community of consumers from organizations that have shared concerns

### IaaS

- Infrastructure as a service
  - we are responsible for Application, Security, Database, OS

### PaaS

- Platform as a service
  - we are responsible for the application

### SaaS

- Software as a service
  - we are responsible for the data

## Emanation and Covert Channels

- electrical emanation
  - key logger
  - it is unintentional information-bearing-signals, which - if intercepted and analyzed - can lead to compromise.
- covert channels
  - creates the capability to transfer information using channels not intended to do so.

### Malware

- Steganography
  - hiding a message inside another media
- Digital Watermark
  - may be hidden
  - often used to fingerprint a file

## Web architecture and attacks

- Applets
  - Java
    - runs in a sandbox, os agnostic
  - activeX
    - runs with certificatres, ms specific
- OWASP
  - A1 Injection
  - A2 Broken Auth
  - A3 Sensitive Data Exposure
  - A4 XML External Entities
  - A5 Broken Access Control
  - A6 Security Misconfig
  - A7 Cross-Site Scripting (XSS)
  - A8 Insecure Deserialization
  - A9 Using Components with known vulnerability
  - A10 Insufficient logging / monitoring

## Database security

### Polyinstantination

- two versions of the same file depending on who accesses it

### Aggregation

- collecting data for statistical analyzing

### Inference 

- deducing from evidence

### Data mining

- discovering patterns in large data sets

### Data analytics

- build baseline, and monitor differences.

## Mobile security

- good policies
  - lock USB ports
  - lock CD drives
  - nework ports
  - disable auto-run
  - use full-disk-encryption
  - remote wipe
  - user awareness
- MDM
- BYOD

## Industrial control systems

### SCADA

- Supervisory Control and Data Acquisition
- DNP3-Protocol

### DCS

- control system for process or plant

### PLC

- digital computer which has been ruggedized and adapted for the manufacturing time.



## Cryptography

### Cryptology

- science of securing communication

### Cryptography

- creates messages where the meaning is hidden

### Cryptanalysis

- science of breaking encrypted communication

### Mathematics and Logical Operations

- OR, AND, NOT, XOR
- Modulo

### Cipher

- cryptographic algorithm
  - plaintext
  - ciphertext
  - encryption
  - decyrption
- Running Key / Book cipher
  - use of well-known text
- Transposition cipher
- Monolithic cipher
  - substitution / easy to break with frequency analysis
- Polyalphabetic cipher
  - same as monoalphabetic but with different starting point each round
- Frequency analysis
  - analyze the frequency of a letter
- Exclusive OR (XOR)
  - very useful in basic cryptography
  - if we have the key, we can decipher
  - used in symmetric encryption
  - used to archieve:
    - confusion
      - relationship between plain and ciphertext should be as random as possible
    - diffusion
    - substitution
    - permutation

## History of cryptography

- Spartan Scytale
- Caesar cipher (substitution)
- vigenère cipher (polyalphabetic substiution)
- cipher disk
- Enigma
- purple - japanese / rotary based
- one-time pad
- vernam cipher
- project "VENONA"
  - Jefferson Disc
  - SIGABA

### COCOM

- used to prevent the export of critical thechnology

### Wassenaar Arrangement

- limits export on military and dual-use technology.

## Encryption today

### Asymmetric

- encrypt with public key / decrypt with private key
- slow
- DH / RSA
- when used for digital signatures:
  - encrypt with private key / decrypt with public key
- used for authentication / non-repudiation

#### prime number factorization

- high prime numbers and multiply
- hard to tell with factorization lead to the result.

#### discrete logarithms

- similar to prime number factorization

- uses logarithms which is the opposite of exponenation

- Diffie-Helman (old)

#### El-Gamel
  - based on DH and used in GNUPGP or PGP
#### ECC
  - often used on low-power-devices
#### Knapsack
  - no longer secure
#### DSA
  - two phases
    - algorithm parameters and computes keypair

### Symmetric

* Number of Keys = n(n-1)/2

#### DES
  - no longer secure
  - 64bit block cipher
  - 56bit key
  - 16 rounds of encryption
  - uses Feistel

#### Block Cipher has 5 modes
  - ECB - Electronic Code Block
  - CBC - Cipher Block Chaining
  - CFB - Cipher Feedback
  - OFB - Output Feedback
  - CTR - Counter

#### 3DES
  - secure until 2030
  - 64bit block cipher
  - 56bit key
  - 16 rounds
  - uses Feistel
  - 3 rounds of DES
    - Keymode1 - 3 different keys with 112bit key strength (common)
    - Keymode2 - 2 different keys with 80bit and 1/3 same key
    - Keymode3 - Same key 3 times, just as insecure as DES (encrypt/decrypt/encrypt)

#### IDEA
  - designed to replace DES
  - 64bit block cipher
  - 128bit key
  - not widely used, because of patents

#### AES
  - uses both transposition and substitution
  - 3+1 Rounds
    - SubBytes
    - ShiftRows
    - MixColumns
    - Final Round (no MIxColumns)
      - SubBytes
      - ShiftRows
      - AddRoundKey
  - Key Size specifies the number of rounds
    - 10 for 128bit
    - 12 for 192bit
    - 14 for 256bit

#### Blowfish
  - no longer secure
  - 64bit block cipher
  - 32 - 448bit key
  - Uses Feistel
  - Dev recommends using Twofish

#### Twofish
  - Uses Feistel
  - 128bit block cipher
  - 128, 192, 256bit Key length
  - considered secure

#### Feistel cipher
  - splits plaintext in left and right halves
  - right halve never changes

#### RC4 
  - used for WPA/SSL/TLS
  - stream cipher
  - 40 - 2048bit key

#### RC5
  - 32, 64 and 128bit blocks
  - 0 - 2040bit key
  - uses Feistel
  - considered secure

#### RC6
  - AES3 
  - based on RC5
  - 128bit block cipher
  - 128, 192 and 256bit key
  - uses Feistel
  - considered secure

### Hashing

- proves the integrity of the data
- one-way function
- collision
  - when two hashes provide the same hsah on different files
- variable length input / fixed length output
- MD5
  - ​	128bit fixed length
- MD6
  - supposed to replace MD5, but SHA2/3 won.
- SHA1
  - 160bit Hash Value
  - not use
- SHA2
  - ?
- SHA3
- RIPE MD
- RIPEMD160
- Salting
  - random data
- Nonce

### Attacks on Cryptography

- Steal the Key
- Brute Force
  - try every combination of lettets/signs/numbers possible
- Key stretching
  - effective against brute force; add 1-2 seconds to verification
- Digraph attack
  - similar to frequency analysis/attacks, but also looks on common ports
- Man-in-the-middle
  - attacker relays traffic through a box under the control of the attacker.
- TCP session hijacking
  - attacker takes over sssion ID and  masquerades as authorized user
- Social Engineering
- Rainbow tables
  - pre-made list of plaintext and matching cipher texts
- Known plaintext
  - you know the painttext and ciphertext, try to find the key
- Chosen plaintext
  - you choose the plaintext, to find the key.
- adaptive chosen plaintext
  - chosen plaintext, but the attacker "adapts" the following rounds based on previos rounds
  - meet-in-the-middle
    - attacker knows parts of plain and ciphertext used to break multiple ciphers
- known key
  - attacker knows something about the key
    - length
    - syntax
    - etc.
- differential cryptoanalysis
  - attacker tries to find differences between related plaintext
- linear cryptoanalyisis
  - attacker has a ton of plain and ciphertext pairs
  - created with the same keys
  - attacker studies the pairs
- differential linear cryptoanalysis
  - both combined
- side channel attacks
  - attacker uses physical data to break crypto system
  - cpu cycles
  - power consumption
- Implementation attacks
  - find flaws in the implementation
- key clustering
  - when 2 different symmetric keys used on the same plaintext produce the same ciphertext, both can decrypt ciphertext from the other keys

## Implementing Cryptography

### PKI

- uses symmetric and asymmetric encryption and hashes to provide and manage digital certificates
- keep private key secret
- store copy of key pair somewhere secure
- 4 eyes principle for key retrieval

### Key Escrow

- keys are kept by a third-party organization

### Digital Signatures

- provides **integrity**
- provides **non-repudiation**

### Digital Certificates

- are public keys
  - signed with digital signature
- server based
  - SSL / TLS
- client based
  - digital signature
- CA
  - issues / revokes the certificates
- ORA
  -  Organizational Registration Authorities
- CRL
  - client revocation lists
- OCSP
  - online certification states protocol
  - better balance
  - faster
  - client / server hybrid
- Alice has Data -> Data gets Hashed with Algorithm -> HASHED DATA  -> encrypt with private key -> DATA + Dig. Signature -> Transfered over the Internet -> On Receivers Side: DATA + Dig. Signature -> DATA gets hashed and Dig. Signature gets decrypted with public key -> If two hashes (DATA Hash and decrypted Hash) matches the DATA has not been altered (hashing for **integrity** and private and public key **non-repudiation**).
- Confidentiality can be added also, but it is not common. After Alice has encrypted the DATA with Alice's private key, Alice would encrypt the DATA again with Bob's Public Key.

### HMAC / MAC / SSL / TLS

- MAC 
  - Message Authentication Code
  - Hash function using a key
  - CBC-MAC, for instance, uses cipher-block-chaining (like DES)
  - provides integrity and authenticity
- HMAC
  - Hashed Message Authentication Code
  - a PSK is exchanged
  - output is hashed
  - hashed is combined with key -> HMAC
  - the receiver does the same and compares the two hashes
- SSL
  - currently on Version 3.0
  - mostly used for web traffic
- TLS
  - more secure than SSL v.3.0
  - used for email and internet chat

### IPSEC (Internet Protocol Security)

- set of protocols that provide cryptographic layer to IP traffic
- IPv6 has it built in
- often used for VPNs

#### AH - Authentication Header

- provides authentication and integrity for each packet
- does not provide confidentiality
- protects against "replay attacks"

#### ESP - Encapsulation Security Payload

- provides confidentiality
- it can provide authentication and integrity

#### SA - Security Association

- simplex connection
- can be used to negotiate ESP or AH parameters
  - if 2 systems use ESP, the need 1 SA per connection
  - if the use AH and ESP, the use 2 x 2 SA
- a unique 32bit SPI (security parameter index) is used to identify each SA connection

#### ISAKMP

- Internet Security and Key Management Protocol
- Manages the SA creation process and key exchange
- Tunnel Mode
  - encrypts and authenticates the whole packet
- Transport Mode
  - encrypts only the payload

#### IKE - Internet Key Exchange

- IPsec can use different types of encryption and hashes
- IKE negotiates the algorithm selection process
- the 2 sides of an IPSEC tunnel will normally use IKE to negotiate the highest and fastest

#### PGP

- provides privacy and authentication
- can provide confidentiality, integrity, authentication and non-repudiation
- uses a serial combination of hashing, data compression, symmetric-key cryptography and finally public-key crypto
- uses web-of-trust

#### MIME

- provides a standard way to format email

#### S/MIME

- uses pki to encrypt and authenticate MIME encoding email.



## Physical Security

- Preventive Control
  - prevents action from happening
- Detective Control
  - controls that detect an attack (cctv, alarms)
- Deterrent Control
  - controls that deter an attack (fences, guards)
- Compensating Control
  - controls that compensate for other controls that for example are too costly
- Administrative Control
  - controls that give us administrative framework (policies, compliance, laws)

### Perimeter defense

- Fences (Deterrent, Preventive)
- Gates (Deterrent, Preventive)
  - ASTM Standard
    - Class 1, 2, 3, 4
- Bollard (Preventive)
- Lights (Detective and Deterrent)
- CCTV (Detective and Deterrent)
- Locks (Preventing)
  - Key bitten code
  - PIN Tumble lock
  - Master Key
  - Core Key
  - Combination Lock
- Smart Card
  - Contact Cards
  - Contactless Cards
- Magnetic Stripe Cards
- Mantrap
- Turnstyle (Deterrent, Preventive)
- Contraband Checks (Detective, Deterrent, Preventive)
  - Often seen in airports or courthouses.
- Motion Detectors (Detective, Deterrent)
  - Ultrasound, Microwave, Infrared, Laser
- Guards (Deterrent, Preventive, Detective, Compensating)
  - Professional Guards
    - armed and trained
  - Amateur Guards
    - armed and not trained
  - Pseudo Guards
    - unarmed
- Dogs (Deterrent, Detective, Compensating)
  - Liability can be an issue

#### Site selection

- Greenfield
- Topography
- Utilities
- Crime

#### Site Design

- don't advertise
- lock wiring closets
- be non-descript
- provide as aless as information as possible
- demarc (Point of demarcation)
- Think about the future
  - How much HVAC is needed?
  - Which material events do we need to factor in?
  - Do we have enough power for the future?
    - Blackouts / Brownouts?
  - What kind and capacity of a UPS

#### Fire Suppression

- Dry Pipe vs Wet Pipe
- Halon / Chemical / FM200
- Fire Extinguishers

#### Media Storage and location

- should be encrypted (DATA at rest)
- should be stored offsite
- keep in mind temperature and HVAC

#### Asset Tracking

- Accurate Inventory
- Hardware hardening
- disable USB Ports
  - physically
  - logically

#### Electricity

- have to be clean
- reliable
- Power Fluctuation Terms
  - Blackout - long loss of Power
  - Fault - short loss of Power
  - Brownout - long loss of Voltage
  - Sag - short loss of Voltage
  - Surge - long high Voltage
  - Spike - short high Voltage

#### Surge Protectors

- protect from high volt

#### USP

 - ensures clean power
 - have large battery bank

#### Generator

- fueled generator

#### PDU

- ensures we have the right voltage

#### Electromagnetic interference

- crosstalk
- can impact integrity (data corruption)
- can impact confidentiality (data sniffed)
- can impact availability (data unavailable)

#### HVAC

- HEAT
  - 20 - 25 ° C
  - keeping data center to cold, wastes money and raises humidity
- Pressure
  - higher pressure inside of the DC
- Humidity
  - should be between 40% and 60%
  - low humidity will cause static electricity and high humidity will corrode metals

#### Detectors

* Heat detectors
* Smoke detectors
  * Ionization
  * Photoelectric
* Flame detectors
  * detect infrared light

### Personnel Safety

- Organization should have clear policies, procedures
- Evac Plans
- Meeting points
- Plan for disabled employees
- Fire/Evac drills quarterly/anually
- Warning signs / sirens

### Fire suppression

- Fire needs 3 of the fire triangle (Oxygen / Heat / Fuel)

### Fire classes

- Class A (ash)
  - ordinary shaft
- Class B (barrel)
  - liquids / gases
- Class C (current)
  - electric
- Class D (dynamite)
  - combustible
- Class K (kitchen)
  - fat

#### Water

- do not use in DC
- orange (57°C) / red (68°C) / yellow (89°C) / green (93°C) sprinkler bulb
  - each sprinkler is independent
- wet pipe
- dry pipe
- deluge
  - like dry pipe, but without pressurized air (open valve)

### Automatic Fire Suppression System

#### Gases

- CO²
  - only in unmanned areas
  - odorless and colorless
- Halon 1301
  - only not to be used since 1994
  - fast
- Fe-13 (Fluoroform)
- FM-200 (HFC-227ea)
  - mostly used today in DC
- Inergen
  - breathable but will kill the fire

#### Fire extinguishers

- should be marked
  - **P**ull the pin
  - **A**im at the base
  - **S**queeze the lever
  - **S**weep from side to side
- Soda-Acid -> not used
- Dry-Powder -> lower temp / remove oxygen (metal fires)
- wet-chemical -> remove oxygen with foam

