# ep3-b4f
ep3 based (https://bs.hbsys.de/) docker environment to book desks in the office during corona

# Install
- install docker
- checkout project
- run docker-compose up --build

# Setup
- da MariaDB database is spawned
- and a PHP 7.2 with apache
- visit localhost:8080 to start the setup procedure of ep3
- unfortunately need to fill all fields :(
- create an admin user

# Configurtion
With admin user
- Verwaltung | Einstellungen | Verhalten
-- set Aktivierung to Sofort
-- and Tage im Kalender as desired (e.g. 8) - needs wide screen or smaller zoom in chrome
-- feel free to exclude Samstag, Sonntag from calendar

Configure the rooms
- give a name
- set Kapazität to the max no of people in that room
- if start 8:00 and end 23:00 then the Zeitblock should be 15x60 = 900 minutes
-- also for Zeitblock min and Zeitblock max
- Stornierung to 0.01 will allow to cancel up to 36 minutes before start
