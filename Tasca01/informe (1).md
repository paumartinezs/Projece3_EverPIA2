# 

# **Informe: Ús d’un Gestor de** 

#                        **Contrasenyes a EverPia**

                                                                                                                             **Nom:** Pau Martínez Sierra  
                                                                                                                              **Curs:** 2b  
		                                                                                                              **Mòdul:** Seguretat Informàtica   
	                                                                                                              **Link doc:** Drive  
                                                                                                                             **Data**: 21/10/2025

ÍNDEX

1. Introducció i Justificació

2. Comparativa Tècnica: Realitzeu una taula comparativa detallada

3. Avantatges i Inconvenients: 

4. Recomanació:

**Fase 1: Anàlisi i Justificació** 

### **1\. Introducció**

EverPia ha patit una fuita d’informació perquè un compte tècnic tenia una contrasenya feble o repetida.  
 Aquest tipus d’errors faciliten atacs com diccionari, brute force o credential stuffing.  
 Per evitar-ho, la direcció ha decidit que tot el personal tècnic ha d’utilitzar un gestor de contrasenyes.

Un gestor de contrasenyes:

- Guarda totes les contrasenyes de forma xifrada i segura.  
- Genera contrasenyes fortes i diferents per a cada compte.  
- Permet accedir-hi des de qualsevol dispositiu.

Així es redueix molt el risc d’atacs i filtracions.

**2\. Comparativa entre opcions**

| Característica | Bitwarden (Online / Núvol) | KeePassXC (Offline / Local) |
| ----- | ----- | ----- |
| **On guarda les contrasenyes** | Al núvol (o servidor propi) | En un fitxer local (.KDBX) |
| **Xifratge** | AES-256 end-to-end | AES-256 local |
| **Codi font** | Obert (auditat) | Obert (comunitari) |
| **Sincronització** | Automàtica entre dispositius | Manual (copiant el fitxer) |
| **Accés multiplataforma** | Web, mòbil, PC, navegador | PC (Windows, Linux, Mac) |
| **Autenticació en dos passos (2FA)** | Sí, integrada | Sí, però amb plugins |
| **Compartir credencials amb companys** | Fàcil (carpetes compartides) | Manualment (fitxers) |
| **Cost** | Gratuït amb opcions premium | Totalment gratuït |
| **Internet necessari** | Sí, per sincronitzar | No |
| **Facilitat d’ús** | Molt fàcil i intuïtiu | Més tècnic |

### **4\. Pros i contres**

#### **Bitwarden**

**Avantatges:**

- Sincronitza automàticament entre tots els dispositius.  
- Té 2FA i és fàcil de fer servir.  
- Interfície moderna i clara.  
- Codi obert i segur.  
- Es pot instal·lar en servidors propis.

**Inconvenients:**

- Necessita connexió a Internet per sincronitzar.  
- Algunes funcions són de pagament.  
- Depèn del núvol (encara que estigui xifrat).

#### **KeePassXC**

**Avantatges:**

- Tot queda al teu ordinador, sense enviar res al núvol.  
- 100% gratuït i de codi obert.  
- Molt segur si es combina amb un fitxer de clau (keyfile).  
- Ideal per entorns tancats o sense connexió.

**Inconvenients:**

- No sincronitza automàticament.  
- Cal saber una mica més per configurar-lo.  
- No és tan pràctic per compartir contrasenyes entre equips.

