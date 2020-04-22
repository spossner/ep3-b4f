# ep3-b4f
ep3 based (https://bs.hbsys.de/) docker environment to book desks in the office during corona

# Install
- install docker
- checkout project (git clone https://github.com/spossner/ep3-b4f.git)
- change to the ep3-b4f directory
- run docker-compose up --build

# Setup
- da MariaDB database is spawned (with port 3306 exposed)
- and a PHP 7.2 with apache (with port 8080 exposed)
- visit http://localhost:8080 to start the setup procedure of ep3
- unfortunately need to fill all fields :(
- create an admin user

# Configuration
## Core behaviour
With admin user
- Verwaltung | Einstellungen | Verhalten
-- set Aktivierung to Sofort
-- and Tage im Kalender as desired (e.g. 8) - needs wide screen or smaller zoom in chrome
-- feel free to exclude Samstag, Sonntag from calendar

## Configure the rooms
- give a name
- set Kapazität to the max no of people in that room
- if start 8:00 and end 23:00 then the Zeitblock should be 15x60 = 900 minutes
-- also for Zeitblock min and Zeitblock max
- Stornierung to 0.01 will allow to cancel up to 36 minutes before start
