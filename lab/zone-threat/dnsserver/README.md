# DNS Server  

Purpose: To provide DNS Server in the environment.  

## Configuration  

| Component | Value |  
|-----------|-------|  
| Server | Ubuntu Core  |  
| RAM | 256 MB  |  
| IP | 13.13.13.53/24 |  
| Hostname | dns.threat.net |  
| Zone | Threat |  

## Prerequisite  
- bind9  

## Usage  
- Edit /etc/bind/db.threat.net to add a host in threat domain.  

### Logging Queries
- Include the following in /etc/bind/named.conf.local
    logging {
        channel query.log {
            file "/var/log/query.log";
            severity debug 3;
        };
        category queries { query.log; };
    };

- Execute the following
    > sudo touch /var/log/query.log
    > sudo chown bind /var/log/query.log

- In file /etc/apparmor.d/usr.sbin.named, add the following line
    /var/log/query.log w,

- Reload all
    > cat /etc/apparmor.d/usr.sbin.named | sudo apparmor_parser -r
    > sudo systemctl restart bind9.service

[source: https://help.ubuntu.com/lts/serverguide/dns-troubleshooting.html#dns-logging]

## TODO  
- Forward the logs to LMS.  
