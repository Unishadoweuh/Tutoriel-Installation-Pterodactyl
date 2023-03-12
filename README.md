# :computer: # Tutoriel-Installation-Pterodactyl

# Installation du panel & Wings

`bash <(curl -s https://pterodactyl-installer.se)`

# Installation de Phpmyadmin:

`cd /var/www/pterodactyl/public/ && mkdir phpmyadmin && cd phpmyadmin/ && wget https://files.phpmyadmin.net/phpMyAdmin/5.2.0/phpMyAdmin-5.2.0-all-languages.zip && unzip phpMyAdmin-5.2.0-all-languages.zip && mv phpMyAdmin-5.2.0-all-languages/* /var/www/pterodactyl/public/phpmyadmin`

# Configuration de MySQL:

`sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf`
`service mariadb restart`

`CREATE DATABASE phpmyadmin DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;`
`GRANT ALL ON phpmyadmin.* TO 'phpmyadmin'@'localhost' IDENTIFIED BY 'MOTDEPASSE';`
`create user admin@'%' identified by 'MOTDEPASSE';`
`grant all privileges on *.* to admin@'%' with grant option;`
`flush privileges;`

Générateur de mot de passe: https://www.dashlane.com/personal-password-manager/password-generator

# Création d'un compte pterodactyl par SSH:

`php artisan p:user:make`

# Informations:

Lien de la vidéo explicative: **https://youtu.be/L_0-v4t4tPw**

Pour plus d'informations direction: https://disord.gg/redstarthosting
