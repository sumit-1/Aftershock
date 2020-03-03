# DC Server  

Purpose: To provide Domain in Shock Zone.

## Configuration  

| Component | Value |
|-----------|-------|
| Server | Windows Server 2016  |
| RAM | 2048 MB  |
| IP | 10.100.1.10/24 |
| Hostname | DC1.shock.com |
| Zone | SOC-Server |



## Installation

- AD DS
- DNS

*TODO*

### GPO List

- **disable\_defender**  
This will disable Windows defender from the systems. This is necessary to allow proper execution of malwares/hacks.  

- **disable\_updates**  
This will disable windows updates from systems. This is necessary to exploit patched vulnerabilities, e.g., GPO.  
