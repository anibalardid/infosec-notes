# Notas sobre InfoSec
Este documento va sobre notas acerca de seguridad en aplicaciones web, pentesting y bug bounty.
El documento es en Español, dado que hay poca info en nuestro idioma.

>Aclaraciones: El objetivo de este documento es tener ordenadas notas para poder testear vulnerabilidades en aplicaciones webs. NO es sobre hackeo malicioso. Es para poder testear aplicaciones propias o participar de programas de Bug Bounty.

>Colaboraciones: En caso de querer colaborar se pueden enviar pull/merge request en este mismo repositorio.

## Diccionario
Algunas frases o palabras pueden confundir al principio. Por lo cual acá dejo algunas para no perderse en el documento. Algunas están explicadas con palabras mias para que sean de facil entendimiento.

- Pentesting: Prueba de intrusión de sistemas
- Bug bounty: Busqueda de fallas de seguridad y errores
- Blue team: Equipo especializado en prevenir ataques
- Red team: Equipo enfocado al ataque
- Purple team: Equipo mixto entre blue y red 
- Write-Ups: Posts, o papers de gente que escribe el paso a paso de como encontró una vulnerabilidad.
- OWASP: Es un proyecto de código abierto dedicado a determinar y combatir las causas que hacen que el software sea inseguro. (https://owasp.org/ , https://wiki.owasp.org/images/5/5e/OWASP-Top-10-2017-es.pdf )

## Laboratorios

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

## Vulnerabilidades
Para conocer el TOP 10 de vulnerabilidades, de que se tratan, ejemplos, etc. Lo mas recomendable es inicial con la página de OWASP, mas especificamente el TOP 10 de OWASP.
https://wiki.owasp.org/images/5/5e/OWASP-Top-10-2017-es.pdf


## Cursos, tutoriales

https://portswigger.net/web-security/all-materials


## Plataformas de Bug Bounty

- Hackerone [https://www.hackerone.com/]
- Bugcrowd [https://www.bugcrowd.com/]
- Intigriti [https://www.intigriti.com/]


