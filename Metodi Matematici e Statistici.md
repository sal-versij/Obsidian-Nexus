# Metodi Matematici e Statistici
## Spazi campionati ed eventi
!def esperimento
Chiameremo esperimenti i fenomeni aleatori di cui ci occupiamo e chiameremo esiti i risultati di tali esperimenti
def!
!def spazio campionario
Dato un esperimento, è detto spazio campionario l'insieme di tutti gli esiti possibili

$\Omega$: generico spazio campionario
$\omega$: generici esiti

Risultati dell'esperimento: insieme
Esiti dell'esperimento: elementi dell'insieme
def!
!def
eventi sono sottoinsiemi di $\Omega$

$\Omega$: Evento certo
$\emptyset$: Evento impossibile
def!
!def
Due eventi di dicono mutuamente esclusivi se
E cap F = emptyset dove E subseteq Omega, F subseteq Omega
def!
Corrispondenze

| Simbolo                | definizione                                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------------- |
| $\Omega$               | spazio campionario certo                                                                       |
| $\omega$               | evento elementare, esito                                                                       |
| $E$                    | si verifica uno degli esiti contenuti in E, si verifica l'evento E                             |
| $\bar{E}$              | non si verifica uno degli esiti contenuti in E, non si verifica l'evento E                     |
| $E \cap F$             | si verificano entrambi gli eventi E ed F                                                       |
| $E \cup F$             | si verifica almeno uno degli eventi E ed F se F cup E neq emptyset                             |
| $E / F$                | si verifica E e non F                                                                          |
| $E \subseteq F$        | se si verifica E allora si verifica F                                                          |
| $E \cap F = \emptyset$ | eventi mutuamente esclusivi, se si verifica uno dei due è impossibile che si verifichi l'altro |
| $\emptyset$            | evento impossibile                                                                             |
| $\Omega$               | insieme degli esiti                                                                            |
| $\mathscr{F}$          | insieme degli eveti                                                                            |

Requisiti per $\mathscr{F}$

```ad-def
title:Algebra
1. $\Omega \in \mathscr{F}$
2. $E \in \mathscr{F} \implies \bar{E} \in \mathscr{F}$
3. $E,F\in\mathscr{F}\implies E\cup F\in\mathscr{F}$
```

```ad-demonstration
title:$E\cap F\in\mathscr{F}$
$E,F\in\mathscr{F}\implies\bar{E},\bar{F}\in\mathscr{F}\implies\bar{F}\cup\bar{F}\in\mathscr{F}\implies\overline{\bar{E}\cup\bar{F}}\in\mathscr{F}\implies E\cap F\in\mathscr{F}$
```

!def $T_n$
all'$n$-esimo lancio è uscito testa
def!

!def $C_n$
all'$n$-esimo lancio è uscito croce
def!

!def $E_n$
È uscita testa per la prima volta all'$n$-esimo lancio
$E_n = C_1\cap C_2\cap C_3\cap\ldots\cap T_n$
def!

Requisiti per $\mathscr{F}$

```ad-def
title:$\sigma$-Algebra
1. $\Omega \in \mathscr{F}$
2. $E \in \mathscr{F} \implies \bar{E} \in \mathscr{F}$
3. $E_n\in\mathscr{F}\forall n\implies \cup_{n=1}^{\infty}E_n\in\mathscr{F}$
```

$\mathscr{F}\subseteq\mathscr{P}(\Omega)$
!eg
Dato $\Omega$ la più piccola $\sigma$-algebra è $\mathscr{F} = \{\emptyset,\Omega\}$, la più estesa è $\mathscr{P}(\Omega)$
eg!

!def
Dato un insieme \Omega, e dati alcuni suoi sottoinsiemi: E_1,E_2,\ldots,E_n si dice $\sigma$-algebra degli E_i la più piccola $\sigma$-algebra di cui hanno parte tutti gli $E_i$
def!

!def Definizione classica di probabilità
$P=\frac{\text{\# casi favorevoli}}{\text{\# casi possibili}}$
def!

!def Definizione frequentista di probabilità
$P=\frac{\text{\# di successi}}{\text{\# di prove}}$
def!

!def Definizione di probabilità secondo Kolmogorov
Sia $\Omega$ uno spazio campionario e $\mathscr{F}$ una $\sigma$-algebra

Assiomi:

1. Per ogni evento $E\in\mathscr{F}$
   $P[E]\in\mathscr{R}$; $0\leq P[E]\leq1$
2. Per l'intero spazio campionario
   $P[\Omega]=1$
3. Presa una qualsiasi successione di eventi tali che $E_i\cap E_j=\emptyset$ se $i\neq j$
   $P[\cup_{i}E_i]=\sum_{i}P(E_i)$

la propabilità è una corrispondenza é$P:\mathscr{F}\to[0,1]$ che soddisfa gli assiomi precedenti

$(\Omega,\mathscr{F},P)$ è detto spazio delle probabilità
def!

Preposizione 1
```ad-demonstration
title:$P[\bar{E}] = 1-P[E]$
- $P[\Omega] = 1$
- $\Omega = E\cup\bar{E}\;;\;E\cap\bar{E}=\emptyset$
- $P[E\cup\bar{E}] = 1$
- $P[E\cup\bar{E}] = P[E] + P[\bar{E}]$
- $P[E] + P[\bar{E}] = 1\implies P[\bar{E}] = 1-P[E]$
```

Preposizione 2
```ad-demonstration
title:$F\subseteq E\implies P[F]\leq P[E]$
$F\subseteq E\implies E=F\cup(E-F)$
$P[E]=P[F\cup(E-F)]=P[E]=P[F]+P[E-F]\geq P[F]$
$F\subseteq E\implies P[F]\leq P[E]$
```
Proposizione 3
!demonstration $P[E\cup F]=P[E]+P[F]-P[E\cap F]$
$P[E]=P[E-F]+P[E\cap F]\implies P[E-F]=P[E]-P[E\cap F]$
$(E\cup F)=(E-F)\cup(E\cap F)\cup(F-E)$
$P[E\cup F]=P[E-F]+P[E\cap F]+P[F-E] =$
$P[E]-P[E\cap F]+P[E\cap F]+P[F]-P[E\cap F] =$
$P[E]+P[F]-P[E\cap F]$
demonstration!

Proposizione 4
$P[\cup_{i=1}^{n}E_i] = \sum\limits_{i}{P[E_i]}-\sum\limits_{i<j}{P[E_i\cap E_j]}+\ldots+(-1)^{n+1}P[E_1\cap E_2\cap\ldots\cap E_n]$

!def Probabilità condizionata
Siano $E$ ed $F$ due eventi, si chiama probabilità di $E$ dato $F$, e scriveremo $P[E|F]$, la probabilità che si verifichi l'evento $E$ supponendo che si sia verificato l'evento $F$
$P[E|F]=\frac{P[E\cap F]}{P[F]}\;\;P[F]>0$
$\implies\begin{cases}P[E\cap F] = P[F]\cdot P[E|F]\\P[E\cap F] = P[E]\cdot P[F|E]\\\end{cases}$
def!

!th Regole della catena
Dati $n$ eventi $E_1,E_2,\ldots,E_n$ la cui intersewzione ha probabilità positiva ($P[E_1\cap E_2\cap\ldots\cap E_n]>0$), si ha: 
$P[E_1\cap E_2\cap\ldots\cap E_n]>0=$
$P[E_1]\cdot P[E_2|E_1]\cdot P[E_3|E_1\cap E_2]\cdot P[E_4|E_1\cap E_2\cap E_3]\cdot\ldots\cdot P[E_n|E_1\cap E_2\cap\ldots\cap E_{n-1}]$
th!