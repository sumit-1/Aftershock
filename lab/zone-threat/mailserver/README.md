# Mail Server  

Purpose: To provide Email functionality in the environment.

## Configuration  

| Component | Value |
|-----------|-------|
| Server | Ubuntu Core  |
| RAM | 256 MB  |
| IP Address | 13.13.13.25/24 |
| Hostname | mail.threat.net |
| Zone | Threat |

## Notes
- Since only few email ids are required, configuration settings are kept to minimal.

## Setup  
- Install necessary packages.  

    > apt-get update  
    > apt-get install apache2 php7.5  

    > apt-get install postfix  
    
    In options, select "internet site". system mail name: "threat.net".
    
- Testing if the postfix works:
    > echo "test" | sendmail user@threat.net
    > cat /var/mail/user

- Installing dovecot
    > apt-get install dovecot-core dovecot-imapd dovecot-pop3d  

- Install squirrelmail (webmail)
    > wget https://downloads.sourceforge.net/project/squirrelmail/stable/1.4.22/squirrelmail-webmail-1.4.22.tar.gz
    > tar -xzf squirrelmail-webmail-1.4.22.tar.gz
    > mkdir /var/www/html/squirrelmail
    > mv squirrelmail-webmail-1.4.22/* /var/www/html/squirrelmail/
    > chown -R www-data:www-data /var/www/html/squirrelmail/
    > chmod -R 755 /var/www/html/squirrelmail/
    > perl /var/www/html/config/conf.pl
    > mkdir -p /var/local/squirrelmail/data
    > chown -R www-data:www-data /var/local/squirrelmail/data

- Login to squirremail webmail (http://mail.threat.net/squirrelmail) with credentials:  
 
       user:user
  If you are able to see the test message you sent as root, it works.  

- Create a new user
    > useradd --create-home -s /sbin/nologin spammer
    > passwd spammer

-  ##### Final Test  
    From any other machine,
    > echo "final" | sendmail spammer@threat.net  

   Login from squirrelmail as spammer. If you can see the email, success.



