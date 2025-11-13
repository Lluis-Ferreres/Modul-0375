## Eines per treballar amb DNS
* whois: ens permetrà conéixer informació sobre dominis registrats. Algunes dades no es publiquen per temes de seguretat i evitar així possibles atacs.
* nslookup: eina per comprovar el correcte funcionament del servidor DNS
* dig: una altra eina per comprovar el correcte funcionament del servidor DNS
* webmin: eina per administrar via web un servidor. Funciona força bé amb el servei BIND9
* bind9: servei DNS. Cal instal·lar els paquets bind i bind-utils per tenir el servei i les eines de gestió i comprovació. El servei s'anomena named i es pot consultar el funcionament amb systemctl status named.

## Exemples d'ús
* Comprovar la informació sobre un domini públic:  
**whois empresa.tld**

* Utilització de nslookup  
  - Fer una cerca amb informació addicional (utilitzarem el paràmetre debug):  
**nslookup debug domini.tld**

  - Per assegurar-se que s'utilitza un servidor DNS en concret s'identifica amb la seva IP:  
**nslookup domini.tld IP-servidor**

* Utilització de dig  
  - Per assegurar-se que s'utilitza un servidor DNS en concret s'identifica amb la seva IP:  
**dig @IP-servidor domini.tld**

  - Retornar tota la informació (registres) sobre un domini:  
**dig ANY domini.tld**

  - Mostra per quins servidors passa la informació fins que s'aconsegueix resoldre la IP:  
**dig -trace domini.tld**

  - Resolució inversa:  
**dig -x domini.tld**
