| Curs: | CFGM Sistemes Microinformàtics i Xarxes |
| :---- | :---- |
| Matèria: | 0224 Sistemes Operatius en Xarxa |
| Tema | UD10. Samba |
| Professor/s: | C. Alonso, C. Fugarolas |
| Alumne: | Edu Gordo Cebrià |

# **UD10. Servidor de fitxers amb Samba**

## Per fer aquesta activitat necessiteu:

* Zorin com màquina Linux.  
* Windows 11

## **Exercici 1: Instal·lació i configuració de SAMBA**

1. Instal·la el servei de SAMBA.

![Imatge1](IMG/1.png)
![Imatge2](IMG/2.png)
![Imatge3](IMG/3.png)

2. Crea les carpetes **/srv/samba/publica** i **/srv/samba/compartida** amb propietat root i el grup **sambashare**. Mostra les carpetes creades i amb la propietat corresponent. Tant el usuari com el grup han de poder escriure (permisos 770)

![Imatge4](IMG/4.png)
![Imatge5](IMG/5.png)

3. Crea tres usuaris: **samba1, samba2 i samba3.** Els tres usuaris han de tenir carpeta personal, no han de poder iniciar sessió local i han de pertànyer al grup **sambashare**.

![Imatge7](IMG/7.png)
![Imatge8](IMG/8.png)

4. Afegir els tres usuaris a samba.

![Imatge9](IMG/9.png)

Canvia el nom a l’arxiu **/etc/samba/smb.conf** i crea un de nou buit.

![Imatge10](IMG/10.png)

---

## **Exercici 2: Accés a carpeta pública en mode anònim**

1. Configura el fitxer smb.conf per tal que el directori /**srv/samba/publica** sigui accessible per a tots de forma anònima, però només lectura. Comprova amb testparm la sintaxi un cop escrites les configuracions.

![Imatge11](IMG/11.png)
![Imatge12](IMG/12.png)

Crea-hi alguns arxius de text dins el directori i comprova que qualsevol usuari hi pot accedir i llegir aquests arxius, sense autentificar-se, però sense poder modificar-los.

![Imatge13](IMG/13.png)

---

## **Exercici 3: Carpetes personals**

1. Afegir al fitxer smb.conf anterior el que calgui perquè qualsevol usuari (de Linux i Samba) pugui accedir al seu directori personal del servidor Linux amb tots els permisos possibles.

![Imatge14](IMG/14.png)

2. Comprova-ho amb usuari1.

![Imatge15](IMG/15.png)
![Imatge16](IMG/16.png)

---

## **Exercici 4: Unitats compartides**

1. Configurar smb.conf per tal que **/srv/samba/compartida** sigui accessible per **usuari1** en mode lectura/escriptura i **usuari2** només lectura. **L'usuari3** no ha de tenir accés.

![Imatge17](IMG/17.png)

2. Comprova l’accés (lectura/escriptura) pels tres usuaris.

![Imatge18](IMG/18.png)  
![Imatge19](IMG/19.png)

3. Crea un arxiu amb extensió .**zip** dins el directori i configura smb.conf per tal que no es pugui accedir a arxius .zip des dels clients. Comprova des de l’equip Windows si es pot veure l’arxiu.

![Imatge20](IMG/20.png)
![Imatge21](IMG/21.png)
![Imatge22](IMG/22.png)
![Imatge23](IMG/23.png)

## **EXERCICI 5: Samba des de Windows 11 a Linux**

Per accedir als recursos SAMBA des de l’explorador de Zorin cal instal·lar el paquet:

*python3-smbc*  

![Imatge24](IMG/24.png)

1. Crea una carpeta a la màquina Windows 11 i comparteix-la de manera que tothom hi pugui accedir en mode lectura.

![Imatge25](IMG/25.png)
![Imatge26](IMG/26.png)
![Imatge27](IMG/27.png)
![Imatge28](IMG/28.png)
![Imatge29](IMG/29.png)

2. Comprova des de l’equip Zorin que es pot accedir al recurs de la màquina Windows.

![Imatge30](IMG/30.png)
![Imatge31](IMG/31.png)
![Imatge32](IMG/32.png)
