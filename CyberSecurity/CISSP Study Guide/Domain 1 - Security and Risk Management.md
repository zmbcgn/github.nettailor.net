# Domain 1 - Security and Risk Management

## TOC
- Principles of Security
- Security Governance
- Information Security Program
- Information Security Risk Management
- Legal Considerations
- Knowledge Transfer

## CIA Triade
- **Confidentiality vs. Disclosure**
	- keep data secret
	- no one unauthorized can access the data
	- need to know and least privilege
		- Tools to ensure this:
			- secure data-at-rest, data-in-motion, data-in-use
- **Integrity vs. Alteration**
	- protect data against unauthorized modification
	- ensure data is not altered
		- Tools to ensure this:
			- checksums
			- hashes
			- signatures
			- ACL
			- encryption
			- IDS
	- Nonrepudiation
	  - Not beeing able to deny of doing a certain activity or action
	    - made possible through IAAA
- **Availability vs. Destruction**
	- authorized people can access when needed
		- Tools to ensure this: 
			- redundancy on power
			- IPS / IDS
			- SLA's
			- Patch Management
			- RAID
			- Backups
			- 

## IAAA
### Identification
- User Access Control
- name, username, ID etc.
### Authentication
- verify of users identity through ex. Password
- 2nd Factor:
	- Something you know (type 1)
	- Something you have (type 2)
	- Something you are (type 3)

### Authorization
- what the identity is allowed to access
- access-control-matrix
- [DAC](Domain 5 - Identity and Asset Management.md#discretionary-access-control-dac) / [MAC](Domain 5 - Identity and Asset Management.md#mandatory-access-control-mac) / [RBAC](Domain 5 - Identity and Asset Management.md#role-based-access-control-rbac) 

### Auditing

* Recording logs 
* Monitoring is possible without auditing

### Accountability

- Track an action to the subjects identities
- Whats has been done, where, when and by who.
- non-repudiation

### Privacy
- level of confidentiality and privacy protections

## Security Governance Principles
- Least Privlege / need to know
	- you only have access you need (MAC)
	- you access only data you need to know (even access (DAC))
- non-repudiation
	- a user cannot deny doing things (authentication and integrity)
- subject / object
	- subject (active)
		- programs, users etc
	- object (passive)
		- passive data
## Governance vs Management

### Governance
- C-Level (CEO / CIO / CTO / CSO / CISO / CFO )
	- prio / decisions
	- balance upon enterprise objects
	- **risk appetite**
	- monitor compliance and performance

### Management
- plan, builds, run, monitors by the direction set by governance
- **risk tolerance**

## Standards and control frameworks
- [PCI / DSS](https://en.wikipedia.org/wiki/Payment_Card_Industry_Data_Security_Standard)
	- required for creditcard institutes
- [OCTAVE](Operationally Critical Threat, Asset and Vulnurability Evaluation )
	- Self directed Risk Management
- [COBIT](https://en.wikipedia.org/wiki/COBIT)
	- Goals for IT
- [COSO](https://en.wikipedia.org/wiki/Committee_of_Sponsoring_Organizations_of_the_Treadway_Commission)
	- Goals for entire organization
- [ITIL](https://en.wikipedia.org/wiki/ITIL)
	- [ITSM](https://en.wikipedia.org/wiki/IT_service_management)
- [FRAP](https://en.wikipedia.org/wiki/Risk_analysis_(business)#Facilitated_risk_analysis_process)
	- Risk analyzation for business units, application system etc. (with internal employees)
- [ISO 27000](https://en.wikipedia.org/wiki/ISO/IEC_27000)
	- [27001](https://en.wikipedia.org/wiki/ISO/IEC_27001) - Implement and establish ISMS (plan/do/check/act)
	- [27002](https://en.wikipedia.org/wiki/ISO/IEC_27002) - practical advice for ISMS
	- [27004](https://en.wikipedia.org/wiki/ISO/IEC_27004) - measurement of success of ISMS
	- [27005](https://en.wikipedia.org/wiki/ISO/IEC_27005) - risk management
	- [27799](https://en.wikipedia.org/wiki/ISO/IEC_27995) - how to protect protected health information (PHI)

## Defense in Depth
![Defense in Depth](https://mk0resourcesinf5fwsf.kinstacdn.com/wp-content/uploads/2020/10/defense-model04212015.gif ) 
Image via [Infosec Institute](https://resources.infosecinstitute.com/topic/defense-depth-layered-protection-data-security/)

1. Polices, Procedures, Awareness
2. Physical Security
3. Network
4. Server
5. Application
6. Data

- also called layered defense or onion defense

## Laws and Regulations
- Criminal Law
	- "Society" is the victim
	- Punishment: incapacitation / death / financial fines
- Civil Law
	- Individuals, groups or organizations are victims
	- Punishment: financial fines
- Administrative Law
	- laws enacted by the government (for example HIPAA)
- Private Regulation
	- Compliance is required by contract (for example PCI-DSS)

### Laws

* CFAA
* FISMA
* COPPA
* GLBA
* PATRIOT Act
* FERPA
* 

### Liability
- Who is held accountable?
- Who is to blame?
- Who should pay?

### Due Diligence / Due Care
- DD: Research / Practices / Common protection
- DC = Acting on a research / Doing the implementation / Bug fixing etc.

### Negligence
- Opposite of Due Care
	- If you did DC, you are not liable
	- If you didn't do DC, you are most likely liable

## Evidence
### Real Evidence
- physical (not the data)
### Direct Evidence
- Testimony of witness
### Circumstantial Evidence
- Evidence to support circumstances
### Corroborative Evidence
- Support facts
### Hearsay
- not first hand knowledge
	- log files are considered hearsay
	- are admissable when taken near the event
### Best evidence rule (real/direct)
- should be accurate, complete, relevant, authentic and convincing

### Secondary evidence
- logs and documents
### Evidence integrity
- hashed files
- hash before and after forensics with original and copy

### Chain of custody
- Who handled it?
- When did the handle it?
- What did they do with it?
- Where did the handle it?

### Reasonable searches
- 4th Amendment protects US citizen from unreasonable search
- court will determine if evidence was obtained legally
- employees need to be aware that their actions will be monitored

### Entrapment and Enticement
- illegal / unethical
	- when someone is persuaded to commit a crinme they had no intention to do and then charged with it.
- legal / ethical
	- making commiting a crime more enticing, but the person has already broken the law
	- honeypots
### Intellectual property
- copyright
	- granted automatically
	- last 70yrs after creators death
	- attack: piracy / infringement
- trademark
	- must be registered
	- last 10yrs
	- attack: counterfeiting
- patents
	- must be new, useful, nonobvious
	- last 20yrs
	- attack: infringement
- trade secrets
  - last unlimited
  - attack: espionage
## Privacy
- HIPAA - Health Insurance Portability and Accountability Act
	- Strict privacy and security rules on handling PHI
- Security Breach Notification Laws
	- individual by state!
- ECPA - Electronic Communications Privacy Act
	- protects against warrentless wiretapping
- PATRIOT Act of 2001
	- expands law enforcement electronic monitoring capabilities
	- allows search and seizure w/o immediate disclosure
- CFAA - Computer Fraud and Abuse Act
	- most used law to prosecutre computer criminals
- GLBA - Gram-Leach-Briley Act
	- applies to financial institutions
- SOX - Serbanes Oxley Act
- PCI-DSS
- GDPR - General Data Protection Regulation
	- If you have customers in the EU the GDPR applies to you
	- fines up to 20Million or up to 4% of the annual worldwide turnover
	- Restrictions
		- lawfull interceptions
	- Right to access
		- able to provide a free copy on request
	-  Right to erasure
		-  right ot be forgotten
	-  Data portability
		-  data must be in an electronic format
	-  Data breach notification
		-  notify within 72hrs
	-  privacy by design
		-  only data witch is absolutely neccessary
	-  data protection officers
## Legacy Laws
- EU Data Protection Directive
- EU-US Safe Harbor
- Privacy Shield
## International Agreements
### OECD
- 8 principles
1. Collection limitation principle
2. Data quality principle
3. Purpose specification principle
4. Use limitation principle
5. Security safe guards principle
6. Openness principle
7. Individual participation principle
8. Accountability principle

## Information Security Government

TOP
1. Values
	- (Ethics, Principles, Beliefs)
2. Vision
	- Hope and Ambition
3. Mission
	- Motivation and Purpose
4. Strategic Objects
	- Plans/Works and sequencing
5. Action & KPI
	- Actions, Recourses, Outcomes, owners and timeframe
	BOTTOM

### Stategic Objects
- Governance
	- Strategic Plan (3-5 Yrs)
- Management
	- Tactical Plan (1 Yr)
- Staff
	- Operational Plan (High detail, updated frequently)

1. Baselines
	- Tactical
	- Mandatory
2. Procedures
	- Tactical
	- Mandatory
	- low-level step-by-step
3. Guidelines
	- Tactical
	- non-mendatory
	- (recommendations)
4. Standards
	- Tactical
	- Mandatory
	- specific use
	- (specific mendatory controls)
5. Policies
	- Strategic
	- Mandatory
	- High level non-specific
	- (general management statements)
## Personal Security
- Awareness
	- we want to change the behavior
- Training
	- give users a specific skillset
- Hiring Practices
	- background checks
	- NDA
- Employee Termination Process
## Access Control Categories
### Administrative Controls
- Regulations
- Training
- Preventive, Detective, Corrective, Recovery, Deterrent, Compensation
### Technical Controls
- Hardware
- Software
### Physical Controls
- Locks
- Fences
- Guards
## Risk Management
- *Risk* = Threat * Vulneribility (* Impact)
	- Impact can be added to give the full picture
- *Total Risk* = Threat * Vulneribility * Asset Value
- *Residual Risk* = Total Risk - Countermeasures
- *IT Risk Verification* -> IT Risk Assessment -> Response and Mitigation -> Risk and Control Monitoring etc. -> IT Risk Verification....
### Build the team
- Scope
- Methods
- Tools
- Acceptable Risk
- Risk Appetite
### Asset
- Tangible: Physical, Buildings..
- Intangible: Data, trade secrets..
### Risk Assessment
- Quantitive (costs) Risk Analysis
  - 1. Inventory Asset (AV)
    2. Research Asset and do a list of threats. For each Threat define a exposure factor (EF) and a single loss expectancy (SLE)
    3. Perform Threat analysis and calculate an annualized rate of occurrence (ARO)
    4. Derive the overall loss potential by calculating the annualized loss expectancy (ALE)
    5. Research countermeasures (Safeguards) for each threat, then recalculate the ARO und ALE
    6. Perform a cost/benefit analysis of each safeguard for each threat of any asset.
- Qualitive (How bad?) Risk Analysis
- cost-benefit analysis
- Risk Mitigation / Transference / Acceptance / Avoid / Respone
- *NEVER* reject a risk
- Assess countermeasures
	- Good enough?
	- Need for improvement?
	- Do we need new?

| Concept                            | Formula                                  |
| ---------------------------------- | ---------------------------------------- |
| Exposure factor (EF)               | %                                        |
| Single loss expectancy             | SLE = AV * EF                            |
| Annualized rate of occurrence      | # / year                                 |
| Annualized loss expectancy         | ALE = SLE * ARO or ALE = (AV * EF) * ARO |
| Annual cost fo the safeguard (ACS) | $ / year                                 |
| Value of benefit of a safeguard    | (ALE1 - ALE2) - ACS                      |



### Risk Analysis (Quantitive) -> [NIST.SP.800-30r1](../../files/NIST/NIST.SP.800-30r1.pdf)
- Risk Analysis Matrix

| Likelihood (X) / Consequences (Y) | Insignificent | Minor | Moderate | Major   | Catastrophic |
| --------------------------------- | ------------- | ----- | -------- | ------- | ------------ |
| Almost Certain                    | High          | High  | Extreme  | Extreme | Extreme      |
| Possible                          | Minor         | High  | High     | Extreme | Extreme      |
| Unlikely                          | Low           | Minor | High     | High    | Extreme      |
| Possible                          | Low           | Low   | Minor    | High    | Extreme      |
| Rare                              | Low           | Low   | Minor    | High    | High         |

- Risk Register

Category | Name | Risk # | Probability | Impact | Mitigation | Cost | Risk Score after Mitigation | Action by | Action When
------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ 
&nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; 

#### Quantitative
- *A*sset *V*alue (AV) = Worth?
- *E*xposure *F*actor (EF) = Percentage of Asset lost?
- *S*ingle*L*oss*E*xpectancy (SLE)  = (AV * EF) = What does it cost when it happens once?
- *A*nnual *R*ate of *O*ccurrence (ARO) = How often will it happen each year?
- *A*nnualized *L*oss *E*xpectency = Cost per Year if we do nothing
- *T*otal *C*ost of *O*wnership (TCO) = Mitigation Cost: upfront + ongoing

### Risk Control and Monitoring
- Key Goal Indicator
	- tell the management if the it prtocess has archived its business needs
- Key Performance Indicator
	- How are we performing?
- Key Risk Indicators
	- How risky is an activity and how much risk is the organization facing?

### Risk Management Maturity Model
- Level 1(initial) -> Level 2 (Repeatable) -> Level 3 (Defined) -> Level 4 (Managed) -> Level 5 (optimizing)
- Sponsor and management
- Identify risk
- Analyze risk
- Plan risk response
- Integrate risk managment and project management systems
- Trust in and a culture of risk management

### Risk Attackers and Types of Attacks
- Script Kiddies & White / Gray / Black Hackers 
- Internal / External Threat
- Hacktivists / Governments
- Bots / Botnets
- Phishing (Social Engineering)

### NIST Cybersecurity Framework Rev.1.1
- Identify -> Protect -> Detect -> Respond -> Recover
- [Link to NIST Site](https://www.nist.gov/cyberframework)

### Business Continuity Plan [NIST.SP.800-34r1](../../files/NIST/NIST.SP.800-34r1.pdf)
Cycle: Analysis -> Solution Design -> Implementation -> Test & Acceptance -> Maintenance
- Contains:
	- COOP (Continuity of Operations Plan)
	- Crisis Communication Plan
	- Critical Infrastructure Contingency Plan
	- Occupant Emergency Plan

Cycle: Project Initiation (w/ Senior Management) -> Scope the project -> Business Impact Analysis -> Identify Preventive Controls -> Recovery Strategy -> Plan, Design and Development -> Implementation / Training / Testing -> BCP / DRP Maintenance (w/ Senior Management)

### Business Impact Analysis
- Critical is where disruption is not unacceptable
	- may also be defined by law
- For each critical system, function or activity two values are assigned:
	- Recovery Point Objective (RPO)
		- The acceptable amount of data that can not be recovered. The RPO must ensure that the maximum data loss is not exceeded
	- Maximum Tolerable Downtime (MTD)
		- MTD >= RTO + WRT
		- System rebuild time must be less or equal to our MTD
	- Recovery Time Objective (RTO)
		- The amount of time to restore the system (hardware)
	- Work Recovery Time (WRT)
		- How long does it take to configure the software
	- Meantime before failure (MTBF)
	- Meantime to repair (MTTR)
	- Minimum Operating Requirements (MOR)
		- Minimum requirements for critical systems to function