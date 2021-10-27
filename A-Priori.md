# A-Priori
````ad-def
collapse:true
title: Approccio Naive
>  Il metodo naive per la ricerca degli itemset frequenti consiste nel generare tutti gli itemset, calcolare per ciascuno di essi il supporto e verificare se supera la soglia.

```ad-note
Se $n$ è il numero totale di item, il numero di coppie da esaminare è $\binom{n}{2}$
il numero di triple da esaminare è $\binm{n}{3}$ e così via.
Il metodo naive è intrattabile poichè esamina troppi candidati.
```
````

```ad-def
title:Algoritmo [[A-Priori]]
Il [[Principio A-Priori]] suggerisce un approccio [[bottom-up]] in cui:
- Gli itemset vengono ricercati per cardinalità crescente
- Se un itemset di cardinalità $k$ non è frequente, allora non occorre estenderlo e costruire un itemset con $k+1$ item
```

```ad-code
1. Costruisci l'insieme $L_1$ degli item frequenti
2. Per valori crescenti di $k$ a partire da $K=1$

```