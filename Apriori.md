# Apriori
````ad-def

title: Approccio Naive
>  Il metodo naive per la ricerca degli itemset frequenti consiste nel generare tutti gli itemset, calcolare per ciascuno di essi il supporto e verificare se supera la soglia.

```ad-note
Se $n$ è il numero totale di item, il numero di coppie da esaminare è $\binom{n}{2}$
il numero di triple da esaminare è $\binm{n}{3}$ e così via.
Il metodo naive è intrattabile poichè esamina troppi candidati.
```
````

[[Anti-monotonicità del supporto]]