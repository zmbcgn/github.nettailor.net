# Domain 8 - Software Development Security

## Programming Concepts

- Machine Code
  - 10101010101110
- Source Code
  - programming code
- Assembler Language
  - ADD / SUB / JMP
- Compiler Language
  - translates higher level language into machine code
- Interpreted Language
  - similar to compiler, but does the translation every time it runs the code
- Byte Code
  - procedural languages
  - object-oriented programming

### Top-Down Programming

- start with big picture
- often procedural programming

### Bottom-Up Programming

- multiple sub-system build a more complex system
- often used by OOP

## Software Development Methods

### Waterfall

- linear
- no stepbacks

### Sashimi 

- waterfall with overlapping phases

### Agile

- self organization cross-functional teams
- uses adaptive planning

### SCRUM

- small teams
- product owner
- development team
- SCRUM Master

### Spiral Model

- planning, risk, analysis, engineering, evaluation

### RAD

- 

### Prototyping

- 

### SDLC

- description of phases in the life cycle of software development
- Phases are:
  - Investigation
  - Analysis
  - Design
  - Build
  - Test
  - Implement
  - Maintenance and support
- can have security built into each step

### Projects

- finite start / end
- focused on creating a unique product

### Program

- is a collection of related projects

### Portfolio

- is a collection of projects / programs 

### IPT - Integrated Product Team

- multidisciplinary group of people who are collectively responsible for delivering a defined product

---

* Source Code Escrow
* Source Code Repository

----

### API Security

- Authentication, Access-Control, input Validation, Output encoding / escaping, cryptography, Error handling and logging

### Guidelines

- [NIST 800-128](../../files/NIST/NIST.SP.800-128.pdf)
- Configuration Management Plan (CMP)
- Change Control Board (CCB)
- Configuration Item Identification
- Configuration Change Control
- Configuration Monitoring

### DevOPS

- Software development and delivery process that emphasis communication and collaboration between product management, software development and Operation

## Databases

### DRMS

- Software application that interacts with the user

### Integrity

- referential integrity
  - every foreign key matches primary key
- semantic integrity
  - each attribute value is consistent with the attribute data type
- entity integrity
  - each row has a unique primary value that is not null
- user-defined integrity

---

- Stability
- Performance
- Re-Usability
- Maintainability

---

### Normalization

1. Form: Divide the base data into tables, primary key is assigned to most of the tables
2. Form: Move data that is partially dependent on the primary key to another table
3. Remove data that is not dependent on the primary key

- greater overall database organization
- reduce of redundant data
- data consistency
- flexible database design
- better handle on database security

### DB Query Language

- DDL
  - CREATE , ALTER , DROP
- DML
  - SELECT, DELETE, INSERT, UPDATE

### Coupling

- interdependence between software modules

### Cohesion

- bow much the elements inside the module belong together

- low coupling -> higher cohesion

### ORB - Object Request Broker

- middleware which allows program calls to be made from one computer to another via a network
- Common ORBs:
  - COM
  - DCOM
  - CORBA
  - .net remote

## OOAD

- Object Oriented Analysis and Design
- iteration after iteration, the outputs of OOAD, analysis models for OOA and design models for OOD respectively, will be refined and evolve continuously driven by the key factors like risks and business value.

### OOA

- Object Oriented Analysis
- find the objects
- organize the objects
- describe how the objects interacts
- define behavior of the objects
- define the internals of the objects

### OOD 

- Object Oriented Design
- How we accomplish the things found in the OOA

### OOM

- Object Oriented Modelling
- used to produce abstract and accessible definitions of both

## OWASP - Open Web Application Security Project

- A1 - Injection
  - often SQL / LDAP
  - Mitigation
    - Input validation
    - data type limitation
    - input length
  - CGI
    - sperates the untrusted (user) from the backend (database)
- A2 - Broken Authentication and Session Management
  - Sessions are too long or do not expire at all
  - Session ID is predictible
- A3 - XSS
  - attacker inject client-side scripts into web pages to prevent it we use input validation and data typing
  - detect simultaneous login from two different IPs
- A4 - Broken Access Control
  - need to centralize access control mechanismus
- A5 - Security Misconfiguration
  - default settings in place
  - database configured wrong
  - can be found with vulnerability scanner
- A6 - Sensitive Data exposure
  - sites are http and not https
  - data at rest not encrypted
  - phishing
- A7 - Insufficient Detection and Response
  - not detecting we have been compromised
  - Mitigation
    - patch software
    - close ports
- A8 - CSRF 
  - Cross-Site Request Forgery 
  - stolen session-id or token
  - phising 
  - passwords saved in cookies
- A9 - Using components with known vulnerabilites
  - Windows XP
- A10 - Under protected APIs
  - badly coded 
  - not using TLS

### Additional Attacks

- Buffer Overflow
  - triggered by malformed input
  - can cause system to crash
- Race conditions
  - TOCTOU (time of check to time of use)
- privilege escalation
- Backdoors
- Disclosure

### Software Capability Maturity Model (SW-CMM)

- Level 1: Initial
  - competent people, informal processes, ad-hoc, absence of formal processes / chaotic
- Level 2: Repeatable
  - project management processes, basic lifecycle management processes
- Level 3: Defined
  - engineering process, presence of basic lifecycle management process and reuse of code, use of requirements management, software project planning quality assurance, configuration management practices
- Level 4: Managed (Capable)
  - product and process improvement, quantitatively controlled
- Level 5: Optimizing
  - continous process improvement, Works with IDEAL model


#### IDEAL

1. Initiate 
   * Begin
2. Diagnose
   * Perform assessment
3. Establish
   * Action Plan
4. Action
   * Implement improvements
5. Leverage
   * reassesses and continuously improve

## Acceptance Testing

- user acceptance testing
  - does the software what it is build for?
- operational acceptance testing
- contract acceptance testing
- compliance acceptance testing
- compatibilty / production testing

## Buying Software from other companies

- We have to do proper testing
  - due care / due diligence 
- When we buy COTS (Commercial of the Shelf), we look at reviews
  - we look at reviews
  - check for roadmaps
- We can use and requirement traceability Matrix
- for long / expensive implementation, ask for references
- check financial viable

## AI - Artificial Intelligence

- 

 









