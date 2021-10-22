# Esercizio Probabilità
````ad-exercise
> **52** carte di un mazzo vengono distribuiti a caso tra **4** giocatori
1. Qual è la propabilità che in una distribuzione ogni giocatore abbia le stesse carte dche aveva nella distribuzione precedente?
2. Qual è la probabilità che uno dei giocatori abbia 7 carte di picche

```ad-solution
title: Esercizio 1
collapse:none

Casi possibili: $52!$

Solution 1: (Dal prof)
Per ogni giocatore $13!$
$p = \frac{(13!)^4}{52!}$

Solution 2: (Dal prof)
$({52\over13}) ({39\over13}) ({26\over13})= \frac{52!}{13!13!13!13!}$
$p = \frac{(13!)^4}{52!}$

Solution 3: (Mia)
Casi possibili: $(52!)^2$
Possibili distribuzioni $({52\over13}) ({39\over13}) ({26\over13})= \frac{52!}{13!13!13!13!}$
Probabilità di una data combinazione: $\frac{13!13!13!13!}{52!}$
Probabilità di due date combinazioni consecutive: $(\frac{13!13!13!13!}{52!})^2$
```
```ad-solution
title: Esercizio 2
collapse:true

Casi possibili: $52!$

Solution 1:
$p = \frac{({13\over7})({52\over6})13!39!}{52!}$

Solution 2:
$p = \frac{({13\over7})({52\over6})}{({52\over13})}$
```
````
