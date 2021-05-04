# Recon
Herramientas orientadas al reconocimiento del objetivo


## Workflow

1. TARGET
2. Enumeración de Subdominios
   1. findomain
   2. assetfinder
   3. amass
   4. subfinder
3. Subdominios vivos
   1. httprobe
4. Wayback Machine
   1. waybackurls
5. Screenshots
   1. aquatone
6. Parámetros
   1. paramspider
7. Directorios
   1. dirsearch (fuzzing)
8. JS
   1. subjs
   2. linkdinfer
   3. new-size


## Recon Everything
https://infosecwriteups.com/recon-everything-48aafbb8987  

1. Check/Verify target’s scope (*.example.com)
2. Find subdomains of target (Refer Subdomain tools mentioned in the article)
3. Run masscan
4. Check which domains resolve
5. Take Screenshot
6. Do Content Discovery (by bruteforcing the files and directories on a particular domain/subdomain)

Web Tools:  
https://pentest-tools.com/  
https://virustotal.com/  
https://www.shodan.io/  
https://crt.sh/?q=%25target.com  
https://dnsdumpster.com/  
https://censys.io  
http://dnsgoodies.com  


## Tips

Tips para hacer Recon  
https://hack.com.ar/?p=350 


## Herramientas  

mainRecon  
Automatizar recon  
https://github.com/l34r00t/mainRecon    
https://github.com/l34r00t/vps-mainRecon  


Total Recon
Instalador AIO de varias herramientas de RECON y dependencias
https://github.com/vitalysim/totalrecon


Nuubi  
Herramientas de Recon y escaners  
https://github.com/pikpikcu/nuubi  

https://securityonline.info/nuubi-recon-tools-scanners-and-tools-for-penetration-testing/  


OSMEDEUS  
Reconocimiento automático y escaneo en pruebas de Penetración.  
https://j3ssie.github.io/Osmedeus/  

https://github.com/j3ssie/Osmedeus  


FinalRecon  
Herramienta automatica de recon en sitios web  
https://github.com/thewhiteh4t/FinalRecon

https://kalilinuxtutorials.com/finalrecon-3/


Assetfinder  
Busca dominios y subdominios  
https://github.com/tomnomnom/assetfinder 


Gau  
Getallurls. Obtiene urls conocidas en diferentes servicios como wayback machine  
https://github.com/lc/gau


Chaos Discovery  
Buscador de subdominios para bug bounty  
https://chaos.projectdiscovery.io   


## Fuzzing  

afl++  
https://github.com/AFLplusplus/AFLplusplus  
https://github.com/antonio-morales/EkoParty_Advanced_Fuzzing_Workshop  


## Helper  
Ayuda para crear busquedas en Google  
https://dorks.faisalahmed.me/   


## Pasos de "El Mago"  
Estos son unos pasos que hizo [Adrian "El Mago"](https://twitter.com/soyelmago) , en un twich o video que participé

https://www.youtube.com/watch?v=-eXsnEb4EFo  

```
1- Escaneo de subdominios
https://github.com/tomnomnom/assetfinder 
assetfinder --subs-only redbull.com | tee -a ./salida_redbull.txt
assetfinder --subs-only redbull.com > redbull.txt

2- httpx - escanea puertos
https://github.com/projectdiscovery/httpx 
cat redbull.txt | ./httpx 

assetfinder --subs-only redbull.com | ./httpx -ports 80,81,300,443,591,593,832,981,1010,1311,2082,2087,2095,2096,2480,3000,3128,3333,4243,4567,4711,4712,4993,5000,5104,5108,5800,6543,7000,7396,7474,8000,8001,8008,8014,8042,8069,8080,8081,8088,8090,8091,8118,8123,8172,8222,8243,8280,8281,8333,8443,8500,8834,8880,8888,8983,9000,9043,9060,9080,9090,9091,9200,9443,9800,9981,12443,16080,18091,18092,20720,28017  -o ./salida_vivos.txt

cat redbull.txt | ./httpx  -o salida_vivos_completa.txt

2x - fhc alternativa a httpx
https://github.com/Edu4rdSHL/fhc 
cat hosts.txt | fhc
cat hosts.txt | fhc -2 (only status code 2xx)

- Aquatone - saca screenshots
https://github.com/michenriksen/aquatone 
cat hosts.txt | aquatone -ports large
cat hosts.txt | aquatone -ports xlarge


3- revisamos manualmente la lista y vemos que sucede con algunas url’s

4- por ejemplo abrimos una web que tiene un admin, y ahi probamos escanear directorios internos

5- FFUF - escaneo directorios / fuzzing
https://github.com/ffuf/ffuf 
Repositorio de listado de diccionarios palabras
https://github.com/danielmiessler/SecLists 
https://raw.githubusercontent.com/jivoi/pentest/master/wordlists/fuzz.txt 
https://gist.github.com/jhaddix/86a06c5dc309d08580a018c66354a056 

./ffuf -w ./directory-listxxx-medium.txt -u https://xxxx.redbull.com/FUZZ  -recursion -c -t 120

Para pasarlo a un proxy de burp por ejemplo:
-replay-proxy http://127.0.0.1:8080

Para correr desde vps a un proxy local
ssh -R 18080:localhost:8080 ssh root@IP
ffuf -w ~/tools/Diccionarios/content_discovery_all.txt -u https://GOOGLE.com/FUZZ -replay-proxy http://127.0.0.1.18080
```






