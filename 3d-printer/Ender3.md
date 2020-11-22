# Tutorial installation Marlin 2.0.x sur une SKR 1.4 Turbo

TODO

# Tutorial installation Marlin 2.0.x sur une MKS GEN L 

## Voir les vidéos pour le montage de la carte
Suivre le lien https://www.ender3.fr/turoriel-marlin-1-1-9-touch-mi-pour-la-ender3/ et voir les vidéos https://www.youtube.com/watch?v=LNdMYgwez8Y, https://www.youtube.com/watch?v=hDuWm9dLwFs, https://www.youtube.com/watch?v=ncc7TRkCH-M, https://www.youtube.com/watch?v=7VHwcEroHPk

## Cloner le code de Marlin
* Voir de mon fork https://github.com/alexandrenavarro/Marlin/tree/bugfix-2.0.x, toutes les modifications sont dans le commentaires du dernier commit)

## Installer un logiciel pour compiler Marlin
* Via ArduinoIde
* Installer ArduinoIde

## Via Installer Platformio
* Installer Visual Code (sudo snap install code --classic)
* Installer le plugin Platformio

## Flasher via votre ide 
* Sans mettre d'alimentation et **ne branchez pas surtout les moteurs**.

## Installer la carte et tous les fils
* Suivez ce guide https://www.youtube.com/watch?v=7VHwcEroHPk) sans mettre les cables pour les moteurs

## Ajustez le voltage de vos drivers
**SANS METTRE LES CABLES DES MOTEURS POUR NE PAS ENDOMMAGER LA CARTE OU LES DRIVERS**
* Si vous avez des TMC2208 (ou smoother qui demande un réglage), branchez l'alimentation, settez le voltable à 0.75 V (0.8 max si shift) pour les x,y,z et 0.90 V (max 1V si shift) pour l'extrudeur (attention linear advanced ne fonctionne pas sur les TMC2208, vous pouvez mettre LV8729 mais bruyant en retraction par rapport a TMC2208) et pensez aussi à régler les jumpers pour le mode de votre driver (voir documentation http://3dmodularsystems.com/fr/drivers-moteurs/483-tmc2208-driver-moteur-hyper-silencieux.html)
* Si vous avez des LV8729 (ou smoother qui demande un réglage), branchez l'alimentation, settez le voltable à 0.45 V pour l'extrudeur (max 0.5 si shift) pour l'extrudeur et pensez aussi à régler les jumpers pour le mode de votre driver (voire documentation http://3dmodularsystems.com/fr/drivers-moteurs/470-mks-lv8729-driver-moteur-ultra-silencieux-15a.html)

## Brancher tout
* Tester d'abord les x, y, z (avec la main sur l'alimentation si endstop ne fonctionne pas) puis extrusion.


# Upgrade Bigtretech 3.5 (e3 ou normal)
* Cloner https://github.com/bigtreetech/BIGTREETECH-TouchScreenFirmware
* Copier sur votre sd
    /BIGTREETECH-TouchScreenFirmware-master/Copy to SD Card root directory to update - Unified Menu Material theme/BIGTREE_TFT35_V3.0_E3.26.x.bin
    /BIGTREETECH-TouchScreenFirmware-master/Copy to SD Card root directory to update - Unified Menu Material theme/config.ini
    /BIGTREETECH-TouchScreenFirmware-master/Copy to SD Card root directory to update - Unified Menu Material theme/TFT35/
* Démarrer votre écran avec cette sd.
* Vous devez avoir les cables ext1 et ext2 pour que l'émulateur 12864 fonctionne et cable tft pour que le mode tactile fonctionne.

# Configuration Post Installation

## Ajuster vos step/unit de vos x, y, z
* Imprimer un cube de 2cm (ou plus) et vérifier la taille des x, y, z sont corrects, si non, ajustez vos DEFAULT_AXIS_STEPS_PER_UNIT avec une règle de trois et retester si c'est correct désormais (https://www.youtube.com/watch?v=3yIebnVjADM&feature=youtu.be et https://www.youtube.com/watch?v=qotADlrrvUw&feature=youtu.be )

## Ajuster vos step/unit de votre extrudeur
* Extruder 10 cm et vérifier si la longeur est bien de 10 cm, si non, ajustez vos DEFAULT_AXIS_STEPS_PER_UNIT pour l'extruder avec un règle de trois et restester si c'est correct désormais

## Tuner votre PID pour la buse / bed
* Tuner votre PID pour la buse avec 210 degrés en lançant la commande puis changer les valeurs dans le firmware https://www.youtube.com/watch?v=_2TSIjD6CBM

    M303 E0 S210 C8
    
* Tuner votre PID pour le bed avec 65 degrés en lançant la commande puis changer les valeurs dans le firmware

    M303 E-1 S65 C8
    
## Tester vos niveaux de retraction acceptables
https://www.thingiverse.com/thing:2563909/

## Tester vos niveaux de température acceptables pour un filament donné 
https://www.thingiverse.com/thing:2729076

## Tuner votre flow / taille de tête (optionel)
* Imprimer https://www.thingiverse.com/thing:3397997 , mesurez la taille des murs, faites une règle de 3 et ajuster le flow ou mettez dans votre slicer la taille de la largeur de mur au lieu de 0.4*2 mm. Normalement, si vous avez ajutez vos step/unit de votre extrudeur, cela devrait être suffisant.

## Tester votre brigding / retraction / max angle
* Imprimer https://www.thingiverse.com/thing:2975429/files (30% sans support)
* Imprimer https://www.thingiverse.com/thing:2806295/files (100% sans support)


# Tuning de l'Ender 3 Pro

## Boiter arrière pour MKS Gen L ou SKR 1.4 et Raspberry
https://www.thingiverse.com/thing:4071141 (à installer, bon flux de ventilation)

https://www.thingiverse.com/thing:3691287 (essayé mais non retenu)

https://www.thingiverse.com/thing:3688967 (essayé mais non retenu)


## Porte pour écran Bigtree TFT35
https://www.thingiverse.com/thing:3950607 (non)

## Porte Bobine arrière (nécessite de tourner à 90 degré l'extrudeur)
https://www.thingiverse.com/thing:3718793 (essayer mais non retenu car ptfe se tord vraiment beaucoup)
TODO peut-être faire un remix pour qu'il soit plus haut comme sur la snapmaker 2.0

## Porte Bobine latérale
https://www.thingiverse.com/thing:3323206 (installé en noir)

https://www.thingiverse.com/thing:4230431 (à essayer)

https://www.thingiverse.com/thing:3441454 (non essayé)

##  Câble clip extruder
https://www.thingiverse.com/thing:2949858 (installé en noir)


## Guide filament
https://www.thingiverse.com/thing:2186253 (imprimé en noir)

https://www.thingiverse.com/thing:2745434 (non choisi)



## Stabilisateur
https://www.thingiverse.com/thing:3003690 (installé en bleu)

https://www.thingiverse.com/thing:3472567 (non choisi)

https://www.thingiverse.com/thing:3370355 (non choisi)


## Roue z
https://www.thingiverse.com/thing:3588485 (à installer en bleu)

https://www.thingiverse.com/thing:2534990 (non choisi)

## Fan Alimentation
https://www.thingiverse.com/thing:3232346 (installé en noir)

https://www.thingiverse.com/thing:3703510 (non choisi)

https://www.thingiverse.com/thing:3623828 (non choisi)

https://www.thingiverse.com/thing:3328495 (non choisi)

https://www.thingiverse.com/thing:2284893 (non choisi)

## Roue Extrudeur
https://www.thingiverse.com/thing:3585506 (à imprimer?)

https://www.thingiverse.com/thing:2776404 (à imprimer?)

https://www.thingiverse.com/thing:3585506 (à imprimer?)

https://www.thingiverse.com/thing:2776404 (à imprimer?)

https://www.thingiverse.com/thing:3176144 (à imprimer?)


## Fan Hot End
https://www.thingiverse.com/thing:3182917 (à imprimer)

https://www.thingiverse.com/thing:1750976 (à imprimer)

https://www.thingiverse.com/thing:1596181 (à imprimer?)

https://www.thingiverse.com/thing:2802474 (à imprimer?)


## Chaine
https://www.thingiverse.com/thing:2920060 (à imprimer)

## Boitier outils
https://www.thingiverse.com/thing:3548246 (à imprimer)

https://www.thingiverse.com/thing:3208219 (à imprimer?)


## VSlot
https://www.thingiverse.com/thing:3248551 (à imprimer?)

https://www.thingiverse.com/thing:3379068 (à imprimer?)

## Rail Cover
https://www.thingiverse.com/thing:3490301 (à imprimer en bleu)

https://www.thingiverse.com/thing:3196302 (non retenu)


## Anti snap guide 
https://www.thingiverse.com/thing:2940855 (à imprimer en bleu)


## Détecteur de filament
https://www.thingiverse.com/thing:3250248 (à imprimer?)

# Slicer : 

## Cura
### Installation
Download AppImage of Cura3D and run it.
Add in alacarte.

#### Configuration

##### Profiles
Add Chep profile https://www.chepclub.com/cura-profiles.html

##### Plugins
* Auto-orientation
* Sidebar

##### Your profile

###### Quality
Initial Layer Width : 120%

###### Shell
Top layer : 7->3
Bottom layer : 7->3
Top/Bottom line Direction : [0,90]
ZSeam Alimentation : User defined
Enable Ironing : true

##### Infill
Infill Density : 25->15%

##### Speed
Print Speed : 50 -> 60-80
Combining : Not in Skin
ZHtop : false -> true if needed


##### Support
Generate Support : false -> true if needed.
Support Z Distante : 0.12 -> 0.2

##### Build Support
Build plate support Adhesion Type : Brim






 



