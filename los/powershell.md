<img src="../static/amsterdam_umc_logo_rgb.svg" height="50%" width="50%" style="display: block; margin-left: auto;
 margin-right: auto; width: 50%;">
<p style="text-align:center; font-size: 200%;">Apotheek</p>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fork-awesome@1.1.7/css/fork-awesome.min.css" integrity="sha256-gsmEoJAws/Kd3CjuOQzLie5Q3yshhvmo7YNtBG7aaEY=" crossorigin="anonymous">

* License: <i class="fa fa-creative-commons" aria-hidden="true"></i> CC BY-SA 4.0
* By: Dion Dresschers of Amsterdam UMC
* Version: 2020-03-17 10:42:54

# PowerShell Cheat Sheet

## Get an object

```
PS H:\> get-adcomputer 19-000239
```

## Show all properties of an object
```
PS H:\> get-adcomputer 19-000239 | Format-List *
```

## Get all objects by piping to Get-Member (!?)

```
PS H:\> get-adcomputer 19-000239 | Get-Member
```

## Get the properties of an object by piping to Select-Object

```
PS H:\> get-adcomputer 19-000239 | Select-Object DistinguishedName
```

## Get Ad Group

```
PS H:\> Get-ADGroup app_divh_poliapo_pc__gebr
```

## Get Ad Group Member-ship

```
PS H:\> Get-ADGroupMember app_divh_poliapo_pc__gebr
```

## Get Ad Group Member-ship and filter on a property

```
PS H:\> Get-ADGroupMember app_divh_poliapo_pc__gebr | where distinguishedname -Like "*zelfbeheerd*"
PS H:\> Get-ADGroupMember app_divh_poliapo_pc__gebr | where distinguishedname -Like "*divisiebeheerd*"
PS H:\> Get-ADGroupMember app_divh_poliapo_pc__gebr | where distinguishedname -Like "*amcplus*"
PS H:\> Get-ADGroupMember app_divh_poliapo_pc__gebr | where distinguishedname -Like "*toepassingsspecifiek*"
PS H:\> Get-ADComputer -Filter * | Where-Object {($_distinquishedname -Like "*amcstandaard*")}
```

## Get Ad Group Member-ship and filter twice on a property
 
```
PS H:\> Get-ADComputer -Filter * | where distinguishedname -Like "*apo*" | where distinguishedname -Like "*divisie*"
```

## See AD Group and Members

```
PS H:\> Get-ADGroup org_divi_apo_poliapo_rol_ontslagteam
PS H:\> Get-ADGroup org_divi_apo_poliapo_rol_ontslagteam | Get-Member
```

## Get AD User 

```
PS H:\> Get-ADUser -Filter 'Name -like "*dresschers*"'
```

## Get AD User get exact match

```
PS H:\> Get-ADUser -Filter 'Name -like "*dresschers*"'
```

## Get AD User filter on admin 

```
Get-ADUser -Filter 'Name -like "admin*"'
``1

##
PS H:\> Get-ADUser -Filter 'Name -like "dhdresschers"' | format-list *
PS H:\> Get-ADUser -Filter 'Name -like "dhdresschers"' | get-member

```
PS H:\> Get-ADUser -Filter 'Name -like "dhdresschers"' | Select-Object GivenName, Surname
```

## See all parents
```

``` 
PS H:\> Get-ADPrincipalGroupMembership dhdresschers 
PS H:\> Get-ADPrincipalGroupMembership dhdresschers | select name
```

## Install Power Shell on Ubuntu 18.04

### Download the GPG keys

```
$ wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
```

### Install the package file

```
$ sudo dpkg -i packages-microsoft-prod.deb
```

### Update the packages and check if packages.microsoft is updated

```
$ sudo apt-get update | grep packages.microsoft.com
```

### Enable the repository called: universe

```
$ sudo add-apt-repository universe
```

### Install PowerShell and answer "Yes" on each question

```
$ sudo apt-get install powershell -y
```

### Check if PowerShell is installed

### Start PowerShell

$ pwsh

```
dhdresschers@ubuntu-vm:~$ sudo apt-get update | grep packages.microsoft.com                                             Hit:4 https://packages.microsoft.com/ubuntu/18.04/prod bionic InRelease  
```

### Get Net IP Address

```
PS H:\> Get-NetIPAddress | where addressfamily -match 'ipv4'
PS H:\> Get-NetIPAddress | where addressfamily -match 'ipv4' #| Select-String -Pattern '.*169.*'
```

### See all parent groups

Handig om te zien welke info allemaal gepusht wordt naar welke PC.

```
PS H:\> Get-ADPrincipalGroupMembership dhdresschers
```

```
PS H:\> Get-ADPrincipalGroupMembership (Get-ADComputer 18-004993)
```

```
PS H:\> Get-ADPrincipalGroupMembership (Get-ADComputer 18-004993) | findstr 'star'
distinguishedName : CN=dist_app_w7_drv-starfvp_10_en,OU=Win7,OU=Extra,OU=Productie,OU=Application 
name              : dist_app_w7_drv-starfvp_10_en
SamAccountName    : dist_app_w7_drv-starfvp_10_en
```