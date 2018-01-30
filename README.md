# Installation de qt5pi

Ce dépôt permet de déployer sur un Raspberry pi les bibliothèques nécessaires à la compilation croisée en C++ avec le framework Qt version 5.7.1 

Editer le fichier ***/etc/apt/sources.list*** et décommenter la ligne **deb-src**.

	sudo nano /etc/apt/sources.list

Pour un raspberry avec **== Raspbian Stretch ==** il est nécessaire de mettre à jour le firmeware.

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


