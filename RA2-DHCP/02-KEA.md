## Servidor KEA de DHCP

**ISC** o Internet Systems Consortium és una corporació sense ànim de lucre que promou el suport universal a la infraestructura d'Internet.

**Kea DHCP** és el nou desenvolupament de la corporació **ISC** que substitueix el seu anterior servidor **ISC DHCP** (*tot i que en alguns entorns encara funciona, es recomana actualitzar a Kea doncs el suport oficial a ISC DHCP finalitzava l'any 2022*) afegint diverses millores:

1. Disseny modular: permet afegir o treure allò que sigui necessari o no, a més de poder afegir millores en un futur si es generen nous mòduls i noves funcionalitats.
2. Es permet la reconfiguració del servidor Kea mitjançant API REST.
3. Fàcil integració amb els sistemes existents, permetent actualitzar de l'antiga versió de servidor DHCP a Kea. Fins i tot disposa d'eines de migració d'un servidor a Kea. A més a més, el suport de la gestió per base de dades millora la seguretat i el rendiment del servidor, així com l'estratègia de resiliència (*recuperar el funcionament normal després de situacions crítiques o atacs*).
4. Gestió gràfica via web amb l'eina Stork. Permet monitorar amb més facilitat el funcionament dels servidors DHCP dintre de l'empresa.
5. Implementat d'acord a les millores tecnològiques més actuals per un alt rendiment.

## Instal·lació a Rocky Linux
Per a que funcioni correctament ens assegurarem de tenir el següent instal·lat (tot amb **sudo** o convertit a **root**):  
Refrescar els repositoris (ho podem veure com un apt update a Debian/Ubuntu)  
`dnf makecache --refresh`  
Cercar actualitzacions:  
`dnf check-update`  
Instal·lar compatibilitat i repositoris que solen aparèixer a Red Hat:  
`dnf install epel-release -y`  
Comoditat per utilitzar la shell, autocompletar al prompt mitjançant el tabulador:  
`dnf install bash-completion -y`  
Finalment, instal·lar kea:  
`dnf install kea-dhcp`

**Exemple de configuració**  
`{ `  
` # DHCPv4 configuration starts on the next line`  
`"Dhcp4":`  
`    { `  
` # First we set up global values`  
`      "valid-lifetime": 4000,`  
`      "renew-timer": 1000,`  
`      "rebind-timer": 2000,`  
` # Next we set up the interfaces to be used by the server.`  
`       "interfaces-config": {`  
`            "interfaces": [ "enp0s9" ]`  
`            },`  
` # And we specify the type of lease database`  
`       "lease-database": {`  
`            "type": "memfile",`  
`            "persist": true,`  
`            "name": "/var/lib/kea/dhcp4.leases"`  
`          },`  
` # Finally, we list the subnets from which we will be leasing addresses.`  
`       "subnet4": [`  
`            {`   
`               "id": 1,`  
`               "subnet": "172.16.201.0/24",`  
`               "pools": [`  
`                   {`  
`                        "pool": "172.16.201.1 - 172.16.201.30"`  
`                   }`  
`               ]`  
`            }`  
`       ]`      
` # DHCPv4 configuration ends with the next line`  
`    }`    
`  }`

*Apunts en desenvolupament*

## Ampliació de coneixements
Agraïments a les següents webs:  
[Wiki ISC](https://en.wikipedia.org/wiki/Internet_Systems_Consortium "ISC")  
[Web oficial](https://www.isc.org/kea/ "KEA")  
[Configuració KEA](https://www.server-world.info/en/note?os=Rocky_Linux_10&p=dhcp&f=1 "Configuració Rocky 10")
