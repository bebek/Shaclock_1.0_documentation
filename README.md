# ShaClock32 pcboard rev 1.0

## Supporte 3 types de mcu :
* esp8266
* esp32
* esp32S2
## Supporte 3 types de régulateurs 5V :
* Linéaire AP1117
* Découpage mini 360
* Découpage module 5V

## Description

## Supporte les mémoires :
* 23LCV1024 exclusivement sur U6 pour l’esp8266. Aucun intérêt pour l’esp32 qui peut utiliser presque la même quantité de RAM en interne. L’esp32S2 en a beaucoup plus.
* PSRAM64H sur U5 pour l’esp32. Peut également être montée en U6 pour amener une taille gigantesque aux esp8266 et esp32.
Dans le cas du esp8266 les jumpers JP1-3 doivent être fermés. De plus il faudra ponter 7 avec 8 ainsi que 3 avec 4. La RAM installée ne supportera que le mode SPI single. Pas de DIO ou de QUAD.
Pour supporter les modes DIO et QUAD il faudra utiliser esp-idf car avec la platforme arduino nous n’avons pas accès aux fonctions.
* La 23LCV1024 en U6 pourra supporter tous les modes : single, DIO et QUAD.
* La PSRAM64H en U6 pourra supporter les modes : single et QUAD.
* La PSRAM64H en U5 permet de l’intégrer au plan mémoire et traiter plus rapidement et simplement les écritures/lectures. Ainsi que le support d’une vitesse élevée de transfert, uniquement pour l’esp32.

## Les connecteurs
* J1 Pour le display MAX_79xx connecteur 5 points
* J2 Entrée alimentation 7 à 15V connecteur 3 points 
* J3 Sortie alimentation 3 points même tension (-0.7V) que J2 avec protection par diode
* J4J5J6 connecteur interne pour brancher le VS1053
* J7 Sortie audio connecteur 3 points
* J8 liaison série connecteur 3 points utile dans le cas du esp32S2 car le port USB est déjà utilisé







