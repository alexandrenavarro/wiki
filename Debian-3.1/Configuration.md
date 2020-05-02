#########################################
# Configuration de Linux (Debian Sarge) #
#########################################



#######################
# Package interessant #
#######################

# Environnement
# -------------
# XFree
apt-get install x-window-system-core

# kde
apt-get install kdm kde kde-i18n-fr

# gnome
# apt-get install gnome 

# clavier
apt-get install numlockx


# Bureautique :
# -------------

# OpenOffice
apt-get install openoffice.org

# xpdf
apt-get install xpdf

# installation xemacs
apt-get install emacs21 xemacs21


# Internet
# --------

# Gnome telnet

# mozilla firefox et thundbird (voir sur cooker pour les dernieres versions)
apt-get install mozilla-firefox-locale-fr-fr
apt-get install mozilla-thunderbird-locale-fr

#apt-get install totem-xine
#apt-get install mozplugger
# gedit /etc/mozpluggerrc
# Chercher cette partie
# 
# ...
# application/x-mplayer2: wmv,asf,mov: Windows Media
# video/x-ms-asf: asf,asx,wma,wax,wmv,wvx: Windows Media
# video/x-ms-wmv: wmv: Windows Media
#         stream noisy ignore_errors: mplayer -really-quiet -nojoystick -nofs -wid $window -vo xv,x11 -ao esd,alsa9,oss,arts,null -zoom -osdlevel 0 "$file" </dev/null
# ...
# # Ajouter la ligne suivante
# 
#         stream noisy ignore_errors: totem "$file" </dev/null
# Sauver le fichier /etc/mozpluggerrc (exemple)
#
# $ rm ~/.mozilla/pluginreg.dat



# Azureus
# bittorrent

# Limewire

# Amule
apt-get install amule

# Kopete
apt-get install kopete

# gFtp
apt-get install gftp


# smk4k
apt-get install samba
apt-get install smbfs

# nvu
apt-get install libstdc++2.10-glibc2.2
# $ cd votre_dossier_de_telechargement
# $ sudo tar jxvf nvu-0.70-pc-linux2.4.23-gnu.tar.bz2 -C /opt/
# $ sudo chown -R root:root /opt/nvu-0.70/
# $ sudo /opt/nvu-0.70/nvu
# $ nautilus applications:///Office
# Menu Fichier -> Cr.béer un lanceur
# Onglet Basique ->
# Nom: Nvu
# Commande: /opt/nvu-0.70/nvu
# Icône: /opt/nvu-0.70/icons/mozicon50.xpm

# namp et ethereal (scan reseau)
apt-get install nmap
apt-get install nmapfe
apt-get install ethereal

# d4x
apt-get install d4x

# ssh
apt-get install ssh

# Apache
apt-get install apache2


# Multimedia
# ----------

# Amarok
apt-get install amarok

# Xmms
apt-get install xmms

# kaffeine
apt-get install kaffeine

# Xine
apt-get install xine-ui

# Totem
#apt-get install totem

# Grip
#apt-get install grip

# Helixplayer
apt-get install helix-player
#helixplayer-mozilla-plugin
#helixplayer-helix-codecs
#openquicktime
#xanim-codecs

# Realpalyer
# $ cd votre_dossier_de_téléchargement
# $ chmod +x realplay-10.0.2.608-linux-2.2-libc6-gcc32-i586.bin
# $ sudo ./realplay-10.0.2.608-linux-2.2-libc6-gcc32-i586.bin
# 
# Enter the complete path to the directory where you want
# RealPlayer to be installed.  You must specify the full
# pathname of the directory and have write privileges to
# the chosen directory.
# Directory:  [/home/chua/RealPlayer]: /opt/RealPlayer
# 
# You have selected the following RealPlayer configuration:
# Destination:            /opt/RealPlayer
# Enter [F]inish to begin copying files, or [P]revious to go
# back to the previous prompts: [F]: F
# 
# Copying RealPlayer files...configure system-wide symbolic links? [Y/n]: Y
# 
# enter the prefix for symbolic links [/usr]: /usr

# myth logiciel pour la tv

# xdtv
#xdtv xdtv-OSD-font xdtv-devel

# KDE TV

# avidemux
apt-get install avidemux

# gimp
apt-get install gimp

# xsane
apt-get install xsane

# codecs
apt-get install gstreamer0.8-plugins w32codecs mime-codecs

# mplayer
apt-get install mplayer-686

# avidemux
apt-get install avidemux

# audacity
apt-get install audacity

# dvdrip
apt-get install dvdrip video-dvdrip dvdrip-doc


# Base de donnees
# ---------------

# mysql
apt-get install mysql-server
#/usr/bin/mysqladmin -u root password password

# postgresql
apt-get install postgresql



# Systeme
# -------

# qtparted
apt-get install qtparted

# nautilus

# konqueror

# k3b
apt-get install k3b

# decompression
apt-get install ark


# font 
apt-get install xfonts-intl-arabic
apt-get install xfonts-intl-asian
apt-get install xfonts-intl-european
apt-get install xfonts-intl-chinese
apt-get install xfonts-intl-chinese-big
apt-get install xfonts-intl-european
apt-get install xfonts-intl-japanese
apt-get install xfonts-intl-japanese-big
apt-get install xfonts-intl-phonetic

# kernel et kernel-source-2.6 (verifier si c'est les meme version)
# kernel
# kernel-source-2.6

# Java
# jdk-1_5_0-linux-i586.rpm
# ln -s /usr/java/jdk1.5.0/jre/plugin/i386/ns7/libjavaplugin_oji.so /usr/lib/mozilla-firefox-0.10.1/plugins/


# $ cd votre_dossier_de_téléchargement
# $ sh jre-1_5_0_01-linux-i586.bin
# $ sudo mkdir /usr/java
# $ sudo mv jre1.5.0_01/ /usr/java/
# $ sudo chown -R root:root /usr/java/jre1.5.0_01/
# $ sudo ln -s /usr/java/jre1.5.0_01/bin/java /usr/bin/java
# $ sudo ln -s /usr/java/jre1.5.0_01/bin/java_vm /usr/bin/java_vm   $ sudo cp /etc/bash.bashrc /etc/bash.bashrc_backup
# $ sudo gedit /etc/bash.bashrc
# $ sudo ln -s /usr/java/jre1.5.0_01/plugin/i386/ns7/libjavaplugin_oji.so /usr/lib/mozilla/plugins/
# $ sudo ln -s /usr/java/jre1.5.0_01/plugin/i386/ns7/libjavaplugin_oji.so /usr/lib/mozilla-firefox/plugins/


apt-get install alien

# Drivers 
# -------

# Nvidia
#apt-get install nvidia-glx
#apt-get install nvidia-settings
#nvidia-glx-config enable
#nautilus applications:///System

# Imprimantes 
# -----------

apt-get install cupsys cupsys-bsd cupsys-client cupsys-driver-gimpprint foomatic-db-engine foomatic-db-hpijs foomatic-filters-ppds 
# BJ4100 ou BJ7004 pour une i560 voir ftp://download.canon.jp/pub/driver/bj/linux/

# Autres
# ------

# Installation Python
apt-get install wxpython2.5.3

# wine
apt-get install wine

# babytrans (Dictonaire)
#babytrans

# Recette
#gfaim

# grisby (compta)
apt-get install grisbi

# gnucash
apt-get install gnucash

# planner
apt-get install planner



# Tar.gz
# ------

# Azureus, tomcat, maven, ant. eclipse (Dezipper)




# Compilation Kernel
# --------------------

apt-get install build-essential fakeroot kernel-package libglib2.0-dev libgtk2.0-dev libqt3-mt-dev libncurses5-dev tk8.4-dev

apt-get install kernel-source-2.6.8

apt-get install cramfsprogs initrd-tools
