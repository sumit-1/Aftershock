# Router  

Purpose: To provide NAT connectivity to internet in the environment.

## Configuration  

| Component | Value |
|-----------|-------|
| Server | OpenWRT 18.06.5  |
| RAM | 128 MB  |
| External IP | NAT |
| Internal IP | 13.13.13.1/24 |
| Hostname | router.threat.net |
| Zone | Threat |

## Notes
- DNS queries to internet is allowed only from dns.threat.net server.
- NTP is blocked.
- Eth0 connects to internet, Eth1 connects to threat.net network.

## Usage  
- Import backup file to router from web interface.

## TODO
- Create a span port to pass data to NIDS.

