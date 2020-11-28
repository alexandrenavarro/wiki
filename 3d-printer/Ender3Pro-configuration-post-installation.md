# Configuration Post Installation

## Ajuster vos step/unit de vos x, y, z
* Imprimer un cube de 2cm (ou plus) et vérifier la taille des x, y, z sont corrects, si non, ajustez vos DEFAULT_AXIS_STEPS_PER_UNIT avec une règle de trois et retester si c'est correct désormais (https://www.youtube.com/watch?v=3yIebnVjADM&feature=youtu.be et https://www.youtube.com/watch?v=qotADlrrvUw&feature=youtu.be )

## Ajuster vos step/unit de votre extrudeur
* Extruder 10 cm et vérifier si la longeur est bien de 10 cm, si non, ajustez vos DEFAULT_AXIS_STEPS_PER_UNIT pour l'extruder avec un règle de trois et restester si c'est correct désormais

## Tuner votre PID pour la buse / bed
* Tuner votre PID pour la buse avec 210 degrés en lançant la commande puis changer les valeurs dans le firmware https://www.youtube.com/watch?v=_2TSIjD6CBM

    M303 E0 S210 C8
    
* Tuner votre PID pour le bed avec 65 degrés en lançant la commande puis changer les valeurs dans le firmware

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

## Tester votre bed leveling
* Imprimer https://www.thingiverse.com/thing:3235018
