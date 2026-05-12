# Exploració de Xarxes

**Autor:** eduard.gordo@mataro.epiaedu.cat

## Activitats
- Utilitzeu un Kali Linux (Live o VM en mode pont).
- Exploreu la xarxa local tant en mode actiu com passiu amb netdiscover.
  - Noteu alguna diferència entre un mètode i l’altre?
- Repetiu l’exploració amb Nmap.
  - Useu l’opció per determinar el sistema dels equips detectats.
  - Mireu els ports oberts al router i al servidor Ubuntu.

## 1️⃣ Configuració de xarxa

![Imatge](IMG/1.png)

Comprovem la IP amb l’ordre:
```bash
ip a
```
Revisem la connexió a la xarxa i la porta d’enllaç amb:
```bash
ip route
```

## 2️⃣ Netdiscover – mode actiu

![Imatge](IMG/2.png)

Comprovem quins dispositius hi ha a la xarxa fent un escaneig amb netdiscover en mode actiu, enviant peticions directament per detectar totes les IPs que responen dins del rang indicat.

## 3️⃣ Netdiscover – mode passiu

![Imatge](IMG/3.png)

Comprovem els dispositius connectats a la xarxa utilitzant netdiscover en mode passiu, escoltant el trànsit sense enviar peticions i mostrant només els equips que es detecten de manera natural.

## 4️⃣ Comparació actiu vs passiu

![Imatge](IMG/4.png)

En el mode actiu fem peticions directament als equips de la xarxa per descobrir tots els dispositius possibles, mentre que en el mode passiu només escoltem el trànsit que ja hi ha a la xarxa i detectem únicament els equips que es comuniquen en aquell moment, sense enviar cap petició.

## 5️⃣ Nmap a un equip de la xarxa (servidor / host)

![Imatge](IMG/5.png)

Analitzem els equips de la xarxa fent un escaneig amb nmap per identificar quins serveis i ports tenen oberts i obtenir una idea general del sistema que està funcionant en cada màquina.

## 6️⃣ Nmap al router (gateway)

![Imatge](IMG/8.png)

Hem intentat escanejar el router amb Nmap utilitzant l’opció -A, però el dispositiu no respon a l’exploració. Això indica que el router bloqueja escanejos de xarxa, això pot ser degut a motius de seguretat o tallafocs, i per aquest motiu no s’han pogut identificar serveis ni ports oberts.
