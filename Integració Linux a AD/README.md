# Afegir Linux a Active Directory  
## [Eduard Gordo Cebria](mailto:eduard.gordo@mataro.epiaedu.cat)

![image1](IMG/1.png)

Creem els usuaris de linux per la nostra màquina Zorin OS i afegim un grup de seguretat, on haurem de posar els usuaris que vulguem que estiguin dintre per aplicar permisos i treurels a tots els usuaris que és trobin dons del grup de seguretat

---

![image2](IMG/2.png)

Comprovem la IP de l’adaptador 0 del servidor

---

![image3](IMG/3.png)

Assignem en IPv4 de la màquina Zorin el DNS del servidor, apliquem els canvis i continuem

---

![image4](IMG/4.png)

Comprovem fent ping tant al servidor com al domini que funciona correctament la conexió  

---

![image5](IMG/5.png)

Instal·lem els paquets de active directory per a zorin

---

![image6](IMG/6.png)

Canviem el nom del Hostname en la màquina i li posem el domini del servidor

---

![image7](IMG/7.png)

Amb la comanda “realm discover” comprovem que la màquina troba correctament el domini i fa la connexió amb el servidor. Seguidament, amb la comanda “join”, unirem el dospositiu al domini, i si ens deixa continuar sense problemes vol dir que ens hem unit al domini correctament   

---

![image8](IMG/8.png) 

Com podem veure, només completar aquests passos, en la carpeta de AD “Computers” ja ens apareix el nou dispositiu

---

![image9](IMG/9.png)  

Afegim la configuració perque quan un usuari del Active Directory es connecti al client Zorin per primer cop es definiexi a la carpeta personal  

---

![image10](IMG/10.png)

Seguidament iniciem sessió amb l’usuari que hem creat dins de la carpeta de linux

---

![image11](IMG/11.png)

En posar la contrasenya de l’usuari ja ens sortirà el missatge de “creando directorio /home/…” I es crearà la carpeta personal de l’usuari directament gràcies a la configuració previa que li hem assignat

---

![image12](IMG/12.png)

Si posem “id” podrem veure que l’usuari pertany al domini  

---

![image13](IMG/13.png)

Tornem a iniicar sessió amb l’usuari administrador de la màquina i creem el fitxer del sudoers. Afegim en aquest fitxer el grup dels usuaris que estiguin dins del grup de linux en el domini

---

![image14](IMG/14.png)

Ara, en tornar a iniciar sessió, podrem comprovar que l’usuari es converteix en administrador i podem executar amb exit la comanda “sudo su”

![image15](IMG/15.png)

Podem treure i posar permisis a qualsevol grup oa  tothom directament amb l’usuari  

---

![image16](IMG/16.png)

Instal·lem el paquet de “smb”

---

![image17](IMG/17.png)

Anem al explorador d’arxius i busquem el directori del servidor en la pestanya de “Otras Ubicaciones”  

---

![image18](IMG/18.png)

Si hem fet la configuració i la instal·lació bé ens hauria de srtir correctament el directori del servidor, pero com que no tenim permisos d’administrador dels servidor no podrem entrar en totes les carpetes, pero si que podrem accedir a algunes d’elles

I amb aixo Finalitza la pràctica
