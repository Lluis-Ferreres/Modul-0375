# Teoria sobre DHCP
## DHCP: definició
DHCP és un protocol que permet assignar IPs a equips de forma automatitzada, sense la intervenció de l'usuari configurant els dispositius de xarxa. Un servei centralitzat s'encarregarà d'assignar les IPs complint amb les característiques que l'administrador de xarxa decideixi.  
DHCP deriva del protocol [BOOTP](https://en.wikipedia.org/wiki/Bootstrap_Protocol "Wikipedia") (Bootstrap Protocol)

**DHCP** són les inicials de **D**ynamic **H**ost **C**onfiguration **P**rotocol

El protocol DHCP utilitza els ports 67/UDP pel servidor i el 68/UDP pel client

## Funcionament del DHCP
Per comprendre el funcionament del protocol DHCP, hem de saber com assignar adreces IP als equips que s'han de connectar a una xarxa.

**Mètodes d'assignació d'adreces IP**
1. *Assignació manual o estàtica*: s'assigna una IP que no variarà amb el temps. Això s'aconsegueix enllaçant l'adreça MAC de la interfície de xarxa amb aquesta IP.
2. *Assignació automàtica*: s'assigna una IP de forma permanent, però sense la necessitat d'associar-la amb l'adreça MAC. Es pot aconseguir quan es disposa de gran quantitat d'adreces disponibles. Exemple: quan el router de casa assigna una IP als dispositius locals que s'hi connecten
3. *Assignació dinàmica*: s'assigna una IP de forma temporal, en cas de necessitat es sol·licita una renovació i es rebrà una nova IP. Exemple: quan el router de casa rep una IP del proveïdor de serveis d'Internet.

**Paràmetres que es poden assignar**
* Adreça IP
* Porta d'enllaç
* Adreça del servidor DNS
* Nom DNS
* Màscara de subxarxa
* Adreça de broadcast o difusió
* Temps de concessió
* MTU (Unitat de transferència màxima) per la interfície
* Servidors NIS (Servei d'informació de xarxa)
* Dominis NIS
* Servidors NTP
* Servidor SMTP
* Servidor TFTP
* Nom del servidor WINS

**Funcionament**
1. Un client envia una petició broadcast a la xarxa per localitzar un servidor DHCP. Aquest és un missatge **DHCPDISCOVER**
2. Si hi ha servidors a la xarxa, li enviaran com a resposta un missatge **DHCPOFFER** al client per a que seleccioni una IP disponible
3. El client en rebre la resposta, envia un missatge **DHCPREQUEST** d'acceptació també per difusió a tots els equips de la xarxa indicant que ha acceptat una de les IPs disponibles
4. El servidor que li ofereix l'adreça respon que pot utilitzar aquesta adreça mitjançant un missatge **DHCPACK**, indicant també durant quan de temps pot utilitzar aquesta adreça
5. Quan el client s'ha de desconnectar, envia un darrer missatge **DHCPRELEASE** per alliberar la IP. Aquest missatge es produeix pel final del temps de concessió o bé per apagada de l'equip

## Avantatges d'utilitzar DHCP
* Evita haver d'anar dispositiu per dispositiu configurant la xarxa
* Evita introduir errades a les dades de configuració
* Evita repetir IPs assignades al mateix temps
* El manteniment i la càrrega de gestió de la xarxa disminueix

En algunes ocasions **és important** garantir certes IPs, per això es posen manualment les associades a servidors.

**Inconvenients d'utilitzar DHCP**  
No tot són avantatges, però aquests superen als inconvenients en moltes situacions.
* Augmenta el trànsit de difusió a la xarxa
* Cal estudiar la càrrega de treball dels servidors DHCP per donar un bon servei a tots els equips que depenen d'ells
* DHCP és un servei crític i s'ha de protegir d'atacs per evitar que els equips de l'empresa es quedin sense connexió a la xarxa, amb les pèrdues econòmiques que pot comportar-

**Adreces APIPA**  
El protocol APIPA (Automatic Private Internet Protocol Addressing) assigna una IP de forma automàtica quan no es pot comunicar o aconseguir una IP des d'un servidor DHCP.

Les adreces estan compreses entre 169.254.0.1 i 169.254.255.254 amb màscara de classe B 255.255.0.0, el que permet generar una xarxa local temporal. Cada 5 minuts el client intentarà aconseguir una IP de la xarxa.

Amb Windows es fa de forma automàtica, amb Linux s'ha de configurar un paquet anomenat avahi-autoipd.

## Ampliació de continguts
Agraïments a les següents webs:  
[Apunts sobre DHCP](https://www.profesordeinformatica.com/servicios/dhcp/introduccion "Apunts")  
[Més sobre DHCP](https://www.fpgenred.es/DHCP/index.html "Formació Professional")  
[DHCP](https://es.wikipedia.org/wiki/Protocolo_de_configuraci%C3%B3n_din%C3%A1mica_de_host "Wiki")
