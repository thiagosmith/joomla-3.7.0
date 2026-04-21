# Joomla 3.7.0 Vulnarable
Demosntração de deploy de ambiente vulnerável para exploração da aplicação Joomla - Totalmente didático.

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

# Aviso de Isenção de Responsabilidade – Material de Red Team
Este material destina-se exclusivamente a fins educacionais, acadêmicos e de conscientização em segurança da informação. 

As técnicas, exemplos e cenários aqui descritos têm como objetivo demonstrar vulnerabilidades potenciais e auxiliar profissionais de segurança na prevenção, detecção e resposta a ameaças.

• Não é permitido utilizar este conteúdo para atividades ilegais, maliciosas ou que violem políticas corporativas, regulamentos ou legislações vigentes.

• O uso indevido das informações apresentadas pode resultar em sanções legais, disciplinares e criminais.

• Os autores e distribuidores deste material não se responsabilizam por qualquer dano, perda ou consequência decorrente da aplicação inadequada ou não autorizada 
das técnicas descritas.

• Recomenda-se que qualquer prática de red team seja realizada em ambientes controlados, autorizados e com consentimento explícito das partes envolvidas.
