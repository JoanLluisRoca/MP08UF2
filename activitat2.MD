# INSTAL·LACIÓ OWNCLOUD

## GUIA D'INSTAL·LACIÓ

### REQUERIMENTS NECESSARIS

Els requisits que hi necesitem per instal·lar el owncloud son els següents.
- LINUX: Ubuntu 22.04LTS
- Servidor Web: Apache
- BBDD: MariaDB
- PHP: versió: (7.3 o 7.4)

El primer pas per poder començar la instal·lació, és instalar el servidor apache2 amb la següent comanda.

```sh
sudo apt install apache2
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/apache1.png)


El següent pas, es fer les comprovacions necessàries per confirmar que hi està actiu ja sigui amb la comanda “service apache2 status” o buscant localhost al buscador de internet.

1.
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/apache2.png)
2.
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/apache3.png)

El següent que hi hem de fer es desactivar el llistat de directoris del servidor.
El cual es fa amb la següent comanda.

```sh
sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/apache4.png)

Un cop ja ho tenim, instalem la MariaDB amb la següent comanda.

```sh
sudo apt-get install mariadb-server mariadb-client -y
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/mariaDB1.png)

El següent que hi hem de fer és començar a configurar la MariaDB. Es a dir assignar les següents opcions.
Deshabilitar usuarios anónimos.
Deshabilitar acceso remoto como root.
Eliminar las bases de datos de testeo y el acceso a las mismas.
Actualizar las tablas de privilegios.

```sh
sudo mysql -u root -p
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/mariaDB2.png)

![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/mariaDB3.png

El següent que hi hem de fer es reiniciar la base de dades amb les següent comanda.

```sh
sudo systemctl restart mariadb.service` o `sudo service mariadb.service restart
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/mariaDB4.png)

Els següents passos a seguir ja son entrar dins de la base de dades MariaDB amb la comanda següent.


```sh
sudo mysql -u root -p
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/mariaDB5.png)

Ara i crearem la base de dades owncloud i l’usuari amb la contrasenya corresponent.

```sh
CREATE DATABASE owncloud;
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/owncloud1.png)

```sh
CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234';
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/owncloud2.png)

El següent que hem de fer és establir el servidor que hem creat amb l’usuari que també hi hem creat amb la comanda següent.

```sh
GRANT ALL ON owncloud.* TO 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234' WITH GRANT OPTION;
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/owncloud3.png)

Despres hi hem de instal·lar els flush privilegie i sortir.
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/owncloud4.png)

El següent que hi hem de fer, és instalar el PHP i els mòduls corresponents.

El primer que instal·larem hi seran els propis repositoris.

```sh
sudo apt-get install software-properties-common -y
sudo add-apt-repository ppa:ondrej/php
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/php1.png)


Un cop ho tenim hi farem la següent comanda per actualitzar hi tenir els nous repositoris.

```sh
sudo apt update
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/php2.png)

Un cop ja ho tenim instalar hi hem actualitzat hi passarem a instal·lar els mòduls necessaris amb la següent comanda.

```sh
sudo apt install php7.4 libapache2-mod-php7.4 php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-apcu php7.4-smbclient php7.4-ldap php7.4-redis php7.4-gd php7.4-xml php7.4-intl php7.4-json php7.4-imagick php7.4-mysql php7.4-cli php7.4-mcrypt php7.4-ldap php7.4-zip php7.4-curl -y
```
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/php3.png)

Després de fer l'instal·lació obrir un fitxer per fer canvis. Amb aquesta comanda.

```sh
sudo nano /etc/php/7.1/apache2/php.ini
```

I els paràmetres a canviar hi son els següents.
-memory_limit = 256M upload_max_filesize = 100M
![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/php4.png)

I l’altra captura.

![](https://github.com/JoanLluisRoca/MP08UF2/blob/main/Aplicacions%20web/php5.png)

……………………………………………………………………………………
