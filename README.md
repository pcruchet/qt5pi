# Installation de qt5pi


Ce dépôt permet de déployer sur un Raspberry pi les bibliothèques nécessaires à la compilation croisée en C++ avec le framework Qt version 5.11.3 avec la gestion de base de données sous Mysql.
La version de Raspbian utilisée est Buster with desktop 2019-09-26 [Raspbian](https://www.raspberrypi.org/downloads/raspbian/)

La chaîne de développement croisée est réalisée à partir des informations d'écrites sur le site [RaspberryPi2EGLFS](https://wiki.qt.io/RaspberryPi2EGLFS), le site [Cross-compile and deploy Qt 5.12 for Raspberry Pi](https://mechatronicsblog.com/cross-compile-and-deploy-qt-5-12-for-raspberry-pi/) et le site de [Marc Wapelhorst](http://wapel.de/?p=641).

Editer le fichier ***/etc/apt/sources.list*** et décommenter la ligne **deb-src**.

	sudo nano /etc/apt/sources.list

Pour un raspberry avec **Raspbian Stretch** il est nécessaire de mettre à jour le firmeware et le noyau afin d'obtenir la dernière version.

	sudo rpi-update
	sudo reboot

Mettre à jour le système et installer les librairies suivantes :

	sudo apt update
	sudo apt build-dep qt4-x11
	sudo apt build-dep libqt5gui5
	sudo apt install libudev-dev libinput-dev libts-dev libxcb-xinerama0-dev libxcb-xinerama0

Pour la gestion de la base de données avec le client QMYSQL :

    sudo apt install mariadb-server libmariadbclient-dev
	
Cloner le dépôt :

	git clone https://github.com/pcruchet/qt5pi.git

Décompresser l'archive :

	cd qt5pi
	tar zxvf qt5pi.tar.gz
	
Deplacer le dossier qt5pi dans **/usr/local/**

    sudo mv qt5pi /usr/local/
    sudo chown pi:pi /usr/local/qt5pi

Pour obtenir la saise avec un clavier AZERTY dans les interfaces développées sous Qt, il est nécessaire de modifier la variable d'environnement **XKB_DEFAULT_LAYOUT** avec la valeur **fr** dans le fichier **~/.profile**. 

	
    sudo nano ~/.profile
	
    export XKB_DEFAULT_LAYOUT=fr

Toujours dans le même fichier, les lignes suivantes permettent de fixer la taille physique de l'affichage. 

    export QT_QPA_EGLFS_PHYSICAL_WIDTH=211
    export QT_QPA_EGLFS_PHYSICAL_HEIGHT=127
