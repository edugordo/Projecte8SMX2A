# AA4 NAT i VPN
## SMX 2A | Edu Gordo Cebrià

---

![imatge1](IMG/1.png)

info

---

![imatge2](IMG/2.png)

info

---

![imatge3](IMG/3.png)

info

---

![imatge4](IMG/4.png)

Executem la comanda per instal·lar els paquets **openssh-server** i **apache2** al sistema utilitzant `apt`.

---

![imatge5](IMG/5.png)

Editem el fitxer **index.html** amb nano per crear la pàgina web del servidor i afegim el contingut de l’activitat DNAT i VPN amb el títol, el nom i la descripció.

---

![imatge6](IMG/6.png)

Reiniciem el servei **apache2** i comprovem el seu estat per verificar que s’està executant correctament.

---

![imatge7](IMG/7.png)

Configurem una regla de tallafocs aplicant **DNAT** per redirigir el trànsit cap a la IP interna **192.168.8.1** a través de la interfície especificada.

---

![imatge8](IMG/8.png)

Configurem els ajustos addicionals de la regla activant-la i establint límits de connexions i taxa per controlar el trànsit.

---

![imatge9](IMG/9.png)

Accedim al servidor web des del navegador i comprovem que la pàgina es mostra correctament a través de la configuració DNAT.

---

![imatge10](IMG/10.png)

Accedim al panell d’IPFire i obrim el menú de serveis VPN per començar la configuració d’OpenVPN.

---

![imatge11](IMG/11.png)

Accedim a la configuració d’OpenVPN i generem els certificats necessaris per establir la connexió segura.

---

![imatge12](IMG/12.png)

Omplim el formulari de generació de certificats d’OpenVPN amb les dades de l’organització i el servidor per crear les claus de seguretat.

---

![imatge13](IMG/13.png)

Comprovem que els certificats d’autoritat, host i la clau TLS s’han generat correctament per a la configuració d’OpenVPN.

---

![imatge14](IMG/14.png)

Premem el botó **“Agregar”** per afegir una nova configuració de connexió OpenVPN.


---

![imatge15](IMG/15.png)

Seleccionem el tipus de connexió **Host-to-Net (Roadwarrior)** per configurar una VPN d’accés remot per als clients.

---

![imatge16](IMG/16.png)

Omplim els camps de la connexió OpenVPN assignant un nom, activant-la i configurant el rang d’adreces IP dinàmiques per als clients.

---

![imatge17](IMG/17.png)

Configurem les opcions avançades del client activant el **redirect gateway** i definint les xarxes accessibles i els paràmetres de DNS.

---

![imatge18](IMG/18.png)

Ens surt un error en el nom de la connexió i cal corregir-lo perquè només accepta certs caràcters vàlids.

---

![imatge19](IMG/19.png)

Activem i revisem la configuració del servidor **OpenVPN Roadwarrior**, comprovant que la connexió creada apareix.

---

![imatge20](IMG/20.png)

Desem el fitxer de configuració del client OpenVPN amb extensió **.ovpn** a l’equip local.

---

![imatge21](IMG/21.png)

Accedim al directori **drivers\etc** des de PowerShell i obrim el fitxer **hosts** amb el bloc de notes per editar-lo.

---

![imatge22](IMG/22.png)

Editem el fitxer **hosts** afegint la correspondència entre la IP **192.168.8.2** i el nom de domini **FW08.foodlogistic08.test** per resoldre’l localment.

---

![imatge23](IMG/23.png)

Seleccionem l’opció **“Import from file…”** per carregar el fitxer de configuració del client OpenVPN.

---

![imatge24](IMG/24.png)

Seleccionem el fitxer **AccesVPN.ovpn** des de la carpeta de descàrregues per importar la configuració del client OpenVPN.

---

![imatge25](IMG/25.png)

Accedim a la carpeta de l’usuari i localitzem el directori **OpenVPN** on gestionarem els fitxers de configuració del client.

---

![imatge26](IMG/26.png)

Entrem dins la carpeta **config** del directori d’OpenVPN per col·locar-hi els fitxers de configuració del client.

---

![imatge27](IMG/27.png)

Accedim a la carpeta **config** i verifiquem que hi ha el directori **AccesVPN** amb els fitxers de configuració preparats per al client OpenVPN.

---

![imatge28](IMG/28.png)

Obrim el menú del client OpenVPN i seleccionem l’opció **Connectar** per iniciar la connexió VPN.

---

![imatge29](IMG/29.png)

Introduïm la contrasenya del client OpenVPN i completam la connexió, confirmant que l’accés VPN s’estableix correctament i permet la comunicació segura amb la xarxa interna.

---

