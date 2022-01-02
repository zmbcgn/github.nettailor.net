# Domain 2 - Asset Security

## Information Life Cycles

- Data acquisition -> Data in Use -> Data archival -> Data disposal

## Data classification

 Government / Military      | Private Sector                                               
--------- | ---------
Top Secret (grave damage) | Confidential (grave damage / trade secrets etc.) 
Secret (serious damage) | Private (credit card info etc. / could cause damage) 
Confidential (some damage) | Sensitive (company restricted, only used by a subset of employees) 
Sensitive but unclassified | Company confidential (used only by employees) 
unclassified | Public 

- objects have labels / subjects have clearance!

## 3 States of Data

### Data at rest

- not used 
  - encrypted

### Data in motion

- being transferred on a network
  - encrypt network traffic

### Data in use

- we are using the data
  - clean desk policy, print policy etc.

## Data handling / Data Storage / Data Retention (administrative controls)

### handling

- only trusted individuals
  - logs should be in place (audit)

### storage

- geo distant / climate controlled / secure

### retention

- should not be kept beyond the period of usefulness.
- regulations may apply

## Data, system, mission ownership, custodian and users

### Mission/Business owner

- senior exec who makes policies

### Data  / Information owner

- Management level, key assign labels and backup frequency
  - approve access request

### Data custodian

- day-to-day tasks 
- techs who do backups, restores, patches
- follow the directions of the data owner
- monitor security, maintain accessibility
- Insuring data integrity (CIA)

### System owners

- select security controls
- data-center / infrastructure manager

### data controller and data processor

- create and manage sensitive data
- processors manage the data for controllers (outsourced payroll)

### Security administrators

- responsible for firewalls / IPS and IDS

### Supervisors

- responsible for user behavior and assets created by users
- needs to inform the security administrators if there a any changes

### End-Users

- need to access the data
- user awareness
- follow instructions and policies

### Auditor

- responsible for reviewing and confirming our security policies are implemented correctly

## Memory and Data Remanence

- Remanence : data left over after removal
- ROM
  - PROM, EPROM, EEPROM, PLD
- RAM
  - SRAM, DRAM, SDRAM
- Flash Memory
  - USB Stick
- SSD Drive
  - combination of EEPROM and DRAM
  - cannot be degaussed

## Data destruction

- Paper
  - shredding -> cross shredding!
- Digital
  - delete (removed, but recoverable)
  - format (same as delete, but writes new file structure, still recoverable)
  - overwrite (write zeros or random data over the data)
  - sanitization (remove data to a point where recovery is infeasible for a given level of effort)
  - purge (remove data to a point where recovery is not feasible at all
  - degaussing (apply strong magnetic field)

## Data security controls and frameworks

- scoping
  - determine which portion of a standard we will deploy
- tailoring
  - customizing a standard
- certification
  - protection profile is appropriate for the data its stores
  - meet the security requirements be the data owner
- accreditation
  - data owner accepts the residual risk and the certification

