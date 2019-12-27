Tutorial installation Marlin 1.1.9 sur une carte mks gen l 
----------------------------------------------------------

* Suivre le lien https://www.ender3.fr/turoriel-marlin-1-1-9-touch-mi-pour-la-ender3/ et voir les vidéos https://www.youtube.com/watch?v=LNdMYgwez8Y, https://www.youtube.com/watch?v=hDuWm9dLwFs, https://www.youtube.com/watch?v=ncc7TRkCH-M, https://www.youtube.com/watch?v=7VHwcEroHPk

* Clonez Marlin avec ces options pour la ender 3 de mon fork https://github.com/alexandrenavarro/Marlin, toutes les modifications sont dans le commentaires du dernier commit)

* Flashez via arduino-ide sans mettre d'alimentation et ne branchez pas surtout les moteurs.

* Installer la carte et tous les fils (suivez ce guide https://www.youtube.com/watch?v=7VHwcEroHPk) sans mettre les cables pour les moteurs

* SANS METTRE LES CABLES DES MOTEURS et si vous avez des TMC2208 (ou smoother qui demande un réglage), branchez l'alimentation,  settez le voltable à 0.75 V pour les x,y,z et 0.90 V pour l'extrudeur SANS METTRE LES CABLES DES MOTEURS, VOUS RISQUERIEZ D'ENDOMMAGER LA CARTE OU LES SMOOTHER (ce qui met arriver).

* Branchez tout et tester d'abord les x, y, z (avec la main sur l'alimentation si endstop ne fonctionne pas) puis extrusion.


* Tuner votre PID pour la buse avec 210 degrés en lançant la commande 
    M303 E0 S210 C8 
* Tuner votre PID pour le bed avec 65 degrés en lançant la command
    M303 E-1 S65 C8 



