## Com utilitzar vim (nivell bàsic)

*Nota*: La tecla **ESC** és la que permet canviar els modes de funcionament a l'editor de text vim/vi. Quan aparegui escrita la paraula ESC significa que cal prèmer la tecla ESC del teclat i tot seguit prémer les tecles que segueixen.

### 1. Crear documents

a. Opció 1: des de la terminal escriure directament `vi nom-fitxer`. *Si no es desa el document no es generarà: ESC :w ruta/nom-fitxer*
b. Opció 2: des del mateix vi --> ESC :w *ruta/nom-fitxer*
   
### 2. Modes de funcionament

a. Mode ordres: l'editor de text accepta instruccions a partir del teclat. Per entrar al mode ordres s'ha de prémer la tecla **ESC**

b. Mode darrera línia: és una puntualització del mode ordres, es tracta de prémer **:** i l'acció corresponent (per exemple desar és la w i sortir la q)

c. Mode edició: permet escriure dintre d'un fitxer. S'accedeix a partir del mode ordres, no entra directament en aquest mode. Per exemple es poden utilitzar les tecles **a** (afegir/append) o **i** (inserir/insert) entre altres per començar a escriure.
    
### 3. Combinacions de tecles

Tot seguit anem a veure algunes de les combinacions més utilitzades al vi/vim. *Nota*: cal tenir en compte les majúscules i minúscules, ja que tenen funcions diferents.

* **ESC**: permet canviar el mode de funcionament del vi
* **a**: permet introduir text al fitxer
* **i**: a diferència de la tecla a, en comptes d'afegir després del cursor afegeix el text en la mateixa posició del cursor. No hi ha diferència si la línia és buida o el cursor es troba al final de la línia
* **dd**: esborra la línia on es troba el cursor. Si afegim un nombre al davant s'esborraran tantes línies com indiqui aquest, i ho podem fer a diferents ordres.
* **1G**: porta al principi del document
* **G**: porta al final del document
* **$**: situa el cursor al final de la línia
* **0**: situa el cursor al principi de la línia
* **yy**: copia la línia on es troba el cursor al porta-retalls
* **p**: enganxa el contingut del porta-retalls a la línia de sota d'on es troba el cursor
* **P**: amb la P majúscula el contingut s'enganxa a la línia superior d'on es troba el cursor
* **/cadena**: permet realitzar la cerca d'un text (en aquest cas seria la paraula *cadena*). Si es necessita repetir la cerca, cal prèmer la tecla **n** per anar cap avall o **N** per cercar cap a dalt
* **:w**: permet desar el document si ja té nom, o crear un document si s'especifica la ruta i el nom
* **:q**: surt del vi
* **:wq**: sortir desant els canvis realitzats
* **:q!**: sortir sense desar els possibles canvis
* **:%s/eth1/br1/g**: (cerca a tot el document eth1 i ho substitueix per br1)
* **:%s/eth1/br1/gc**: (demana confirmació per cada aparició)

### Usos més avançats
1. Amb Vim podem crear diferents pantalles dintre de l'editor de text per obrir diferents fitxers, realitzar comparacions, etc. Per aconseguir-ho utilitzarem les següents combinacions de tecles:

**Divisió vertical**

Ctrl w v  
:vs  
Ctrl w l  
Ctrl w h  
Ctrl w j  
Ctrl w k  

**Divisió horitzontal**

Ctrl w s  
:sp  
Ctrl w j  
Ctrl w k  

**Canviar la posició de les finestres**

Ctrl w r  
Ctrl w R  

**Tancar split**

Ctrl w q  
Ctrl w c  


2. Per modificar diferents línies al mateix temps (per exemple per afegir un nombre d'espais al principi de la línia):  
Activar mode visual amb Ctrl v    
Prémer 3j  
Prémer I (lletra i majúscula)  
*Text a afegir* (text que volem escriure, per exemple un espai en blanc, que només surt a la primera línia, fins que es prem ESC)  
Prem ESC

3. També es pot desar un document que s'ha de modificar com a sudoer però ens hem oblidat de posar sudo abans d'obrir vi. Es pot solventar així:
**:w !sudo tee %**
