Tutorial installation Marlin 1.1.9 sur une carte mks gen l 
----------------------------------------------------------

* Suivre le lien https://www.ender3.fr/turoriel-marlin-1-1-9-touch-mi-pour-la-ender3/ et voir les vidéos https://www.youtube.com/watch?v=LNdMYgwez8Y, https://www.youtube.com/watch?v=hDuWm9dLwFs, https://www.youtube.com/watch?v=ncc7TRkCH-M, https://www.youtube.com/watch?v=7VHwcEroHPk

* Clonez Marlin avec ces options pour la ender 3 de mon fork https://github.com/alexandrenavarro/Marlin branche bugfix-2.0.x, toutes les modifications sont dans le commentaires du dernier commit)

* Flashez via arduino-ide sans mettre d'alimentation et ne branchez pas surtout les moteurs.

* Installer la carte et tous les fils (suivez ce guide https://www.youtube.com/watch?v=7VHwcEroHPk) sans mettre les cables pour les moteurs

* SANS METTRE LES CABLES DES MOTEURS et si vous avez des TMC2208 (ou smoother qui demande un réglage), branchez l'alimentation,  settez le voltable à 0.75 V pour les x,y,z et 0.90 V pour l'extrudeur SANS METTRE LES CABLES DES MOTEURS, VOUS RISQUERIEZ D'ENDOMMAGER LA CARTE OU LES SMOOTHER (ce qui met arriver).

* Branchez tout et tester d'abord les x, y, z (avec la main sur l'alimentation si endstop ne fonctionne pas) puis extrusion.

* Imprimer un cube de 2cm (ou plus) et vérifier la taille des x, y, z sont corrects, si non, ajustez vos DEFAULT_AXIS_STEPS_PER_UNIT avec une règle de trois et retester si c'est correct désormais

* Extruder 10 cm et vérifier si la longeur est bien de 10 cm, si non, ajustez vos DEFAULT_AXIS_STEPS_PER_UNIT pour l'extruder avec un règle de trois et restester si c'est correct désormais

* Tuner votre PID pour la buse avec 210 degrés en lançant la commande puis changer les valeurs dans le firmware

    M303 E0 S210 C8
    
* Tuner votre PID pour le bed avec 65 degrés en lançant la commande puis changer les valeurs dans le firmware

    M303 E-1 S65 C8
    



