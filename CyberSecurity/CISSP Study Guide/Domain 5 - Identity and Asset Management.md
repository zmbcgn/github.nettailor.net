# Domain 5 - Identity and Asset Management

## IAAA

### Identification

- your name, username

### Authentication

- type 1 - Knowledge
  - password, pin, passphrase
- type 2 - posession
- type 3 - biometrics ("you are ...")
- type 4 - somewhere you are
- type 5 - something you do
- MfA - Multi-Factor Authentication
  - two out of the types above

#### Type 1 Authentication

- Brute force attacks
  - use key stretching
- Dictionary attacks
  - limit number of logins
  - do not allow dictionary words
- Rainbow tables
  - limit number of logins (salts)
- Key logger
- Clipping levels
  - to prevent administrative overhead
  - allow failed attempts (only 3-4)
  - block the account for an amount of time
- Microsoft Defaults:
  - password history: set to 24
  - max age: 90 days
  - min age: 2 days
  - min length: 8 chars
  - complexity
  - store password using irreversible encryption

#### Type 2 Authentication

- single-use passwords
  - can be paper-based
  - TAN
- smart-cards or token (HTOP / TOTP)
  - contact
  - contactless
- magnet-swipe cards
  - very easy to replicate

#### Type 3 Authentication

- fingerprint
- facial geometry
- biological characteristics
- behavioral characteristics
  - keystrokes dynamics
  - signature dynamics
- FRR (type-1 error) 
  - False Rejection Rate
  - valid subject denied
- FAR (type-2 error)
  - False Acceptance Rate
  - invalid subject allowed
- Point when FRR and FAR are equal, is the CER (Crossover Error Rate)
- Issues
  - biometrics are easily to get / find out
  - attackers can take pictures
  - how you type can be replayed

### Authorization

#### Discretionary Access Control (DAC)

- often used when availability is not important
- based on Data Owners discretion
- identity based access control

#### Mandatory Access Control  (MAC)

- used when confidentiality is most important
- all objects and subjects have a label
- compartments may or may not be used
- access-control will be enforced on operation system level

#### Role-Based Access Control (RBAC)

- used when integrity is most important

#### Attribute Based Access Control (ABAC)

- subject attributes
  - department
  - title

- action attributes
  - view
  - edit
  - delete

- object attributes
  - description


- contextual attributes
  - time
  - location
  - elements

#### Context-based access control

- based on location, time, access history
- providing username/password followed by challenge/response (such as CAPTCHA)

### Accountability

- providing non-repudiation
- Track an action to a subjects identity

## Access Control Systems

- centralized
  - Pros
    - all systems and location have the same 
    - security posture
    - easier to manage
    - only few have access
    - provides separation of duties
    - SSO can be used
  - Cons
    - Traffic overhead and response time
    - is connectivity to head office stable?
- Identity and access provisioning lifecycle
  - User access review
  - System account access review
  - Provisioning and Deprovisioning
- Accounts can have too much access (excessive privilege)
- Accounts can have inherited privilege (privilege creep)

#### Federated Identity Management

- extends IM from a single organization to multiple organization whishing to share identities between themselves.
- pros
  - ease of account management
  - single-sign-on
  - increased productivity (because staff has to remember just one login and can use SSO)

- cons
  - doesn't prevent brute-force attacks

- SSO
  - OAuth, OpenID, Shibboleth, Kerberos, Active Directory Federation Services (ADFS), Central Authentication Services (CAS)
- SAML
  - XML
  - webbased SSO
  - to secure SAML against eavesdropping or forged assertions use TLS with dig signatures

#### Authentication Protocols

##### Kerberos

- mutual authentication
- client-server model
- protected against eavesdropping and replay attacks
- build on symmetric keys
- uses realms
- KDC - Key Distribution Center
  - trusted third party that provides authentication services. Maintains the secret keys for all registered entities.
- Authentication Server
  - verifies and accepts/rejects tickets based on authenticity and timeliness
- Ticket Granting Server
  - issues tickets to authorized users
- Ticket
  - an encrypted message that provides some form or type of proof depending on what type of ticket it is. 
    - Ticket-Granting Ticket
    - Service Ticket
- Concerns
  - security depends on careful implementation
  - enforcing limited lifetimes for authentication, minimize the threats of replayed credentials
  - KDC must be physically secured and protected
  - KDC can be a SPoF, and therefore must be considered in backup plan and BCP
  - length of the keys (secret and session) is very important
    - too short
      - brute-force attacks
    - too long
      - system can be overloaded
  - encryption processes are based on passwords
    - password-guessing attacks

##### RADIUS

- uses UDP 1812 and 1813
- can support TLS in TCP
- provides AAA between NAS Client and Authentication Server.
- encrypts only the password exchange

##### TACACS+

- uses TCP 49
- two factor authentication
- encrypts entire package
- seperates AAA processes and allows them to be hosted seperately

##### Diameter

- uses TCP 3368 or SCTP port 3868
- supports IPSec and TLS
- was intended to replace RADIUS
- used in 3G space
- 32bit AVP field, RADIUS only 8bit

##### PAP 

- plaintext user/password

##### CHAP

- need plaintext shared secret
- stores plaintext passwords

##### AD - Active Directory

- uses LDAPv2/v3, Kerberos and DNS
- often used as RBAC
- Trust Domains
  - one-way host
  - two-way host
  - Trusted Domain
  - transitive trust
  - intransitive trust
  - 

​	