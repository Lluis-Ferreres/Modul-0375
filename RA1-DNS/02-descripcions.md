## Jerarquia del sistema DNS
El DNS és una base de dades distribuïda a diferents servidors.  
El sistema de noms segueix el que s'anomena una estructura jeràrquica en forma d'arbre invertit. Això vol dir que a la part superior trobem el nivell més baix, el **0** on comença tot. Aquest nivell és l'**arrel** i només hi ha 13 servidors arrel (replicats a tot el món) per temes tecnològics. Amb IPv4 no es poen construir paquets que permetin emmagatzemar IPs per més dominis. En canvi amb IPv6 es podrà superar aquesta limitació tècnica i segurament apareixeran més servidors arrel.  
Seguidament trobem el **TLD al nivell 1**.  
Al **nivell 2** es defineix el **domini**.  
Finalment **a partir del nivell 3** es defineixen els **subdominis**.

De moment habitualment no trobarem més de 5 nivells per temes de rendiment. El màxim que permet la ICANN però és de 127 nivells, comptant subdominis i arrel.

Quan tenim definit un domini, utilitzarem el terme FQDN (**F**ully **Q**ualified **D**omain **N**ame) per a referir-nos al mateix. D'aquesta forma queda identificat a la xarxa i podrem accedir si està ben definit al servidor i tenim connectivitat.

## Tipus de servidors
* **Servidor primari**: conté les zones (arxius de definició de dominis) a dintre seu
* **Servidor secundari**: conté una còpia de les zones facilitada pel servidor primari
* **Servidor cau**: no conté informació, s'utilitza per accelerar les cerques d'informació. La primera vegada que es realitza una consulta a un DNS la resposta es pot desar a un servidor cau, el que accelera l'accés a posteriors visites al mateix domini. Per gestionar la validesa de la informació es defineixen els següents valors:
* **TTL** o temps de vida màxim: validesa de la informació a la memòria cau. Quan finalitza aquest temps la consulta es torna a realitzar al servidor primari o secundari corresponent
* Temps d'actualització (**refresh**): temps que utilitza el servidor secundari per sol·licitar una renovació de la informació al servidor primari
* Temps de reintents (**retry**): temps que ha de transcórrer des de que es detecta que el servidor primari està "caigut" fins que es demana la informació a un altre servidor
* Temps de caducitat (**expire**): temps fins que s'esborra la informació de zona del servidor secundari en cas que no hi hagi connectivitat amb el primari o qui li pugui facilitar la informació de zona 

## Registre de recursos (RR)
Dintre de les zones es defineixen els recursos (equips accessibles per IP). Per deixar clar quin tipus d'informació s'està utilitzant, es defineixen diferents tipus de registres.


*Documentació en desenvolupament*
## Més informació
[Limitació de servidors arrel](https://www.lifewire.com/dns-root-name-servers-3971336 "Ampliació de coneixements")  
[Nombre màxim de nivells de domini](https://www.byronvargas.com/web/cuantos-niveles-puede-tener-un-nombre-de-dominio-2/?expand_article=1 "Ampliació de coneixements")
