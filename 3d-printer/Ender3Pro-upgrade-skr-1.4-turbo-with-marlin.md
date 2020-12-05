# Tutorial installation Marlin 2.0.x sur une SKR 1.4 Turbo

## Voir les vidéos pour le montage de la carte
* https://www.youtube.com/watch?v=-Gdk0wHg51w

## Installer Visual Studio Code
* Télécharger le .deb depuis le site

    sudo apt install ./code_xxxxx.deb
    
* Installer platformIO IDE extentions (menu à gauche extention puis install)

## Compiler Marlin
* Forker marlin 2.0.x (voir de mon fork https://github.com/alexandrenavarro/Marlin/tree/2.0.x-ender3-skr-1.4t, toutes les modifications sont dans le commentaire du dernier commit).
* Copier la configuration config/examples/Creality/Ender-3/CrealityV1/ venant de https://github.com/MarlinFirmware/Configurations/archive/release-2.0.7.2.zip (prendre Configurations-release-2.0.7.2/config/examples/Creality/Ender-3/CrealityV1/) dans le répertoire Marlin/Marlin (pas dans config).
* Modifier quelques fichiers dont le platformio.in, Configuration.h et Configuration_adv.h (voir vidéo https://www.youtube.com/watch?v=-Gdk0wHg51w 9:25)
* Copier le fichier .pio/build/LPC1769/firmware.bin dans un carte micro.

## Installer la carte et tous les fils
* Voir la vidéos

## Brancher tout
* Tester d'abord les x, y, z (avec la main sur l'alimentation si endstop ne fonctionne pas) puis extrusion.
