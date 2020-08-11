# kallithea op Ubuntu 18.04 met Virtualenv

* Datum: 2020-08-11
* Door: Amstedam UMC, & Dion Dresschers
* Licentie: CC BY-SA 4.0
* Versie: 2020-08-11 17:00:24
* Geinspireerd door: [Installation on Unix/Linux — Kallithea 0.6.1 documentation](https://kallithea.readthedocs.io/en/latest/installation.html#installation-virtualenv)

1. 
1. Installeer `virtualenv`
    * `sudo apt install virtualenv`
1. Maak een nieuwe directory aan in `/var/www` genaamd `source_code_management`
    * `mkdir /var/www/source_code_management`
1. Maak een nieuwe virtual environment aan aan in `/var/www/source_code_management`:
    * `python3 -m venv /var/www/source_code_management/venv`
1. Ga naar die virtual environment:
    * `cd /var/www/source_code_management/venv/`
1. Activeer die omgeving:
    * `bin/activate`
1. Het resultaat van bovenstaande is dat de prompt verandert naar een aangeeft dan het een `(venv)` omgeving is.
(venv) dhdresschers@ubuntu-vm:/var/www/source_code_management/venv$    
1. Via `pip`, installeer en update je `pip` en de `setuptools`:
    `pip install --upgrade pip setuptools`
1. Ga naar de data-directory:
    `cd /var/www/source_code_management`
1. Installeer daar `kallithea`
    `pip install --update kallitea`
1. Het kan zijn dat er afhankelijkheden/dependencies zijn. Installeer deze `python-ldap`, `python-pam` en `pychopg2` dan ook:
    * `pip install --upgrade kallithea python-ldap python-pam psycopg2`
1. Je kan nu alle `kallithea` commando's zien:
    * `kallithea-cli [ENTER]`
1. Maak eerst de `kallithea` configuratiefile `my.ini` aan:
    * `kallithea-cli config-create my.ini`


