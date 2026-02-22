# Servidors web
## Protocol HTTP
Hypertext Transfer Protocol: es tracta d'un protocol que permet la transferència d'informació en format hipertext, text, imatges, vídeos, documents, fitxers, etc. entre un client (navegador web) i un servidor web mitjançant el **port 80**.  

*Hipertext és una forma de premetre accedir a informació extra seleccionant una paraula o text definit amb aquesta característica, el que es coneix com a link o hiperenllaç*.  

**HTTPS** és una versió millorada que aporta seguretat amb xifrat SSL/TLS (Secure Socket Layer i Transfer Layer Security). En aquest cas s'utilitza el **port 443** i és el nou estàndar per a les pàgines web actualment, grans empreses ja no permeten utilitzar http per defecte per temes de seguretat.

## Tipus MIME
Al principi les pàgines web només permetien compartir text. Actualment les pàgines mostren text però també imatges, so, vídeos, etc. Per aconseguir aquesta funcionalitat s'utilitza el tipus MIME.

**M**ultipurpose **I**nternet **M**ail **E**xtensions és una solució que, implementada en primera instància en el servei de correu, permetia l'adjunció d'elements que no es codificaven en format ASCII per la seva transferència. Els tipus MIME els defineix l'organisme **IANA**.

Es poden consultar en aquestes rutes:  
GNU/Linux: /etc/mime.types  
Windows: C:\Windows\System32\drivers\etc\mime.types

Exemples: text/html per una pàgina web, text/css per un full d'estils, video/mpeg per un vídeo en format mpeg.

Quan s'utilitzen els tipus MIME
- Per informar al navegador del tipus de dades que rep el servidor (**Content-type**)
- Visualitzar un document (exemple text/html)
- Cridar a una aplicació externa (exemple application/pdf)
- Consultar a l'usuari si no el servidor no sap resoldre com accedir a la informació (exemple application/abb)
- També per permetre o denegar contingut (exemple Allow: application/doc permet accedir a documents)
- Permet encapsular un o més objectes dintre del cos dels missatges (exemple multipart/form-data que permet utilitzar el mètode POST per pujar una imatge a un servidor)

## Adreces web
El que s'anomena navegar per la xarxa consisteix en localitzar recursos ubicats en diferents servidors. Cada equip s'identifica per una adreça IP, però recordar totes les adreces que necessitem per treballar o localitzar el que es necessita es fa pràcticament impossible de gestionar per un ésser humà. En aquest moment entra a formar part de la identificació el servidor DNS, que ajudarà a recordar els llocs que necessitem visitar mitjançant paraules (noms de domini) associades a les adreces IP que identifiquen els servidors realment.  
La identificació del recurs dintre d'un servidor rep el nom de **URL** o **U**niform **R**esource**L**ocator, informalment anomenada adreça web. Exemple: [https://esteveterradas.cat](https://agora.xtec.cat/iesesteveterradas/ "Web del centre Esteve Terradas i Illa")

URL: Esquema://userinfo@domini:Port/cami?Query
- Esquema: protocol que s'utilitza (http, https, ftp)
- userinfo: dades d'autenticació de l'usuari
- Domini: FQDN o adreça IP on localitzar el recurs
- Port: el port que s'utilitzarà per realitzar la connexió
- Camí: ruta on localitzar el recurs dintre del servidor
- Query: dades que es poden enviar per aconseguir resoldre una consulta i cercar millor el recurs


*Apunts en desenvolupament*

## Més informació
Agraïments a les següents webs:  
[Teoria sobre servidors Web](https://www.profesordeinformatica.com/servicios/http/introduccion "Ampliació de coneixements")  
[Descripció de MIME](https://en.wikipedia.org/wiki/MIME "Wikipedia")
