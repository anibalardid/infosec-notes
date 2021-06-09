:warning: Work in Progress :warning:

# :book: Notas sobre InfoSec 

**Autor**: [Anibal Ardid](https://twitter.com/aardid)

En este documento voy a ir poniendo información que a mi me sirvió para ir aprendiendo, como capacitarse online e ir practicando, herramientas, y todo lo que se me vaya ocurriendo sobre seguridad en aplicaciones web, pentesting y bug bounty.  

El documento es en Español, dado que hay poca info en nuestro idioma.

Este archivo principal lleva lo mas básico sobre el tema, introducción, y enlaces a otras secciones con información más detallada.  


**Aclaraciones**   
1) Para encarar este tema hay que tener mínimos conocimientos de linux, redes y manejar la consola. 
2) El objetivo de este documento es tener ordenadas notas para poder testear vulnerabilidades en aplicaciones webs.  
**NO** es sobre hackeo malicioso. Es para poder testear aplicaciones propias o participar de programas de Bug Bounty.  
El documento se irá actualizando de forma constante. Agregando y mejorando todo lo que voy aprendiendo , y mejorando para que sirva de guía.  
  

**Colaboraciones**  
En caso de querer colaborar se pueden enviar pull/merge request en este mismo repositorio.


---

## :notebook: Diccionario
Algunas frases o palabras pueden confundir al principio. Por lo cual acá dejo algunas para no perderse en el documento. Algunas están explicadas con palabras mias para que sean de facil entendimiento.

- Pentesting: Prueba de intrusión de sistemas
- Bug bounty: Busqueda de fallas de seguridad y errores
- Blue team: Equipo especializado en prevenir ataques. Seguridad defensiva
- Red team: Equipo enfocado al ataque. Seguridad ofensiva
- Purple team: Equipo mixto entre blue y red 
- Write-Ups: Posts, o papers de gente que escribe el paso a paso de como encontró una vulnerabilidad
- OWASP: Es un proyecto de código abierto dedicado a determinar y combatir las causas que hacen que el software sea inseguro. ( https://owasp.org/ , https://wiki.owasp.org/images/5/5e/OWASP-Top-10-2017-es.pdf )
- Oneliner: Se refiere a usar una sola linea de comando para obtener un X resultado. Muchas veces son combinaciones de varios comandos en una sola linea concatenados
- OSINT: Inteligencia de Fuentes Abiertas. Es una metodología multifactorial de recolección, análisis y toma de decisiones sobre datos de fuentes disponibles de forma pública para ser utilizados en un contexto de inteligencia


--- 

## :microscope: Laboratorios

Para realizar pruebas tenemos diferentes formas: probar en un entorno productivo, en un entorno de pruebas, en entornos locales, o también podemos probar en laboratorios (online o locales).  

Estos últimos son entornos preparados especialmente para realizar pruebas.

Acá resumo algunos de los laboratorios más conocidos.  

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

### Laboratorios locales con Docker  
https://github.com/vulhub/vulhub    

### Hacker101 CTF
https://ctf.hacker101.com/    

--- 

Todas estas plataformas cuentan con retos y máquinas preparadas para ser vulneradas. En caso de no saber cómo empezar a afrontar estos desafíos pongo algunos lugares para entender de que va todo esto.  

- Canal de YouTube de S4vitar: https://youtube.com/s4vitar  (En Español)  
- Canal de YouTube de Julio Ureña: https://www.youtube.com/channel/UC2o1vzpUIvgf0VMJIMKZ_rQ  (En Español)  
- Canal de YouTube de Takito: https://www.youtube.com/channel/UCjNHFaBm_0-Mo749MB3A9cQ   (En Español)  
- Canal de YouTube de CyberMentor: https://www.youtube.com/channel/UC0ArlFuFYMpEewyRBzdLHiw  (En Inglés)  
- Canal de YouTube de Ippsec: https://youtube.com/ippsec  (En Inglés)  
- Canal de YouTube de John Hammond: https://www.youtube.com/user/RootOfTheNull  (En Inglés)  
  
Buen canal con explicaciones y videos en español de HackTheBox    
https://www.youtube.com/c/JulioUre%C3%B1a/videos   


---

## :bomb: Vulnerabilidades
En cuanto a vulnerabilidades, hay un listado de cuales son las más comunes y las más importantes en cuanto al impacto que producen.  

Para conocer el TOP 10 de vulnerabilidades, de que se tratan, ejemplos, etc. lo más recomendable es inicial con la página de OWASP.

OWASP TOP 10 - 2017  
https://wiki.owasp.org/images/5/5e/OWASP-Top-10-2017-es.pdf  

Exploit-DB  
https://www.exploit-db.com/  


---


## :mortar_board: Cursos, Tutoriales, Academias

Un interesante listado de los que yo considero mejores recursos para capacitarse, ya sean cursos, tutoriales, notas, etc.  

[Clic acá para abrir la info](./training.md)

---

## :moneybag: Plataformas de Bug Bounty 

Que es bug bounty ya esta aclarado en el diccionario.  
Estas son algunas de las plataformas más interesantes para poder participar de programas (públicos y privados) de Bug Bounty, y cobrar dinerito, o simplemente ganar reputación.  

- Hackerone [https://www.hackerone.com/]
- Intigriti [https://www.intigriti.com/]
- Bugcrowd [https://www.bugcrowd.com/]


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

### HackerOne Top Reports  
https://github.com/reddelexc/hackerone-reports  


---

## :wrench: Herramientas y Notas separadas  
Para que esté todo más ordenado hice archivos y secciones separadas:  
  

* [Recon](recon.md)  

* [Vulnerabilidades](vulnerabilities.md)  
   
* [Herramientas](tools.md)  

* [Popurri Varios](popurri.md)  

* [Payloads](payloads.md)  

* [HackTheBox](htb.md)  

* [Metodologías](methodologies.md)  

* [Capacitación y Certificaciones](training.md)  

* [CheetSheets](cheetsheets.md)  

* [OneLiners](oneliners.md)  

