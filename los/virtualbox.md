* Title: Cheatsheet - VirtualBox 6.0 with Ubuntu 18.04
* Date: 2019-10-21
* File: cheatsheet\virtualbox.md
* Scope: Amsterdam UMC - Apotheek
* License: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 
* Version: 2020-07-27 11:24:58

# VM - Port Forwaring

1. In your VM (Ubuntu 18.04), you can set Port Forwarding.
1. In VirtualBox select `Devices` - `Network` - `Network Settings...`. Click `Advanced`, enable `Cable Connected`. Click `Port Forwarding`.
1. There you can make some connections like:

|Name|Protocol|Host IP|Guest IP|Guest Port|
|----|--------|-------|--------|----------|
|Apache2|TCP|127.0.0.2|80|10.0.2.15|Guest Port|
|Rule2  |TCP|127.0.0.2|8000|10.0.2.15|8000|
|SSH|TCP|127.0.0.2|22|10.0.2.15|22|
|test|TCP|127.0.0.2|8080|10.0.2.15|80|

The network connected to the VM is 10.0.2.0/24. The VM is apperantly connected 
The Guest IP is the IP of the VM. The host IP is the (local) IP address of the PC on which VirtualBox is installed.

1. Je kan extra netwerkpoorten aanmaken. Hiervoor moet de VM (de Guest) eerst uit staan.
1. Om extra poorten aan te maken ga naar `Settings` - `Network` - `Adapter 2`. Vink aan `Enable Network Adapter`, selecteer bij `Attached to:`, `NAT`, selecteerd `Port Forwarding`, klik op `Adds new port to forwarding rule.`
1. Vul daar de volgende informatie in:
    * `Name` - `Apache_80`
    * `Protocol` - `TCP`
    * `Host IP` - `127.0.3.1`
    * `Host Port` - `80`
    * `Guest IP` - `10.0.3.15`
    * `Guest Post - `80`
1. Als je de VM nu opstrart kan je het IP adres ook terug vinden in de Guest VM:
    * `ip address shwow | grep `10.0.3.15`.
1. Vanuit de Host kan je het IP adres ook pingen:
    *  `ping 127.0.3.1`






