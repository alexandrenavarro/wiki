# Tutorial installation Marlin 2.0.x sur une MKS GEN L 

## Voir les vidéos pour le montage de la carte
Suivre le lien https://www.ender3.fr/turoriel-marlin-1-1-9-touch-mi-pour-la-ender3/ et voir les vidéos https://www.youtube.com/watch?v=LNdMYgwez8Y, https://www.youtube.com/watch?v=hDuWm9dLwFs, https://www.youtube.com/watch?v=ncc7TRkCH-M, https://www.youtube.com/watch?v=7VHwcEroHPk

## Cloner le code de Marlin
* Voir de mon fork https://github.com/alexandrenavarro/Marlin/tree/bugfix-2.0.x, toutes les modifications sont dans le commentaires du dernier commit)

## Installer un logiciel pour compiler Marlin
* Via ArduinoIde
* Installer ArduinoIde

## Via Installer Platformio
* Installer Visual Code (sudo snap install code --classic)
* Installer le plugin Platformio

## Flasher via votre ide 
* Sans mettre d'alimentation et **ne branchez pas surtout les moteurs**.

## Installer la carte et tous les fils
* Suivez ce guide https://www.youtube.com/watch?v=7VHwcEroHPk) sans mettre les cables pour les moteurs

## Ajustez le voltage de vos drivers
**SANS METTRE LES CABLES DES MOTEURS POUR NE PAS ENDOMMAGER LA CARTE OU LES DRIVERS**
* Si vous avez des TMC2208 (ou smoother qui demande un réglage), branchez l'alimentation, settez le voltable à 0.75 V (0.8 max si shift) pour les x,y,z et 0.90 V (max 1V si shift) pour l'extrudeur (attention linear advanced ne fonctionne pas sur les TMC2208, vous pouvez mettre LV8729 mais bruyant en retraction par rapport a TMC2208) et pensez aussi à régler les jumpers pour le mode de votre driver (voir documentation http://3dmodularsystems.com/fr/drivers-moteurs/483-tmc2208-driver-moteur-hyper-silencieux.html)
* Si vous avez des LV8729 (ou smoother qui demande un réglage), branchez l'alimentation, settez le voltable à 0.45 V pour l'extrudeur (max 0.5 si shift) pour l'extrudeur et pensez aussi à régler les jumpers pour le mode de votre driver (voire documentation http://3dmodularsystems.com/fr/drivers-moteurs/470-mks-lv8729-driver-moteur-ultra-silencieux-15a.html)

## Brancher tout
* Tester d'abord les x, y, z (avec la main sur l'alimentation si endstop ne fonctionne pas) puis extrusion.
