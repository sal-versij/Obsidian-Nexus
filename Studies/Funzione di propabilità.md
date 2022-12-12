# Funzione di propabilità
## Definizione secondo Kolmogorov
```ad-def
Una corrispondenza
$P:\mathscr{F}\to[0,1]$
Che soddisfi i seguenti assiomi
1. > Per ogni evento $E\in\mathscr{F}$
   > $P[E]\in\mathbb{R};0\leq P[E]\leq1$
2. > Per l'intero campo campionario $P[\Omega]=1$
3. > Per una qualsiasi successione di eventi tali che $\forall i,j | i\neq j \; E_i\cap E_j = \emptyset$, $P[\bigcup\limits_i{E_i}] = \sum\limits_i P(E_i)$
```
### Proposizioni
1. $P[\bar{E}] = -P[E]$
2. $F\subseteq E \implies P[F]\leq P[E]$
3. $P[E\cup F] = P[E]+P[F]-P[E\cap F]$
4. $P[\bigcup\limits_{i=1}^{n}E_i] = \sum\limits_{i}^{n}P[E_i] - \sum\limits_{i<j}^{n}P[E_i\cap E_j] + \dots +(-1)^{n+1}(P[E_1\cap E_2 \cap \ldots \cap E_n])$


## References
[[Probabilità condizionata]]