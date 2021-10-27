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

## Algoritmo [[A-Priori]]
Il [[Principio A-Priori]] suggerisce un approccio [[bottom-up]] in cui:
- Gli itemset vengono ricercati per cardinalità crescente
- Se un itemset di cardinalità $k$ non è frequente, allora non occorre estenderlo e costruire un itemset con $k+1$ item

```ad-code
1. Costruisci l'insieme $L_1$ degli item frequenti
2. Per valori crescenti di $k$ a partire da $k=1$:
   1. Genera l'insieme $C_{k+1}$ degli itemset candidati di cardinalità $k+1$ a apartire dall'insieme $L_k$:
      > Se l'insieme $L_k$ è rappresentato da una tabella con $k$ colonne, cisacuna delle quali corrisponde ad un item, l'insieme dei candidati $C_{k+1}$ si può ottentere mediante join di $L_k$ con se stesso.
    
      Nel combinare due righe $A$ e $B$ di $L_k$ dobbiamo imporre che:
      1. I primi $k-1$ item di $A$ e $B$ siano uguali
      2. Il $K$-esimo item di $A$ sia minore del $k$-esimo item di $B$
   2. Rimuovi dall'insieme $C_{k+1}$ gli itemset che contengono sottoinsiemi con $k$ item che non sono frequenti
   3. Calcola il supposto di ogni itemset in $C_{k+1}$
   4. Costruisci l'insieme $L_{k+1}$ formato da tutti gli itemset di $C_{k+1}$ frequenti
L'algoritmo termina quando  non ci sono più candidati da esaminare
```

### Ottimizzazioni Memoria
- Supporti dei singoli item
- Supporti delle coppie di item
  - Metodo della matrice triangolare
  - metodo delle triple
- Supporto di itemset con più di due item

### Algoritmi derivati ottimizzati
[[Algoritmo di Park, Chen, Yu (PCY)]]