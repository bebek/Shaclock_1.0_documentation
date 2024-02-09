# ShaClock32 pcboard rev 1.0

## Supporte 3 types de mcu :
* esp8266
* esp32
* esp32S2
## Supporte 3 types de régulateurs 5V :
* Linéaire AP1117
* Découpage mini 360
* Découpage module 5V

## Supporte les mémoires :
* 23LCV1024 exclusivement sur U6 pour l’esp8266. Aucun intérêt pour l’esp32 qui peut utiliser presque la même quantité de RAM en interne. Egalment aucun intéret pour l’esp32S2 qui a 4 giga en interne.
* PSRAM64H sur U5 pour l’esp32. Peut également être montée en U6 pour amener une taille gigantesque aux esp8266 et esp32.
Dans le cas du esp8266 les jumpers JP1-3 doivent être fermés. De plus il faudra ponter 7 avec 8 ainsi que 3 avec 4. La RAM installée ne supportera que le mode SPI single. Pas de DIO ou de QUAD.
Pour supporter les modes DIO et QUAD il faudra utiliser esp-idf car avec la platforme arduino nous n’avons pas accès aux fonctions.
* La 23LCV1024 en U6 pourra supporter tous les modes : single, DIO et QUAD.
* La PSRAM64H en U6 pourra supporter les modes : single et QUAD.
* La PSRAM64H en U5 permet de l’intégrer au plan mémoire et traiter plus rapidement et simplement les écritures/lectures. Ainsi que le support d’une vitesse élevée de transfert, uniquement pour l’esp32.
## Cas du esp8266
Si l'on veut utiliser la mémoire externe on doit fermer les JP1 JP2 et JP3.
De plus il faut ponter U6.3 avec U6.4 ainsi que U6.7 avec U6.8 pour ne pas laisser flottantes les entrées 3 et 7.
On pourra utiliser la 23LCV1024 ainsi que la PSRAM64H en mode SPI simple.
## cas du esp32S2
Il faut noter que ce chip possède une ram interne conséquente aucun besoin de ram externe.
Si l'on veut alors la PSRAM64H en U6. Même prinicipe que pour l'esp8266 pour accéder à la RAM.
## cas du esp32
on peut utiliser la 23LCV1024 ainsi que la PSRAM64H en U6 
On peut mettre la PSRAM64H en U5 pour que la memoire soit dans le plan mémoire du chip
## Les connecteurs
* J1 Pour le display MAX_79xx connecteur 5 points
* J2 Entrée alimentation 7 à 15V connecteur 3 points 
* J3 Sortie alimentation 3 points même tension (-0.7V) que J2 avec protection par diode
* J4J5J6 connecteur interne pour brancher le VS1053
* J7 Sortie audio connecteur 3 points
* J8 liaison série connecteur 3 points utile dans le cas du esp32S2 car le port USB est déjà utilisé







