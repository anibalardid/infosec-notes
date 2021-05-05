:warning: Work in Progress :warning:

# :book: Notas sobre InfoSec 
**Autor**: [Anibal Ardid](https://twitter.com/aardid)

Este documento va sobre notas acerca de seguridad en aplicaciones web, pentesting y bug bounty.
El documento es en Español, dado que hay poca info en nuestro idioma.

>Aclaraciones: El objetivo de este documento es tener ordenadas notas para poder testear vulnerabilidades en aplicaciones webs. NO es sobre hackeo malicioso. Es para poder testear aplicaciones propias o participar de programas de Bug Bounty.

>Colaboraciones: En caso de querer colaborar se pueden enviar pull/merge request en este mismo repositorio.

---

## :notebook: Diccionario
Algunas frases o palabras pueden confundir al principio. Por lo cual acá dejo algunas para no perderse en el documento. Algunas están explicadas con palabras mias para que sean de facil entendimiento.

- Pentesting: Prueba de intrusión de sistemas
- Bug bounty: Busqueda de fallas de seguridad y errores
- Blue team: Equipo especializado en prevenir ataques. Seguridad defensiva
- Red team: Equipo enfocado al ataque. Seguridad ofensiva
- Purple team: Equipo mixto entre blue y red 
- Write-Ups: Posts, o papers de gente que escribe el paso a paso de como encontró una vulnerabilidad
- OWASP: Es un proyecto de código abierto dedicado a determinar y combatir las causas que hacen que el software sea inseguro. (https://owasp.org/ , https://wiki.owasp.org/images/5/5e/OWASP-Top-10-2017-es.pdf )
- Oneliner: Se refiere a usar una sola linea de comando para obtener un X resultado. Muchas veces son combinaciones de varios comandos en una sola linea concatenados
- OSINT: Inteligencia de Fuentes Abiertas. Es una metodología multifactorial de recolección, análisis y toma de decisiones sobre datos de fuentes disponibles de forma pública para ser utilizados en un contexto de inteligencia


---

## :microscope: Laboratorios

Para realizar pruebas tenemos diferentes formas: probar en un entorno productivo, en un entorno de pruebas, en entornos locales, o también podemos probar en laboratorios (online o locales).
Estos últimos son entornos preparados especialmente para realizar pruebas.

### Pentest Lab
Diferentes ambientes locales con varios proyectos.
Corre bajo imagenes de docker. E incluye diferentes herramientas de monitorización que pueden usarse para tareas del blue team.

https://github.com/oliverwiegers/pentest_lab


### PortSwigger Web Security Academy
PortSwigger es la empresa detras de Burp Suite (uno de los programas mas importantes para pentesting), y tiene una plataforma muy completa de enseñanza que incluye laboratorios de pruebas, con ejemplos y ayudas sobre como resolver ejercicios.
https://portswigger.net/web-security
https://portswigger.net/web-security/all-labs

### TryHackMe
TryHackme es una web donde se puede acceder a muchos laboratorios gratuitos y pagos. Ademas de poseer cursos y certificaciones.
https://tryhackme.com/
https://tryhackme.com/hacktivities

### HackTheBox (HTB)
Plataforma similar a las previas, con una comunidad y redes sociales muy activas. Como las anteriores también incluye una academia de formación y certificaciones.
https://www.hackthebox.eu/
https://academy.hackthebox.eu/
https://help.hackthebox.eu/

### Vulnhub
https://www.vulnhub.com/

### Root-Me
https://www.root-me.org/

### Virtual Hacking Labs
https://www.virtualhackinglabs.com/


Todas estas plataformas cuentan con retos y máquinas preparadas para ser vulneradas. En caso de no saber cómo empezar a afrontar estos desafíos, te proporcionamos las siguientes fuentes para empezar a coger una buena base:

- Canal de YouTube de S4vitar: https://youtube.com/s4vitar  (En Español)  
- Canal de YouTube de Julio Ureña: https://www.youtube.com/channel/UC2o1vzpUIvgf0VMJIMKZ_rQ  (En Español)  
- Canal de YouTube de Takito: https://www.youtube.com/channel/UCjNHFaBm_0-Mo749MB3A9cQ   (En Español)  
- Canal de YouTube de CyberMentor: https://www.youtube.com/channel/UC0ArlFuFYMpEewyRBzdLHiw  (En Inglés)  
- Canal de YouTube de Ippsec: https://youtube.com/ippsec  (En Inglés)  
- Canal de YouTube de John Hammond: https://www.youtube.com/user/RootOfTheNull  (En Inglés)  
  
Buen canal con explicaciones y videos en español de HACKTHEBOX  
https://www.youtube.com/c/JulioUre%C3%B1a/videos   


---

## :bomb: Vulnerabilidades
Para conocer el TOP 10 de vulnerabilidades, de que se tratan, ejemplos, etc. Lo mas recomendable es inicial con la página de OWASP, mas especificamente el TOP 10 de OWASP.

OWASP TOP 10 - 2017

https://wiki.owasp.org/images/5/5e/OWASP-Top-10-2017-es.pdf

Exploit-DB

https://www.exploit-db.com/


---

## :mortar_board: Cursos, Tutoriales, Academias

PortSwigger Academy  
https://portswigger.net/web-security/all-materials

HacksPlaining  
Security Training for Developers  
https://www.hacksplaining.com/  

HackTheBox Academy  
https://academy.hackthebox.eu/

TryHackMe Hacktivities  
https://tryhackme.com/hacktivities

Bug Bounty Hunting Methodology v2 - Jason Haddix from Bugcrowd's LevelUp 2017  
https://www.youtube.com/watch?v=C4ZHAdI8o1w

The Bug Hunter's Methodology v4.0 - Recon Edition by @jhaddix #NahamCon2020!  
https://www.youtube.com/watch?v=p4JgIu1mceI   

LevelUp 0x02 - Bug Bounty Hunter Methodology v3  
https://www.youtube.com/watch?v=Qw1nNPiH_Go


Curso Introducción al pentesting en español (lista de youtube)  
https://www.youtube.com/watch?v=v8E0_Swe89c&list=PLXm1FM6zsxpBxKtPzT-pQVKoUFXZkuqkh  


Bug Bounty Roadmap  
The Bug Hunter’s Methodology v4 Roadmap  
https://github.com/1ndianl33t/Bug-Bounty-Roadmaps 

Backtrack Academy  
https://backtrackacademy.com/

Guía básica de NMAP  
https://hackear.com.ar/guia-basica-nmap/

Recon Everything  
https://infosecwriteups.com/recon-everything-48aafbb8987  

Bug Bounty Writeups  
https://pentester.land/list-of-bug-bounty-writeups.html  

Cómo usar burp suite  
https://infosecwriteups.com/basic-burp-suite-usage-c23cf65152f2  

Completo write-up en tryhackme  
https://infosecwriteups.com/team-tryhackme-writeup-f36f26289b44  

Awesome-Bugbounty-Writeups  
Lista curada de writeups de bug bounty, inspirada en https://github.com/ngalongc/bug-bounty-reference    
https://github.com/devanshbatham/Awesome-Bugbounty-Writeups   


Guía de uso básico de Burp Suite (ingles)  
https://infosecwriteups.com/basic-burp-suite-usage-c23cf65152f2  

---

## :moneybag: Plataformas de Bug Bounty

- Hackerone [https://www.hackerone.com/]
- Bugcrowd [https://www.bugcrowd.com/]
- Intigriti [https://www.intigriti.com/]


--- 

## :ballot_box_with_check: Cheat Sheets
Diferentes plantillas para tener a mano comandos utiles, checklists, herramientas...

### Subdomains Enumeration Cheat Sheet
https://pentester.land/cheatsheets/2018/11/14/subdomains-enumeration-cheatsheet.html

### OWASP XSS Cheat Sheet
https://owasp.org/www-community/xss-filter-evasion-cheatsheet

### PortSwigger XSS chear sheat
https://portswigger.net/web-security/cross-site-scripting/cheat-sheet

### Checklist for pentesting web applications  
https://github.com/alanbriangh/Magic-CheckList-for-Web-Applications/blob/master/Magic%20CheckList%20for%20Web%20Applications.md  
https://github.com/alanbriangh/Magic-CheckList-for-Web-Applications/blob/master/Magic-CheckList-for-Web-Applications-EN.MD  


---

## :computer: Oneliners

- oneliner to get links from the target itself
```bash
for h in $(cat hosts.txt); do curl -siL https://$h|sed -n -E "s/.*<.*(href|src|url)[=:]['\"]?([^'\">]+).*/\2/p" ; done	
```

- la salida del assetfinder (busca subdominios) se la pasa al httprobe (busca servicios HTTP prendidos) y lo saca a salida.txt
```bash
assetfinder --subs-only dominio.com | httprobe | tee | -a salida.txt
```

https://github.com/KingOfBugbounty/KingOfBugBountyTips

Escaneo de dominios y subdominios

```bash
cat all-domain-extensions.txt | sed 's/FUZZ/redbull/gi' | assetfinder --subs-only | httpx 
```


---

## :earth_americas: Servicios online
Pagos y gratuitos

PenTest WS  
https://pentest.ws/features


---

## :pencil2: Reportes
Ejemplo de reportes

### Penetration Test Report  
https://www.offensive-security.com/reports/sample-penetration-testing-report.pdf 


---


## :wrench: Herramientas  

* [Recon](tools/recon.md)  

* [Vulnerabilidades](tools/vulnerabilities.md)  

* [Popurri Varios](tools/popurri.md)  

* [Payloads](tools/payloads.md)  


---


## :tv: Apuntes de cursos realizados  


[Aprenda Hacking Web y Pentesting](https://docs.google.com/document/d/10o9liBmBNCVwSOPDAdBL9mNI2oumCjHWNnqMQoZpf54/edit?usp=sharing)  

[Bug Bounty Hunting and Web Application Hacking](https://docs.google.com/document/d/1ucBITVKojczWS2F1zwDVXTRy5ZW90oFKPswjFn1b7Q4/edit?usp=sharing)  

[Getting Started with OWASP Zed Attack Proxy (ZAP) for Web Application Penetration Testing](https://docs.google.com/document/d/1F8Vy4ecEP8SULywGtQZKOkKAfcMj5r1WEjdvxhf4Z78/edit?usp=sharing)  

[Testing Applications for CompTIA PenTest+](https://docs.google.com/document/d/1hyjcYorH_drz4doIle9Idnk4J3hGd9Af63CNK4zcTjU/edit?usp=sharing)  

[AngularJS Security Fundamentals](https://docs.google.com/document/d/1m2ptf8fEnQW5MdRGMIcq1wppmnDWTHQHdj2issKMdgI/edit?usp=sharing)  

[Web Application Penetration Testing: Insecure Error Handling](https://docs.google.com/document/d/1VnrjOzSuWuoI_Jqmztp4bxfEcVkDmCHhgTthCuR9MZo/edit?usp=sharing)  

[Web App Penetration Testing: Input Validation](https://docs.google.com/document/d/1yR3NaNLKOBPHKP-CrFXvnCEJvCbGr6PQqqq0b1ins_A/edit?usp=sharing)  

[Web App Hacking: Cross-Site Request Forgery (CSRF) ](https://docs.google.com/document/d/1v8m8h1I-tlH7vzCoJ1y41ZSMwP23J8YAn2YJ23P1Jog/edit?usp=sharing)  



