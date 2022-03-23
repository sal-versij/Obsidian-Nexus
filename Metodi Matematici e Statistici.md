# Metodi Matematici e Statistici
## Spazi campionati ed eventi
```ad-def
title:esperimento
Chiameremo esperimenti i fenomeni aleatori di cui ci occupiamo e chiameremo esiti i risultati di tali esperimenti
```

```ad-def
title:spazio campionario
Dato un esperimento, è detto spazio campionario l'insieme di tutti gli esiti possibili

$\Omega$: generico spazio campionario
$\omega$: generici esiti

Risultati dell'esperimento: insieme
Esiti dell'esperimento: elementi dell'insieme
```

```
title: Eventi
Sottoinsiemi di $\Omega$

$\Omega$: Evento certo
$\emptyset$: Evento impossibile
```

```
Due eventi si dicono mutuamente esclusivi se
$E\cap F=\emptyset$ dove $E\subseteq\Omega, F\subseteq\Omega$
```

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

```ad-dem
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

```ad-dem
title:$P[\bar{E}] = 1-P[E]$
- $P[\Omega] = 1$
- $\Omega = E\cup\bar{E}\;;\;E\cap\bar{E}=\emptyset$
- $P[E\cup\bar{E}] = 1$
- $P[E\cup\bar{E}] = P[E] + P[\bar{E}]$
- $P[E] + P[\bar{E}] = 1\implies P[\bar{E}] = 1-P[E]$
```

Preposizione 2

```ad-dem
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
Dati $n$ eventi $E_1,E_2,\ldots,E_n$ la cui intersezione ha probabilità positiva ($P[E_1\cap E_2\cap\ldots\cap E_n]>0$), si ha:
$P[E_1\cap E_2\cap\ldots\cap E_n]=$
$P[E_1]\cdot P[E_2|E_1]\cdot P[E_3|E_1\cap E_2]\cdot P[E_4|E_1\cap E_2\cap E_3]\cdot\ldots\cdot P[E_n|E_1\cap E_2\cap\ldots\cap E_{n-1}]$

!def Partizione di $\Omega$
Si dice partizione di $\Omega$ un insieme di eventi $E_i$ (*finito* o *numerabile*) con le seguenti caratteristiche:

1. Ogni $E_i$ ha probabilità diversa da $0$
   $0<P[E_i]\leq1$
2. Gli $E_i$ sono mutualmente esclusi
   $P[E_i\cap E_j] = 0$
3. L'unione di tutti gli E_i copre \Omega
   $\bigcup_{i=1}^{n}{E_i}=\Omega$

def!
th!

!th Formula della probabilità totali
Sia {E_i} una partizione di \Omega, sia F un evento qualsiasi contenuto in \Omega, allora
$P[F]=\sum\limits_{i=1}^{n}{P[F|E_i]P[E_i]}$
!dem
$P[F]=\sum\limits_{i=1}^{n}{P[F|E_i]P[E_i]}\leftarrow$
$F=F\cap\Omega=F\cap(\bigcup_{i}E_i)=\bigcup_i(F\cap E_i)$
$P[F]=P[\bigcup_{i}{(F\cap E_i)}]=\sum\limits_{i}{P[F\cap E_i]}=$
$=\sum\limits_{i}{P[F|E]P[E_i]}$
dem!
th!

!th Legge condizionata o delle alternative
Sia {E_i} una partizione di \Omega e siano G ed F due eventi qualsiasi, allora
$P[F|G] = \sum\limits_{i}{P[F|E_i\cap G]\cdot P[E_i|G]}$
dove la sommatoria è estesa unicamente ai casi $P[E_i\cap G]\neq\emptyset$
th!

!th Formula di Bayes
Dato un evento F e datga una partizione {E_h} di \Omega, si ha
$P[E_h|F]=\frac{P[E|E_h]\cdot P[E_h]}{\sum\limits_{i}{P[F|E-i]\cdot P[E_i]}}$
!dem
$P[E_h\cap F]=P[F|E_h]P[E_h]=P[E_h|F]P[F]$
$P[E_h|F]=\frac{P[F|E_h]\cdot P[E_h]}{P[F]}=$
$=\frac{P[E|E_h]\cdot P[E_h]}{\sum\limits_{i}{P[F|E-i]\cdot P[E_i]}}$
dem!
th!

Eventi indipendenti
Osservazioni:
$P[E|F]>P[E]$ l'evento $F$ è favorevole ad $E$
$P[E|F]<P[E]$ l'evento $F$ è sfavorevole ad $E$
$P[E|F]=P[E]$ l'evento $F$ è ininfluenzato oppure indipendente da $E$
Proprietà:
Se $E$ è indipendente da $F$ allora $F$ è indipendente da $E$
$P[E|F]=P[E]\implies P[F|E]=P[F]$
!dem (da ricontrollare, mi sa che il prof l'abbia sbagliata)
$P[E\cap F]=P[E|F]P[F]=P[E]P[F]$
$P[E\cap F]=P[F|E]P[E]=P[E]P[F]$
$P[F|E]=P[F]$
allora
$P[E\cap F]=P[E]P[F]$
$P[E\cap F]=P[E|F]P[F]$
dem!

Proposizione
Se E ed F sono indipendenti allora sono indipendenti anche E e $\bar{F}$
!dem
$E=(E\cap F)\cup(E\cap\bar{F})$
$P[E]=P[E\cap F]+P[E\cap\bar{F}]=P[E]P[F]+P[E\cap\bar{F}]$
$P[E\cap\bar{F}]=P[E]-P[E]P[F]=P[E](1-P[F])=P[E]P[\bar{F}]$
dem!
!def
Una famiglia di $n$ eventi $E_1,E_2,\ldots,E_n$ si dice famiglia di eventi indipendenti se gli eventi $\{E_i\}$ sono a due a due , a tre a tre,... e così via fino ad $n$ ad $n$ indipendenti
def!

!def Disposti
Si dice che n oggetti sono ordinati (o disposti) in un allinemaneto quando sono collocati in n posti numerati da 1 ad n
def!

!def Permutazione
Si dice permutazione di n oggetti distinti ogni allineamento deli oggetti stessi, due permutazioni sono distinte quando differiscono per il posto occupato da almeno un oggetto.
Indicheremo con P_n il numero di permutazioni
!th
$P_n=n!$
th!
!th
Il numero di permutazioni distinte di n oggetti qei quali $q_1$ uguali tra loro, $q_2$ uguali tra loro e distinti dai precedenti,..., $q_h$ uguali tra loro e distinti dai precedenti(dove $q_1+q_2+\ldots+q_h=n$) è
$P^{*}_{q_1q_2\dots q_h}=\frac{n}{q_1!\cdot q_2!\cdot\ldots\cdot q_h!}$
Osservazione:
se gli oggetti sono solo di due tipo $(k,n-k)$
$P^{*}_{k,n-k}=\frac{n!}{k!(n-k)!}=\binom{n}{k}$
th!
def!

!def Disposizioni semplici
Si dice disposizione semplice di n oggetti di classe m ogni allineamento di m oggetti scelti fra gli n
!th
$D_{n,k}=\frac{n!}{(n-k)!}$
th!
Si dice disposizione con ripetizione di n oggetti di classe m ogni allineamento di m oggetti scelti fra gli n con la convenzione che ogni oggetto può essere ripetuto una o più volte
$D^{*}_{n,k}=n^k$
def!

!def
def