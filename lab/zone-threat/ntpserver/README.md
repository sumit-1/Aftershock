# NTP Server  

Purpose: To provide NTP Server in the environment.  

## Configuration  

| Component | Value |  
|-----------|-------|  
| Server | Ubuntu Core  |  
| RAM | 256 MB  |  
| IP | 13.13.13.123/24 |  
| Hostname | ntp.threat.net |  
| Zone | Threat |  

## Prerequisite  
- Python2.7  

## Usage  
    > sudo python ntpserver.py  


This will provide timesync all the machines with internal time of this machine.   

## Tips  
- Execute command inside a tmux shell.  
- Even if using same time as of host, make time differ by 2 minutes to confirm ntp client working.  

## TODO
- Migrate to Python3.  
- Use smaller linux.  
