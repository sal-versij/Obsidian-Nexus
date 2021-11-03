# Algoritmo Toivonen
#study #not-understood
```ad-def
Si basa sul concetto di [[frontiera negativa]].
1. Considera un campione random $S$ dal dataset $D$, formato da p basket. Se s è il supporto minimo in D, fussa la soglia di suporto minimo di $S$$ a $\sigma\times p\times s$, dove $\sigma$ è un parametro tra 0 e 1.
2. Calcola gli itemset frequenti in S e quelli che stanno nella frontiera negativa.
3. Calcola il supporto degli itemset trovati al passo precedente:
   1. Se nessun itemset della frontiera negativa è frequente in D, allora restituisci come risultato gli item che sono risultati frequenti in $S$
   2. Se uno o più itemset della frontiera negativa risultano frequenti in $D$, allora ripetil'algoritmo su un nuovo campione.

```