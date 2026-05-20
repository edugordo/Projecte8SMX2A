# AA3. IPFire \- WebProxy
## SMX 2A  | [Eduard Gordo Cebria](mailto:eduard.gordo@mataro.epiaedu.cat)  

---

## Configuració xarxa i proxy

![Imatge1](IMG/1.png)

Comprovem la configuració de la xarxa cablejada del client, amb una IP assignada (192.168.8.1), una porta d’enllaç (192.168.8.254) i un servidor DNS (8.8.8.8), assegurant una connectivitat correcta dins la xarxa.

![Imatge4](IMG/1.1.png)

Configurem el proxy de la xarxa en mode manual, indicant la IP del servidor (192.168.8.254) i el port 800 per als protocols HTTP i HTTPS, assegurant que tot el trànsit web passa pel proxy.

![Imatge2](IMG/2.png)

Executem una prova de connectivitat fent un ping a 8.8.8.8, comprovant que tenim accés a Internet i que la xarxa funciona correctament.

![Imatge3](IMG/3.png)

Accedim a la interfície web d’IPFire mitjançant el navegador i iniciem sessió amb les credencials d’administrador per poder configurar el proxy.

![Imatge4](IMG/4.png)

Accedim al panell principal d’IPFire, on comprovem l’estat de les interfícies de xarxa (INTERNET i LAN) i verifiquem que el proxy encara està apagat abans de començar la configuració.

---

## Mostra URL Bloquejada  

![Imatge5](IMG/5.png)

Accedim al menú Red d’IPFire i seleccionem l’opció Web Proxy per començar la configuració del servidor proxy.

![Imatge6](IMG/6.png)

Configurem el servidor proxy avançat, activant-lo a la xarxa interna (Green), definint el port 800 i habilitant el filtre d’URL per permetre el control i bloqueig de l’accés web.

---

## Instal·la les llistes Negres

![Imatge7](IMG/7.png)

Accedim al menú Red i seleccionem l’opció Filtre de URL per configurar les regles de filtratge i control d’accés a les pàgines web.

![Imatge8](IMG/8.png)

Accedim a l’apartat de manteniment del filtre de URL, on configurem i actualitzem les llistes negres, activant les actualitzacions automàtiques i seleccionant una font per descarregar-les.

---

## Blocar Categories: Bank i Radio

![Imatge9](IMG/9.png)

Seleccionem les categories que volem bloquejar: bank i radio, dins del filtre d’URL, per restringir l’accés a aquests tipus de contingut web.

![Imatge10](IMG/10.png)

Verifiquem que el bloqueig funciona intentant accedir a una pàgina d’un banc (ing.es) i comprovem que l’accés és denegat pel proxy.

![Imatge11](IMG/11.png)

Comprovem que el bloqueig també funciona intentant accedir a una pàgina de ràdio (ah.fm) i verifiquem que el proxy impedeix l’accés correctament.

---

## Blocar dominis: [elnacional.cat](http://elnacional.cat) i [tecnocampus.cat](http://tecnocampus.cat)

![Imatge12](IMG/12.png)

Afegim dominis a la llista negra personalitzada, com elnacional.cat i tecnocampus.cat, i activem aquesta llista per bloquejar completament l’accés a aquests llocs web.

![Imatge13](IMG/13.png)

Verifiquem que el domini elnacional.cat està correctament bloquejat, ja que el proxy mostra un error i impedeix l’accés a la pàgina web.

![Imatge14](IMG/14.png)

Comprovem que el domini tecnocampus.cat també està correctament bloquejat, ja que el proxy mostra un error i impedeix l’accés a la pàgina web.

---

## Prova bloqueig URL concreta d’un domini  

![Imatge15](IMG/15.png)

Afegim una URL concreta (http://www.gironafc.com/es) a la llista de bloqueig per impedir l’accés només a aquesta pàgina específica dins d’un domini.

![Imatge16](IMG/16.png)

Comprovem que el bloqueig de la URL específica funciona correctament, ja que el proxy mostra un error i impedeix l’accés a aquesta pàgina concreta del domini.

---

## Blocar  pàgines amb el terme anime. Exc.: animenewsnetwork. com  

![Imatge17](IMG/17.png)

Afegim un domini permès a la llista blanca (animenetwork.com) i definim una paraula clau (anime) a la llista de frases bloquejades per restringir l’accés a pàgines que continguin aquest terme.

![Imatge18](IMG/18.png)

Comprovem que, tot i haver definit el bloqueig per la paraula anime, una pàgina concreta (animenewsnetwork.com) es pot carregar perquè està permesa o no coincideix exactament amb el filtre aplicat.

---

## Prova bloqueig per hores  

![Imatge19](IMG/19.png)

Accedim al menú Tallafocs (Firewall) d’IPFire i obrim les opcions relacionades amb les regles i configuracions de seguretat per gestionar el control del trànsit de xarxa.

![Imatge20](IMG/20.png)

Configurem una regla del tallafocs definint l’origen com la xarxa interna (Green) i el destí cap a RED, establint el protocol TCP per controlar el trànsit que passa pel proxy.

![Imatge21](IMG/21.png)

Configurem l’acció de la regla del tallafocs seleccionant Descartar i activem una restricció horària, definint els dies i la franja de temps en què s’aplicarà el bloqueig del trànsit.

![Imatge22](IMG/22.png)

Comprovem que la regla del tallafocs s’ha aplicat correctament, verificant que limita el trànsit de la xarxa interna (Green) cap a Internet (RED) només en els dies i hores establerts.

---

