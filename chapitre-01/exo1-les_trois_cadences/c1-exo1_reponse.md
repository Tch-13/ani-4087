Calculons (retirons les 8ms pour les capteurs, la transmission, la composition, l'affichage) :
* La durée d'une image à 72 hertz,
durée = (1000 / 72) = 13,88 == 13,9
On retire 8 ms, il reste 5,9 ms pour le code

* La durée d'une image à 90 hertz,
durée = (1000 / 90) = 11,11 == 11,1
On retire 8ms, il reste 3,1 ms pour le code

* La durée d'une image à 120 hertz,
durée = (1000 / 120) = 8,33 == 8,3 ms
On retire 8ms, il reste 0,3 ms pour le code

Donc on a :
- 72 Hz == 5,9 ms
- 90 Hz == 3,1 ms
- 120 Hz == 0,3 ms
