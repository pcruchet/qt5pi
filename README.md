# Installation de qt5pi


Ce dépôt permet de déployer sur un Raspberry pi les bibliothèques nécessaires à la compilation croisée en C++ avec le framework Qt version 5.7.1 

La chaîne de développement croisée est réalisée à partir des informations d'écrites sur le site [RaspberryPi2EGLFS](https://wiki.qt.io/RaspberryPi2EGLFS) 

Editer le fichier ***/etc/apt/sources.list*** et décommenter la ligne **deb-src**.

	sudo nano /etc/apt/sources.list

Pour un raspberry avec **Raspbian Stretch** il est nécessaire de mettre à jour le firmeware.

	sudo rpi-update
	sudo reboot

Mettre à jour le système et installer les librairies suivantes :

	sudo apt update
	sudo apt build-dep qt4-x11
	sudo apt build-dep libqt5gui5
	sudo apt install libudev-dev libinput-dev libts-dev libxcb-xinerama0-dev libxcb-xinerama0
	
Cloner le dépôt :

	git clone https://github.com/pcruchet/qt5pi.git

Décompresser l'archive :

	tar zxvf qt5pi.tar.gz
	
Deplacer le dossier qt5pi dans **/usr/local/**

	sudo mv qt5pi /usr/local/

Pour obtenir la saise avec un clavier AZERTY dans les interfaces développées sous Qt, il est nécessaire de modifier la variable d'environnement **XKB_DEFAULT_LAYOUT** avec la valeur **fr** dans le fichier **/etc/profile**.

	sudo nano /etc/profile
	
	export XKB_DEFAULT_LAYOUT=fr
