# **T04: Serveis de directori. LDAP**

## **3.1. Instal·lació i Configuració Base d'OpenLDAP**

![][image1]

Un cop dins de la màquina, canvia el nom del server.

![][image2]

Entra en la configuració del domini per canviar el nom.

![][image3]

Canvia el nom com surt en pantalla, “server.innovatech253.test”

![][image4]

Comprovem que el nom del domini ha canviat utilitzant “**hostname \-f**”

![][image5]

afegeix una segona interfície privada “Host-Only”

![][image6]

Per instal·lar el OpenLDAP utilitza aquest codi.

![][image7]

Introdueix la contrasenya d'administrador, en el meu cas usuari

![][image8]

Introdueix un altre cop la contrasenya d'administrador.

![][image9]

Per veure l'estat del slapd utilitza el codi mostrat en la captura

![][image10]

Per comprovar que el directori s’ha creat amb el nom que volem, utilitza “**Sudo slapcat**” i ens sortirà el nom del directori **“innovatech18.test”**

**![][image11]**

**![][image12]**                

**![][image13]**

## **3.2. Gestió i Administració (LAM)**

**![][image14]**

Instal·larem directament el paquet del gestor

![][image15]

Utilitza la “**Ip a**” per mirar la IP de la enp0s8.

![][image16]

Ara posa la ip \+ **“/lam/templates/login.php”** per entrar dintre.

![][image17]  
Clica a **“LAM configuration”**.

![][image18]

Ara clica a **“Edit server profiles”**

![][image19]

Si vols canviar el password o crear un nou perfil, ves a **“Manage server profiles”** 

![][image20]

La contrasenya és la mateixa que el nom del perfil **“lam”**

![][image21]  
Canvia la configuració del server com surt a la pantalla.

![][image22]

També canvia la de **“Tool”**  
![][image23]

Canvia la configuració del **“users”** i dels **“grups”** com a la captura de la pantalla.

![][image24]

Contrasenya **“usuari”**

![][image25]

Entra a **“groups”.**

![][image26]

![][image27]  
Crea un nou grup.

![][image28]  
Posa de nom al grup **“Manager”**

![][image29]  
Crea un nou usuari.

![][image30]

Posal·li de last name **Tech01** i entra a **“Unix”**

![][image31]  
Posal·li de nom **“Tech01**” i a UID number posa 10000

![][image32]

Crea un altre user amb el last name de **“manager01”**

![][image33]  
Entra a **“unix”**, posa de nom **“manager01”** i a UID número posa **10001**

![][image34]  
Afageix·li una contrasenya a l’usuari **“manager01”** 

## **4\. Integració de Client (Client Ubuntu Desktop)**

![][image35]

Entra amb una màquina de Zorin i posa de segona interfície host only.

![][image36]

Entra a la carpeta de **/etc/hosts** per canviar el nom del domini.

![][image37]

Canvia el nom del domini.

![][image38]

Comprova que el nom del domini és correcte.  
![][image39]

Utilitza la comanda **“dig”** per comprovar que els noms funcionen correctament.

![][image40]

Instal·la **“lDAP”**

![][image41]

Canvia el nom perquè sigui el mateix que el domini i també borra una línia si no, no funcionarà la instal·lació

![][image42]

Canvia com surt a la captura de pantalla

![][image43]

Prem **“3”**

![][image44]

Prem **“Si”** perquè l’usuari root pugui canviar les contrasenyes del LDAP

![][image45]

Prem **“no”**

![][image46]

Canvia com surt a la captura

![][image47]

Utilitza la teva contrasenya en el meu cas **“usuari”.**

![][image48]

Copia aquest comanda per comprovar sí el client conecta amb el servidor.  
![][image49]

 Configurem l'arxiu **nsswitch.conf** per indicar que s'usarà LDAP per usuaris i grups.

![][image50]

Canvia la configuració com surt a la imatge.

![][image51]

Utilitza aquesta comanda per entrar a l'arxiu **“/etc/pam.d/common-password**”.  
elimina  la línia el terme **“use authtok.”**

![][image52]

![][image53]

Ara edita l'arxiu **/etc/pam.d/common-session** i afegeix la línia marcada en vermell  per crear els perfils.

![][image54]

Utilitza aquesta comanda per reiniciar el servei **nscd.**

![][image55]

Comprova que els usuaris es veuen al LDAP  
 

![][image56]

ara edita l'arxiu indicat, per permetre l'inici de sessió

![][image57]

Copia el mostrat a la captura de pantalla.  
![][image58]

Reincia la màquina virtual i inicia sessió amb l’altre usuari.

![][image59]

Posa **“manager01”**

![][image60]

Introdueix la contrasenya que has introduït anteriorment al **“LAM”**

![][image61]

Un cop dins de la màquina virtual amb l’altre usuari, entra a la terminal

![][image62]

Un cop iniciem sessió, comprovem com se li ha creat la carpeta personal i comprovem l'usuari amb la comanda **“id”**
