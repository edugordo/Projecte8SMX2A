# AA5 - Wireshark
## SMX 2A | Edu Gordo Cebrià

---

![Imatge1](IMG/1.png)

Hem seleccionat la interfície **eth0** i hem iniciat la captura de paquets amb Wireshark.

---

![Imatge2](IMG/2.png)

Hem comprovat que la porta d’enllaç és **192.168.2.254** i hem executat un ping a **8.8.8.8**, obtenint resposta correcta amb 0% de pèrdua de paquets.

---

![Imatge3](IMG/3.png)

Hem filtrat pel protocol **ICMP** i hem observat paquets de tipus **Echo request (tipus 8)** i **Echo reply (tipus 0)** dins del camp ICMP del paquet.


---

![Imatge4](IMG/4.png)

Hem confirmat dins del detall del paquet ICMP que la petició d’eco té **Type 8 (Echo request)**, identificat clarament al camp “Type” del protocol ICMP.


---

![Imatge5](IMG/5.png)

Hem capturat trànsit mentre es feien peticions des de la màquina física i hem observat paquets **ARP, SSDP i broadcast**, identificant trànsit relacionat amb altres dispositius de la xarxa.

---

![Imatge6](IMG/6.png)

Hem identificat una **petició DNS (Standard query)** on el client consulta la resolució del domini **[www.xtec.cat](http://www.xtec.cat)** al servidor DNS 8.8.8.8.

---

![Imatge7](IMG/7.png)

Hem identificat la **resposta DNS (Standard query response)** on el servidor retorna l’adreça IP **83.247.151.214** associada al domini **[www.xtec.cat](http://www.xtec.cat)**.

---

![Imatge8](IMG/8.png)

Hem filtrat pel protocol **ARP** i hem identificat la resposta del gateway, obtenint la seva adreça **MAC**, així com el fabricant de la seva targeta de xarxa a partir del prefix de la MAC.

---

![Imatge9](IMG/9.png)

Hem identificat una petició ARP on s’associa una adreça IP amb la seva adreça MAC, mostrant la MAC del dispositiu origen i confirmant la resolució d’adreces dins la xarxa local.

---

![Imatge10](IMG/10.png)

Hem obert l’arxiu de captura **captura1.pcapng** per analitzar el trànsit i obtenir la informació requerida dels diferents protocols.

---

![Imatge11](IMG/11.png)

Hem identificat que l’equip amb adreça IP **192.168.1.1** té la MAC **d4:76:ea:0f:fd:58**, obtinguda a través de la resposta del protocol ARP.

---

![Imatge12](IMG/12.png)

Hem analitzat la sessió FTP i hem observat les ordres de connexió, on es pot veure l’usuari que intenta iniciar sessió i les respostes del servidor en text pla, ja que el protocol FTP no està xifrat.

---

![Imatge13](IMG/13.png)

Hem identificat que l’usuari inicia sessió amb usuari **anonymous** i password **contra**, ja que FTP transmet les credencials en text pla, i hem observat les ordres de navegació i llistat de directoris del servidor.

---

![Imatge14](IMG/14.png)

Hem identificat que el fitxer descarregat del servidor és **README.txt**, observant l’ordre **RETR README.txt** dins de la sessió FTP.

---

![Imatge15](IMG/15.png)

Hem accedit a la sessió Telnet seguint el flux TCP i hem comprovat que es pot veure tot el contingut en text pla, ja que el protocol no està xifrat, incloent la informació que visualitza l’usuari durant la connexió.

---

![Imatge16](IMG/16.png)

Hem observat el contingut de la sessió Telnet i hem identificat una representació en ASCII d’una nau espacial petita, composada per caràcters com `-`, `_`, `=`, `(`, `)` i `>`, visibles directament en el flux de dades.

---

![Imatge17](IMG/17.png)

Hem observat el contingut de la sessió Telnet i hem identificat una representació en ASCII d’una nau espacial petita, composada per caràcters com `-`, `_`, `=`, `(`, `)` i `>`, visibles directament en el flux de dades.

---

![Imatge18](IMG/18.png)

Hem identificat el domini del servidor SSH a partir de l’inici de la connexió (**SSH-2.0-OpenSSH\_7.2p2 Ubuntu-4ubuntu2.2**) i hem observat l’intercanvi de claus i algoritmes, tot i que el contingut posterior està xifrat i no es pot interpretar.

---

![Imatge19](IMG/19.png)

Hem identificat una comunicació SMTP on s’envia un correu electrònic des del client al servidor, observant les ordres **MAIL FROM**, **RCPT TO** i **DATA**, que indiquen l’enviament del missatge.

---

![Imatge20](IMG/20.png)

Hem seguit el flux TCP de la sessió SMTP per visualitzar el contingut del correu i poder extreure el missatge enviat juntament amb el fitxer adjunt.

---

![Imatge21](IMG/21.png)

![Imatge22](IMG/22.png)

![Imatge23](IMG/23.png)

![Imatge24](IMG/24.png)

Hem identificat el contingut complet del correu electrònic dins del flux SMTP i hem pogut reconstruir el missatge enviat, incloent el text **“mensaje ultrasecreto para el administrador”**, demostrant que el protocol no xifra la informació i permet la seva extracció.

---

![Imatge25](IMG/25.png)

Hem desat el contingut del correu en un fitxer **correu.txt**, confirmant que hem pogut extreure correctament el missatge de la comunicació SMTP.

---
