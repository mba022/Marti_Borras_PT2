## Configuració del sistema de virtualització (IsardVDI) ##
---
1 Entra a IsardVDI i clica el boto de "crear maquina"

2 Selecciona quin tipus de maquina vols (en el nostre cas Desktop Ubuntu)

3 En Parametres avançats, canvia els GB, els PC's i finalment la xarxa (8PC),(25GB)

---

 ## Instal·lació del gestor d’arxius Nextcloud ##

Enllaços oficials

    Nextcloud: https://www.nextcloud.com
    Descàrrega directa:
    https://download.nextcloud.com/server/releases/latest.zip

    ownCloud: https://www.owncloud.org
    Descàrrega directa (versió estable):
    https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip

    Nota: Nextcloud és compatible amb PHP 8.1+, mentre que ownCloud encara requereix PHP 7.4 en moltes versions estables. Assegura’t de tenir la versió de PHP adequada abans d’instal·lar.
---
## Instal·la Apache (Configurar el servidor web)  ##

sudo apt install apache2 -y

Activa i inicia el servei:

sudo systemctl enable apache2
sudo systemctl start apache2

Verifica l’estat:

sudo systemctl status apache2

Visita http://localhost per veure la pàgina per defecte d’Apache.

---
## Instal·la MySQL (Base de dades)## 

Ubuntu 24.04 ja inclou el paquet mysql-server als repositoris oficials (versió 8.0 o superior):

sudo apt install mysql-server mysql-client -y

Inicia i habilita el servei:

sudo systemctl enable mysql
sudo systemctl start mysql

Configura de MySQL:
Accés a la consola de MySQL

sudo mysql

Creació de la base de dades

CREATE DATABASE bbdd;

Creació de l’usuari local

CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
GRANT ALL PRIVILEGES ON bbdd.* TO 'usuario'@'localhost';
FLUSH PRIVILEGES;
EXIT;

    Nota: Aquest usuari només pot connectar-se des del servidor local (localhost), cosa que és suficient si l’aplicació web i la base de dades estan al mateix servidor.
---
## Instal·la PHP i extensions comunes ##

Ubuntu 24.04 inclou PHP 8.3 als repositoris estàndard:

sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip php-json php-cli -y

Reinicia Apache per carregar PHP:

sudo systemctl restart apache2

Verifica la versió de PHP:

php -v

Crea un fitxer de prova:

echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php

Visita http://localhost/info.php per veure la informació de PHP.

    🔒 Mesura de seguretat: Un cop hagis verificat que funciona, elimina el fitxer:

    sudo rm /var/www/html/info.php
