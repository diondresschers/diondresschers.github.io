* Door: Dion Dresschers
* Licentie: CC BY-SA 4.0  
* Datum: 2020-07-27
* Revisie: Jaarlijks
* Versie: 2020-07-27 16:27:18

# UFW (Uncomplicated FireWall) on Ubuntu 18.04

1. Check if UFW is enabled:
    * `sudo ufw status`
1. The result can be that UFW is disabled:
    * `Status: inactive`
1. You can enable UFW if it is not enabled:
    * `sudo ufw enable`
1. You can again the status if the firewall is enabled:
    * `sudo uf status`
1. If the firewall is enabled you will see the open ports like:
    ```
    Status: active

    To                         Action      From
    --                         ------      ----
    80/tcp                     ALLOW       Anywhere                  
    80/tcp (v6)                ALLOW       Anywhere (v6) 
    ```
1. You can see all options by
    * `ufw` + [tab]-key
1. This will result in:
    ```
    allow      delete     --dry-run  --help     logging    reset      status
    app        deny       enable     insert     reject     route      version
    default    disable    --force    limit      reload     show     
    ```
1. You can allow new ports and optionally the protocol via:
    * `sudo ufw allow 22/tcp`
1. You can see the result via `ufw status`:
    ```
    Status: active

    To                         Action      From
    --                         ------      ----
    80/tcp                     ALLOW       Anywhere                  
    80/tcp (v6)                ALLOW       Anywhere (v6)      
    ```
1. You can delete the second entry as this is IPv6, by refering it to as `2`:
    * `sudo ufw delete 2`
1. This will result in:
    ```
    Deleting:
    allow 80/tcp
    Proceed with operation (y|n)? y
    Rule deleted (v6)
    ```
1. You could also deleted both via:
    * `ufw delete 80/tcp`
1. UFW has also some built in ports via `apps`:
    * `sudo ufw app list`
1. This will result in:
    ```
    Available applications:
    Apache
    Apache Full
    Apache Secure
    CUPS                                                                         OpenSSH
    ```
1. You can see the specific port(s) for an application by:
    * `sudo ufw app info "Apache Full`
1. This will result in:
    ```
    Profile: Apache Full                                                                                                    Title: Web Server (HTTP,HTTPS)                                                                                          Description: Apache v2 is the next generation of the omnipresent Apache web                                             server.                                                                                                                                                                                                                                         Ports:                                                                                                                    80,443/tcp        
    ```
1. You can specify from and to a specific IP address via:
    `sudo ufw allow from 10.0.2.15/24 to 192.168.1.1/24 app Cups`
1. This will result in:
    ```
    Status: active                                                                                                                                                                                                                                  To                         Action      From                                                                             --                         ------      ----                                                                             80/tcp                     ALLOW       Anywhere                                                                         22/tcp                     ALLOW       Anywhere                                                                         192.168.1.0/24 CUPS        ALLOW       10.0.2.0/24       
    ```
1. UFW uses underwater IPTables. You can see the UFW config files:
    * `ls -l /etc/ufw/
1. The UFW rules added by the user can be seen by:
    * `sudo less /etc/ufw/user.rules`


