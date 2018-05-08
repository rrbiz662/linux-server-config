# linux-server-config
This project consisted of configuring `Ubuntu server` and deploying the `Catalog Application` created in the previous `item-catalog-project` to it. An `Amazon Lightsail` virtual server was used to host the application. This project demonstrates how to: harden an Ubuntu server, create users and set privileges, setup a Postgres SQL server, and  deploy an application.

## Ubuntu Server Hardening
To harden the `Ubuntu server`:
1) Updated the current server packages.
2) Enabled `SSH`, `HTTP`, and `NTP` ports only.
3) Enabled the `Uncomplicated Firewall` (UFW).
4) Enforced login via `RSA` keys.
5) Verified root ssh and remote login was disabled.

`ssh-keygen` was used to create the private and public key on the local machine via `Git Bash`. `ssh-copy-id` was used to deploy the public key to the server. `PuTTYgen` was used to generate a private `PuTTY` key which was then used to connect to the server via `PuTTy` and test the key login implementation.

## User Access/Privileges
To demonstate user access rights and privileges:
1) Created user `grader`.
2) Added user to `sudo` privilege group.
3) Verified correct privileges.

## Postgres SQL Setup
To demonstrate `Postgres` setup:
1) Installed `Postgres` package.
1) Created `catalog` database.
2) Created `catalog` user/role.
3) Granted user `CONNECT` privileges to the database.
4) Enforced `PASSWORD` login for the user.
5) `REVOKED` privileges for the `public` role.
6) Updated `Catalog Application` python code connecstring to use `Postgres` and `catalog` user.

## Application Deployment
To demonstrate application deployment:
1) Installed `Apache` package to serve Python `mod_wsgi` app.
2) Installed `git` package to get source code from github.
3) Enabled `mod_wsgi`.
4) Transferred source code from `github` to the server `/var/www/catalog/flaskapp` directory.
5) Renamed `application.py` to `__init__.py`.
6) Installed `virtualenv` to hold  `Python` packages.
7) Installed all packages required by the application.
8) Created/configured `VirtualHost` file for the application located at `/etc/apache2/sites-available/catalog.config`
9) Enabled `VirtualHost` for the application.
10) Created/configured `.wsgi` file for the application located at `/var/www/catalog/catalog.wsgi`.
11) Restarted `Apache`.

`pip` was installed to install the required packages and allow the application to function as designed.

## Getting Started
The IP Address to connect to the server is: `54.191.186.106`
The SSH Port is: `2200`

### Prerequisites
To connect to the webpage correctly an internet connection is required.

## Run the Project
To run project:
1) Connect to the IP address `54.191.186.106` via a web browser.

## Ubuntu Packages used:
* `Apache2 2.4.18`
* `Python 2.7.12`
* `Postgres 9.5.12`
* `Git 2.7.4`

## Tools used:
* `PuTTY`
* `PuTTYgen`
* `GitBash`

## PIP Packages used:
* `HTTPLib2 0.11.3`
* `Flask 1.02`
* `Psycopg2 2.7.4`
* `Requests 2.18.4`
* `SQLAlchemy 1.2.7`
* `PassLib 1.7.1`
* `VirturalEnv 15.2.0`
* `URLLib3 1.22`

## References
* For Flask App Deployment - [Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
* For PuTTY setup - [AWS Lightsail](https://lightsail.aws.amazon.com/ls/docs/en/articles/lightsail-how-to-set-up-putty-to-connect-using-ssh)
* For Postgres setup - [Chartio](https://support.chartio.com/knowledgebase/creating-a-user-with-psql)
* For SSH Key setup - [SSH](https://www.ssh.com/ssh/copy-id#sec-Setting-up-public-key-authentication)



## Authors
* Ricardo Rivera