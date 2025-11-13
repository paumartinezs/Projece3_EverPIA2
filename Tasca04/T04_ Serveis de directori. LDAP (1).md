# **T04: Serveis de directori. LDAP**

## **3.1. Instal·lació i Configuració Base d'OpenLDAP**

![imagen](img/Tasca04_1.png)

Un cop dins de la màquina, canvia el nom del server.

![imagen](img/Tasca04_2.png)

Entra en la configuració del domini per canviar el nom.

![imagen](img/Tasca04_3.png)

Canvia el nom com surt en pantalla, “server.innovatech253.test”

![imagen](img/Tasca04_4.png)

Comprovem que el nom del domini ha canviat utilitzant “**hostname \-f**”

![imagen](img/Tasca04_5.png)

afegeix una segona interfície privada “Host-Only”

![imagen](img/Tasca04_6.png)

Per instal·lar el OpenLDAP utilitza aquest codi.

![imagen](img/Tasca04_7.png)

Introdueix la contrasenya d'administrador, en el meu cas usuari

![imagen](img/Tasca04_8.png)

Introdueix un altre cop la contrasenya d'administrador.

![imagen](img/Tasca04_9.png)

Per veure l'estat del slapd utilitza el codi mostrat en la captura

![imagen](img/Tasca04_10.png)

Per comprovar que el directori s’ha creat amb el nom que volem, utilitza “**Sudo slapcat**” i ens sortirà el nom del directori **“innovatech18.test”**

**![imagen](img/Tasca04_11.png)**

**![imagen](img/Tasca04_12.png)**                

**![imagen](img/Tasca04_13.png)**

## **3.2. Gestió i Administració (LAM)**

**![imagen](img/Tasca04_14.png)**

Instal·larem directament el paquet del gestor

![imagen](img/Tasca04_15.png)

Utilitza la “**Ip a**” per mirar la IP de la enp0s8.

![imagen](img/Tasca04_16.png)

Ara posa la ip \+ **“/lam/templates/login.php”** per entrar dintre.

![imagen](img/Tasca04_17.png)
Clica a **“LAM configuration”**.

![imagen](img/Tasca04_18.png)

Ara clica a **“Edit server profiles”**

![imagen](img/Tasca04_19.png)

Si vols canviar el password o crear un nou perfil, ves a **“Manage server profiles”** 

![imagen](img/Tasca04_20.png)

La contrasenya és la mateixa que el nom del perfil **“lam”**

![imagen](img/Tasca04_21.png)
Canvia la configuració del server com surt a la pantalla.

![imagen](img/Tasca04_22.png)

També canvia la de **“Tool”**  
![imagen](img/Tasca04_23.png)

Canvia la configuració del **“users”** i dels **“grups”** com a la captura de la pantalla.

![imagen](img/Tasca04_24.png)

Contrasenya **“usuari”**

![imagen](img/Tasca04_25.png)

Entra a **“groups”.**

![imagen](img/Tasca04_26.png)

![imagen](img/Tasca04_27.png)
Crea un nou grup.

![imagen](img/Tasca04_28.png)
Posa de nom al grup **“Manager”**

![imagen](img/Tasca04_29.png)
Crea un nou usuari.

![imagen](img/Tasca04_30.png)

Posal·li de last name **Tech01** i entra a **“Unix”**

![imagen](img/Tasca04_31.png)  
Posal·li de nom **“Tech01**” i a UID number posa 10000

![imagen](img/Tasca04_32.png)

Crea un altre user amb el last name de **“manager01”**

![imagen](img/Tasca04_33.png)  
Entra a **“unix”**, posa de nom **“manager01”** i a UID número posa **10001**

![imagen](img/Tasca04_34.png)  
Afageix·li una contrasenya a l’usuari **“manager01”** 

## **4\. Integració de Client (Client Ubuntu Desktop)**

![imagen](img/Tasca04_35.png)

Entra amb una màquina de Zorin i posa de segona interfície host only.

![imagen](img/Tasca04_36.png)

Entra a la carpeta de **/etc/hosts** per canviar el nom del domini.

![imagen](img/Tasca04_37.png)

Canvia el nom del domini.

![imagen](img/Tasca04_38.png)

Comprova que el nom del domini és correcte.  
![imagen](img/Tasca04_39.png)

Utilitza la comanda **“dig”** per comprovar que els noms funcionen correctament.

![imagen](img/Tasca04_40.png)

Instal·la **“lDAP”**

![imagen](img/Tasca04_41.png)

Canvia el nom perquè sigui el mateix que el domini i també borra una línia si no, no funcionarà la instal·lació

![imagen](img/Tasca04_42.png)

Canvia com surt a la captura de pantalla

![imagen](img/Tasca04_43.png)

Prem **“3”**

![imagen](img/Tasca04_44.png)

Prem **“Si”** perquè l’usuari root pugui canviar les contrasenyes del LDAP

![imagen](img/Tasca04_45.png)

Prem **“no”**

![imagen](img/Tasca04_46.png)

Canvia com surt a la captura

![imagen](img/Tasca04_47.png)

Utilitza la teva contrasenya en el meu cas **“usuari”.**

![imagen](img/Tasca04_48.png)

Copia aquest comanda per comprovar sí el client conecta amb el servidor.  
![imagen](img/Tasca04_49.png)

 Configurem l'arxiu **nsswitch.conf** per indicar que s'usarà LDAP per usuaris i grups.

![imagen](img/Tasca04_50.png)

Canvia la configuració com surt a la imatge.

![imagen](img/Tasca04_51.png)

Utilitza aquesta comanda per entrar a l'arxiu **“/etc/pam.d/common-password**”.  
elimina  la línia el terme **“use authtok.”**

![imagen](img/Tasca04_52.png)

![imagen](img/Tasca04_53.png)

Ara edita l'arxiu **/etc/pam.d/common-session** i afegeix la línia marcada en vermell  per crear els perfils.

![imagen](img/Tasca04_54.png)

Utilitza aquesta comanda per reiniciar el servei **nscd.**

![imagen](img/Tasca04_55.png)

Comprova que els usuaris es veuen al LDAP  
 

![imagen](img/Tasca04_56.png)

ara edita l'arxiu indicat, per permetre l'inici de sessió

![imagen](img/Tasca04_57.png)

Copia el mostrat a la captura de pantalla.  
![imagen](img/Tasca04_58.png)

Reincia la màquina virtual i inicia sessió amb l’altre usuari.

![imagen](img/Tasca04_59.png)

Posa **“manager01”**

![imagen](img/Tasca04_60.png)

Introdueix la contrasenya que has introduït anteriorment al **“LAM”**

![imagen](img/Tasca04_61.png)

Un cop dins de la màquina virtual amb l’altre usuari, entra a la terminal

![imagen](img/Tasca04_62.png)

Un cop iniciem sessió, comprovem com se li ha creat la carpeta personal i comprovem l'usuari amb la comanda **“id”**
