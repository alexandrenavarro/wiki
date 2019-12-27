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
* Si vous avez des TMC2208 (ou smoother qui demande un réglage), branchez l'alimentation, settez le voltable à 0.75 V (0.8 max si shift) pour les x,y,z et 0.90 V (max 1V si shift) pour l'extrudeur (attention linear advanced ne fonctionne pas sur les TMC2208, je vous conseille un LV8729) et pensez aussi à régler les jumpers pour le mode de votre driver (voir documentation http://3dmodularsystems.com/fr/drivers-moteurs/483-tmc2208-driver-moteur-hyper-silencieux.html)
* Si vous avez des LV8729 (ou smoother qui demande un réglage), branchez l'alimentation, settez le voltable à 0.45 V pour l'extrudeur (max 0.5 si shift) pour l'extrudeur et pensez aussi à régler les jumpers pour le mode de votre driver (voire documentation http://3dmodularsystems.com/fr/drivers-moteurs/470-mks-lv8729-driver-moteur-ultra-silencieux-15a.html)

## Brancher tout
* Tester d'abord les x, y, z (avec la main sur l'alimentation si endstop ne fonctionne pas) puis extrusion.

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


# Tuning de l'Ender 3 pro

## Boiter arrière pour MKS Gen L ou SKR 1.3 et Raspberry
https://www.thingiverse.com/thing:3691287
https://www.thingiverse.com/thing:3688967

## Porte pour écran Bigtree TFT35
https://www.thingiverse.com/thing:3950607

## Porte Bobine latérale
https://www.thingiverse.com/thing:3441454
https://www.thingiverse.com/thing:3323206

## Stabilisateur
Imprimer Stabilisateur z (noir)
https://www.thingiverse.com/thing:3472567
https://www.thingiverse.com/thing:3370355
https://www.thingiverse.com/thing:3003690


 
 



