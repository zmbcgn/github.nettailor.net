# Domain 6 - Security Assessment and Testing

## Security Assessment

- full picture approach of how effective out access controls are
- open multiple areas
  - politics
  - real-world assessment 
  - change management
  - architectural reviews
  - penetration testing
  - vulnerability assessments
  - security audits

#### Security Audits

##### SOC2 

- Type1
  - reports suitability
- Type 2
  - reports rentability and effectiveness

##### Internal and 3rd Party Audits

- Structural audits (3rd Party)
- unstructured audits (internal, is run before external audit)

- Security Audit Logs
  - Review audit logs (detective control)
  - [NIST.SP.800-92](../../files/NIST/NIST.SP.800-92.pdf) suggest the following log sources
    - Network Security Software / Hardware
    - Operating System
  
- Centralized Logging

- Vulnerability Scanners
  - Software with list of many vulnerabilities
  
    

##### Pen-Testing

- test if vulnerabilities are exploitable
- authorized simulated attack
- very important to have very clear rules of engagement
- senior management set goals
- Planning -> Information Gathering and Discovery -> Vulnerability Scanning -> Exploitation -> Reporting
- Black Box
- White Box
- Gray Box
- Tools
  - War Dialing
  - War Driving
  - Wireless test
    - evaluate the risk related to potential access to your wireless network
  - Client-Side Network Attacks
  - Server-Side Network Attacks

#### Social Engineering

- can be used in combination with many other attacks
- Authority
- Intimidation
- Consensus
- Scarcity
- Urgency
- Familiarly

### Software Testing

##### Code Reviews

1. Planning
2. Overview
3. Preparation
4. Inspection
5. Rework
6. Follow-UP

##### Static Testing

- not run / passive test
- walkthrough, syntax checking
- code reviews

##### Dynamic Testing

- run / active executing

- White Box
- Black Box

### TM / RTM

- #### Table, used to map customers requirements to a testing plan

- A requirement trackability matrix my be used to check if current project requirements are being met

### Software testing levels

##### Unit Testing

- functionality of specific section of code
- in object environment usually that the "class"-level

##### Integration Testing

- seeks to verify the interfaces between components

##### component interface testing

- Testing can be used to check handling of data passed between various units
- test a complete system

##### Operational Acceptance

-  

##### Installation testing

- assures software installs correctly

##### Regression testing

- finding defects after mayor code change

#### Software testing types

- Fuzzing
- All-pair testing
- designed to test all possible combination
- uses carefully chosen test vectors
- Interface Testing
  - API
  - GUI
  - Physical Interfaces
- Misuse case testing
  - acting like an attacker
- Test coverage analysis
  - how much of the code did we test?



