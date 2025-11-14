# **T03: Gestió flexible de discos** 

## **(LVM i Espais d’emmagatzematge)**

En primer lloc, crea 2 discos virtual des de paràmetres.

![imagen](Tasca03_projecte3_01_01.png)

Ara instal·lem el fdisk per comprovar si tenim els dos discos de 10 GB 

![imagen](Tasca03_projecte3_01_02.png)

Utilitza aquesta comanda per fer la comprovació “sudo fdisk -l”

![imagen](Tasca03_projecte3_01_03.png)

![imagen](Tasca03_projecte3_01_04.png)

![imagen](Tasca03_projecte3_01_05.png)

Ara és el moment de generar els volums físics utilitzant l’ordre pvcreate, aplicada sobre les particions que vulguem convertir en PV.

![imagen](Tasca03_projecte3_01_06.png)

![imagen](Tasca03_projecte3_01_07.png)

Més endavant es poden incorporar nous volums o bé eliminar-ne alguns.

![imagen](Tasca03_projecte3_01_08.png)

Es poden afegir volums nous utilitzant tot el seu espai disponible o només una porció.

![imagen](Tasca03_projecte3_01_09.png)

Amb vgdisplay podem consultar les propietats i informació del grup de volums.

![imagen](Tasca03_projecte3_01_10.png)

Els volums lògics es generen a partir del VG, especificant-ne la mida, el grup de volums i el nom que volem assignar.

![imagen](Tasca03_projecte3_01_11.png)

Si executem la comanda vgdisplay, veurem que ara l’espai ja apareix marcat com a ocupat.

![imagen](Tasca03_projecte3_01_12.png)

Els volums lògics (LV) actuen com si fossin particions; per tant, per fer-los servir cal formatar-los amb un sistema de fitxers.

![imagen](Tasca03_projecte3_01_13.png)

Per poder utilitzar el volum lògic, hem de muntar-lo amb la comanda mount cap al directori creat prèviament.

![imagen](Tasca03_projecte3_01_14.png)

També és necessari modificar l’arxiu /etc/fstab.

![imagen](Tasca03_projecte3_01_15.png)

Per ampliar un volum, la nova mida s’indica amb l’opció -L.

![imagen](Tasca03_projecte3_01_16.png)

![imagen](Tasca03_projecte3_01_17.png)

A continuació s’ha d’actualitzar el sistema de fitxers amb resize2fs per aprofitar l’espai afegit, i es pot verificar amb df -h.

![imagen](Tasca03_projecte3_01_18.png)

Aquesta comanda mostra els volums físics existents i indica si estan associats a algun grup de volums.

![imagen](Tasca03_projecte3_01_19.png)

Aquesta ordre permet visualitzar els grups de volums disponibles i el nombre de volums físics que en formen part.

![imagen](Tasca03_projecte3_01_20.png)

Crearem alguns fitxers dins del lv01.

![imagen](Tasca03_projecte3_01_21.png)

Ara generarem la instantània (snapshot).

![imagen](Tasca03_projecte3_01_22.png)

Podem comprovar els dos LV creats i observar com la instantània apunta al volum original.

![imagen](Tasca03_projecte3_01_23.png)

Muntem la còpia per revisar-ne el contingut.

![imagen](Tasca03_projecte3_01_24.png)

Per continuar amb aquesta demostració, eliminarem els volums lògics i el grup de volums creat anteriorment.

![imagen](Tasca03_projecte3_01_25.png)

Crearem un grup de volums utilitzant dos dels volums físics disponibles.

![imagen](Tasca03_projecte3_01_26.png)

A continuació configurarem un sistema de mirall (mirror) senzill.

![imagen](Tasca03_projecte3_01_27.png)

![imagen](Tasca03_projecte3_01_28.png)
