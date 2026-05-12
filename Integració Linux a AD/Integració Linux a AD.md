# Afegir Linux a Active Directory
## SMX 2A | Edu Gordo Cebrià

---

Creem els usuaris de Linux per la nostra màquina **Zorin OS** i afegim un **grup de seguretat**, on posarem els usuaris que vulguem que en formin part per aplicar permisos. La resta d’usuaris que no hagin de tenir permisos quedaran fora d’aquest grup.

Comprovem la IP de l’adaptador 0 del servidor.

## Configuració de xarxa

Assignem a IPv4 de la màquina Zorin el **DNS del servidor**, apliquem els canvis i continuem.

Comprovem fent `ping` tant al servidor com al domini que la connexió funciona correctament.

## Instal·lació i unió al domini

Instal·lem els paquets necessaris d’**Active Directory** per a Zorin.

Canviem el **hostname** de la màquina i li posem el domini del servidor.

Amb la comanda:

```bash
realm discover
```

comprovem que la màquina troba correctament el domini i fa la connexió amb el servidor.

Seguidament, amb la comanda:

```bash
realm join
```

unim el dispositiu al domini. Si ens deixa continuar sense problemes, vol dir que la unió al domini s’ha fet correctament.

Un cop completats aquests passos, a la carpeta **Computers** de l’Active Directory ja apareix el nou dispositiu.

## Configuració de l’usuari

Afegim la configuració perquè, quan un usuari de l’Active Directory iniciï sessió al client Zorin per primer cop, se li creï automàticament la **carpeta personal**.

Seguidament iniciem sessió amb l’usuari que hem creat dins del domini.

En introduir la contrasenya, apareixerà el missatge:

```
creando directorio /home/...
```

i es crearà la carpeta personal de l’usuari gràcies a la configuració prèvia.

Si executem:

```bash
id
```

podem veure que l’usuari pertany correctament al domini.

## Permisos i sudo

Tornem a iniciar sessió amb l’usuari administrador de la màquina i creem el fitxer de **sudoers**.

Afegim en aquest fitxer el grup d’usuaris de Linux que pertanyen al grup del domini.

En tornar a iniciar sessió, comprovem que l’usuari es converteix en administrador i pot executar:

```bash
sudo su
```

Podem treure i posar permisos a qualsevol grup o a tothom directament amb l’usuari.

## Accés a recursos del servidor

Instal·lem el paquet:

```bash
smb
```

Anem a l’explorador d’arxius i busquem el directori del servidor a la pestanya **Otras Ubicaciones**.

Si la configuració i la instal·lació s’han fet correctament, el directori del servidor apareixerà. Tot i això, com que no tenim permisos d’administrador del servidor, no podrem accedir a totes les carpetes, però sí a algunes.

---

**I amb això finalitza la pràctica.**

