#Installation de qt5pi

Editer le fichier ***/etc/apt/sources.list*** et décommenter la ligne **deb-src**.

	sudo nano /etc/apt/sources.list

Mettre à jour le système et installer les librairies suivantes :

	sudo apt update
	sudo apt build-dep qt4-x11
	sudo apt build-dep libqt5gui5
	sudo apt install libudev-dev libinput-dev libts-dev libxcb-xinerama0-dev libxcb-xinerama0