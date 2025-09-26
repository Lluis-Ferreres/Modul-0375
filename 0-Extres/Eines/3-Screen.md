### Screen

L'eina **screen** permet que es puguin generar sessions sobre un equip informàtic a les quals es pot accedir de forma remota si s'escau, permetent desconnectar-se d'elles sense perdre els processos en execució que n'haguem llançat.

És també una forma de poder gaudir de múltiples sessions en un entorn de text, el qual podria estar limitat a una sola pantalla de text, el que ens permetria realitzar diferents tasques al mateix temps. Una altra possible utilització és la de permetre una connexió remota a un usuari i que aquest vegi el que s'està escrivint i executant en aquesta sessió, seria una forma de gestió o control remot per poder ajudar a resoldre incidències de forma no presencial o una pissarra virtual per fer classes. Veiem com utilitzar-ho.

### Utilització de l'eina de gestió de sessions screen
#### Instal·lació

Si es disposa de la distribució Ubuntu:  
`sudo apt update; sudo apt install screen -y`

OpenSuSE:  
`sudo zypper in screen -y`

Rocky Linux:  
`sudo dnf install screen`

Arch:  
`sudo pacman -Syu screen`

#### Creació de sessions
Es poden generar sessions desde la terminal de forma genèrica o amb un nom (millor opció per identificar després cada sessió amb més facilitat). Dintre de cada sessió es poden definir finestres per treballar més còmodament. Aquestes finestres es poden reorganitzar i mostrar-les per pantalla per poder aprofitar al màxim aquesta eina.

**Creació de sessió amb nom**  
`screen -dmS nom-sessio`

**Accedir a la sessió generada**  
`screen -R nom-sessio`

**Desconnectar de la sessió**  
Podem desconnectar la sessió, el que implica que no deixarà d'executar-se allò que haguem posat en funcionament a dintre de la sessió. Més tard podrem tornar a connectar per veure com va la feina.  
`Ctrl a d`

Ens mostrarà un missatge indicant que s'ha desconnectat de la sessió (detached)

**Tornar a connectar a la sessió**  
`screen -R nom-sessio`

Com es pot apreciar, funciona igual que quan ens connectem per primera vegada.

**Tecles per interactuar amb screen**  
Un cop dintre de la sessió creada amb screen, per realitzar diferents tasques hem de prémer una combinació de tecles per poder gaudir-ne dels avantatges d'aquesta utilitat. Per defecte la combinació per activar una ordre a screen és la combinació de la tecla control (**Ctrl**) i la tecla **a**  
Seguidament en mostrem un llistat dels usos més comuns, amb la tecla corresponent (majúscules i minúscules poden tenir usos diferents) i la descripció del que fan:
* Ctrl a c: nova pantalla
* Ctrl a ": ens mostra els noms de totes les finestres disponibles (es pot canviar aquest nom)
* Ctrl a A: canviar el nom de la finestra
* Ctrl a :*sessionname nou-nom* --> canviar el nom de la sessió
* Ctrl a n: passa a la següent pantalla
* Ctrl a S: crea una divisió horitzontal de pantalla
* Ctrl a X: elimina una divisió
* Ctrl a |: crea una divisió vertical (la línia vertical s'aconsegueix amb la tecla **Alt gr** i la tecla **1**)
* Ctrl a Q: tanca una divisió (finestra)
* Ctrl a tab: canvia de pantalla a la divisió
* Ctrl a w: veure les pantalles que disposem
* Ctrl a :*resize nova-mida* --> modifica la mida d'una finestra, si no s'especifica la mida ho pregunta i es pot modificar (exemple --> :resize 20 (canvia la mida a 20 línies))
* Ctrl+A :*focus finestra* --> per finestra escriurem la posició de la mateixa top, bottom, next, prev, left, right, up, down (exemple --> :focus bottom (ens envia a la finestra de sota del tot))

Per tancar la sessió amb exit en podem sortir
