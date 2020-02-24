# Router  

Purpose: To provide firewall/router to the LAN environment.  

## Configuration  

| Component | Value |
|-----------|-------|
| Server | OpenWRT 18.06.5  |
| RAM | 128 MB  |
| External IP (eth1) | 13.13.13.5 |
| LAN (eth0) | 10.100.1.1/24 |
| DMZ (eth2) | 10..0.1.1/24 |  
| SOC (eth3) | 10.200.1.1/24 |  
| Hostname | router.shock.com |
| Zone | Threat |  

## Notes  
- Eth0 connects to internet, Eth1 connects to threat.net network.  
- DHCP is not set on DMZ.  
- LAN is considered to be secure.  
- Traffic to WAN (Threat) is NATted.  
- DMZ cannot connect to LAN.  
- SOC can connect to any network segment.  

## Usage  
- Import backup file to router from web interface.  
- Credentials: admin:shock1!  

## TODO  
- Define segmentation using VLAN.  
- Create a span port to pass data to NIDS.  

