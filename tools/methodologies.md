# Metodologías 
Metodologías explicadas, paso a paso con pruebas y herramientas.  
Son las que probe, me funcionaron, me gustaron.

## Listado de varios métodos
Un listado con links y videos de varias metodologías de Recon.  
https://securib.ee/beelog/the-best-bug-bounty-recon-methodology/  


## zseano's methodology (pdf)
https://www.bugbountyhunter.com/methodology/zseanos-methodology.pdf  


## Diferentes Estrategias/Métodologías de Bug Bounty

### Opción 1  
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

### Opción 2
https://www.infosecmatter.com/bug-bounty-tips-8-oct-14/#7_simple_reflected_xss_scenario  

Run  
subfinder -d target.com | httprobe -c 100 > target.txt  
Run  
cat target.txt | waybackurls | gf xss | kxss  
Got a URL which had all the special characters unfiltered and the parameter was callback=  

### Opción 3
https://twitter.com/nullenc0de/status/1236047455831101446  

Methodology:  
1) Identify bug bounty  
2) Enumerate sub domains (I use amass, subfinder)  
3) Feed those to httpprobe  
4) Feed that list to a crawling tool  (hakcrawler)  
5) Feed that list to kxss  
6) grep output for " (easiest win)  

assetfinder target.com | hakrawler | kxss  
  
### Opción 4 
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


### Curso Become Ethical Hacker in 15 Hours - 2021  
https://www.udemy.com/course/become-ethical-hacker-in-15-hours  

#### Recon  

##### Passive Scan  
Harvester  
Recon-NG  
ARP : `arp -a` , `arp -an`  
Wireshark (captura tráfico de la red)  

##### Active Scan  
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

##### Vulnerability Scan y Exploits  
Nessus  
Exploit Databases - https://www.exploit-db.com/  

##### Explotation Framework
Metasploit  
In Kali Linux : `/usr/share/metasploit-framework/`  

```
eervice postgresql start
msfdb init
msfconsole -q
msf > use auxiliary/scanner/portscan/tcp
show options
set RHOST 10.10.2.14
set PORTS 20-500
run
```





