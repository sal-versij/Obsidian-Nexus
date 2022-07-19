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

```ad-def
title: Eventi
Sottoinsiemi di $\Omega$

$\Omega$: Evento certo
$\emptyset$: Evento impossibile
```

```ad-def
Due eventi si dicono mutuamente esclusivi se
$E\cap F=\emptyset$ dove $E\subseteq\Omega, F\subseteq\Omega$
```
### Corrispondenze
| Simbolo                | definizione                                                                                    |
| ---------------------- | ---------------------------------------------------------------------------------------------- |
| $\Omega$               | spazio campionario certo                                                                       |
| $\omega$               | evento elementare, esito                                                                       |
| $E$                    | si verifica uno degli esiti contenuti in $E$, si verifica l'evento $E$                         |
| $\bar{E}$              | non si verifica uno degli esiti contenuti in $E$, non si verifica l'evento $E$                 |
| $E \cap F$             | si verificano entrambi gli eventi $E$ ed $F$                                                   |
| $E \cup F$             | si verifica almeno uno degli eventi $E$ ed $F$ se $F\cup E\neq\emptyset$                       |
| $E / F$                | si verifica $E$ e non $F$                                                                      |
| $E \subseteq F$        | se si verifica $E$ allora si verifica $F$                                                      |
| $E \cap F = \emptyset$ | eventi mutuamente esclusivi, se si verifica uno dei due è impossibile che si verifichi l'altro |
| $\emptyset$            | evento impossibile                                                                             |
| $\Omega$               | insieme degli esiti                                                                            |
| $\mathscr{F}$          | insieme degli eveti                                                                            |

---
### Requisiti per $\mathscr{F}$
```ad-def
title: Algebra
1. $\Omega \in \mathscr{F}$
2. $E \in \mathscr{F} \implies \bar{E} \in \mathscr{F}$
3. $E,F\in\mathscr{F}\implies E\cup F\in\mathscr{F}$

```

```ad-dem
title:$E\cap F\in\mathscr{F}$
$E,F\in\mathscr{F}\implies\bar{E},\bar{F}\in\mathscr{F}\implies\bar{F}\cup\bar{F}\in\mathscr{F}\implies\overline{\bar{E}\cup\bar{F}}\in\mathscr{F}\implies E\cap F\in\mathscr{F}$
```

```ad-def
title:$T_n$
all'$n$-esimo lancio è uscito testa
```

```ad-def
title:$C_n$
all'$n$-esimo lancio è uscito croce
```

```ad-def
title:$E_n$
È uscita testa per la prima volta all'$n$-esimo lancio
$E_n = C_1\cap C_2\cap C_3\cap\ldots\cap T_n$
```

---

```ad-def
title:$\sigma$-Algebra
1. $\Omega \in \mathscr{F}$
2. $E \in \mathscr{F} \implies \bar{E} \in \mathscr{F}$
3. $E_n\in\mathscr{F}\forall n\implies \cup_{n=1}^{\infty}E_n\in\mathscr{F}$
```

$\mathscr{F}\subseteq\mathscr{P}(\Omega)$

```ad-eg
Dato $\Omega$ la più piccola $\sigma$-algebra è $\mathscr{F} = \{\emptyset,\Omega\}$, la più estesa è $\mathscr{P}(\Omega)$
```

```ad-def
Dato un insieme $\Omega$, e dati alcuni suoi sottoinsiemi: $E_{1},E_{2},\ldots,E_{n}$ si dice $\sigma$-algebra degli $E_{i}$ la più piccola $\sigma$-algebra di cui hanno parte tutti gli $E_{i}$
```
## Probabilità
```ad-def
title: Definizione classica di probabilità
$P=\frac{\text{\# casi favorevoli}}{\text{\# casi possibili}}$
```

```ad-def
title: Definizione frequentista di probabilità
$P=\frac{\text{\# di successi}}{\text{\# di prove}}$
```

```ad-def
title: Definizione di probabilità secondo Kolmogorov
Sia $\Omega$ uno spazio campionario e $\mathscr{F}$ una $\sigma$-algebra

Assiomi:

1. Per ogni evento $E\in\mathscr{F}$
   $P[E]\in\mathbb{R}$; $0\leq P[E]\leq1$
2. Per l'intero spazio campionario
   $P[\Omega]=1$
3. Presa una qualsiasi successione di eventi tali che $E_i\cap E_j=\emptyset$ se $i\neq j$
   $P[\cup_{i}E_i]=\sum_{i}P(E_i)$

la propabilità è la corrispondenza $P:\mathscr{F}\to[0,1]$ che soddisfa gli assiomi precedenti

$(\Omega,\mathscr{F},P)$ è detto spazio delle probabilità
```
### Preposizioni
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

```ad-dem
title: $P[E\cup F]=P[E]+P[F]-P[E\cap F]$
$P[E]=P[E-F]+P[E\cap F]\implies P[E-F]=P[E]-P[E\cap F]$
$(E\cup F)=(E-F)\cup(E\cap F)\cup(F-E)$
$P[E\cup F]=P[E-F]+P[E\cap F]+P[F-E] =$
$P[E]-P[E\cap F]+P[E\cap F]+P[F]-P[E\cap F] =$
$P[E]+P[F]-P[E\cap F]$
```

Proposizione 4
$P[\cup_{i=1}^{n}E_i] = \sum\limits_{i}{P[E_i]}-\sum\limits_{i<j}{P[E_i\cap E_j]}+\ldots+(-1)^{n+1}P[E_1\cap E_2\cap\ldots\cap E_n]$
### Probabilità condizionata
Siano $E$ ed $F$ due eventi, si chiama probabilità di $E$ dato $F$, e scriveremo $P[E|F]$, la probabilità che si verifichi l'evento $E$ supponendo che si sia verificato l'evento $F$
$P[E|F]=\frac{P[E\cap F]}{P[F]}\;\;P[F]>0$
$\implies\begin{cases}P[E\cap F] = P[F]\cdot P[E|F]\\P[E\cap F] = P[E]\cdot P[F|E]\\\end{cases}$
### Regole della catena
Dati $n$ eventi $E_1,E_2,\ldots,E_n$ la cui intersezione ha probabilità positiva ($P[E_1\cap E_2\cap\ldots\cap E_n]>0$), si ha:
$P[E_1\cap E_2\cap\ldots\cap E_n]=$
$P[E_1]\cdot P[E_2|E_1]\cdot P[E_3|E_1\cap E_2]\cdot P[E_4|E_1\cap E_2\cap E_3]\cdot\ldots\cdot P[E_n|E_1\cap E_2\cap\ldots\cap E_{n-1}]$

```ad-def Partizione di $\Omega$
Si dice partizione di $\Omega$ un insieme di eventi $E_i$ (*finito* o *numerabile*) con le seguenti caratteristiche:

1. Ogni $E_i$ ha probabilità diversa da $0$;
   $0<P[E_i]\leq1$
2. Gli $E_i$ sono mutualmente esclusi;
   $P[E_i\cap E_j] = 0$
3. L'unione di tutti gli $E_{i}$ copre $\Omega$;
   $\bigcup_{i=1}^{n}{E_i}=\Omega$
```
### Formula della probabilità totali
Sia $\{E_{i}\}$ una partizione di $\Omega$, sia $F$ un evento qualsiasi contenuto in $\Omega$, allora
$P[F]=\sum\limits_{i=1}^{n}{P[F|E_i]P[E_i]}$

```ad-dem
$P[F]=\sum\limits_{i=1}^{n}{P[F|E_i]P[E_i]}\leftarrow$
$F=F\cap\Omega=F\cap(\bigcup_{i}E_i)=\bigcup_i(F\cap E_i)$
$P[F]=P[\bigcup_{i}{(F\cap E_i)}]=\sum\limits_{i}{P[F\cap E_i]}=$
$=\sum\limits_{i}{P[F|E]P[E_i]}$
```
### Legge condizionata o delle alternative
Sia $\{E_{i}\}$ una partizione di $\Omega$ e siano $G$ ed $F$ due eventi qualsiasi, allora
$P[F|G] = \sum\limits_{i}{P[F|E_i\cap G]\cdot P[E_i|G]}$
dove la sommatoria è estesa unicamente ai casi $P[E_i\cap G]\neq\emptyset$
### Formula di Bayes
Dato un evento $F$ e data una partizione $\{E_{h}\}$ di $\Omega$, si ha
$P[E_{h}|F]=\frac{P[F|E_{h}]\cdot P[E_{h}]}{\sum\limits_{i}{P[F|E_{i}]\cdot P[E_{i}]}}$

```ad-dem
$P[E_h\cap F]=P[F|E_h]P[E_h]=P[E_h|F]P[F]$
$P[E_h|F]=\frac{P[F|E_h]\cdot P[E_h]}{P[F]}=$
$=\frac{P[F|E_h]\cdot P[E_h]}{\sum\limits_{i}{P[F|E_i]\cdot P[E_i]}}$
```
### Eventi indipendenti
#### Osservazioni
$P[E|F]>P[E]$ l'evento $F$ è favorevole ad $E$
$P[E|F]<P[E]$ l'evento $F$ è sfavorevole ad $E$
$P[E|F]=P[E]$ l'evento $F$ è ininfluenzato oppure indipendente da $E$
#### Proprietà
Se $E$ è indipendente da $F$ allora $F$ è indipendente da $E$
$P[E|F]=P[E]\implies P[F|E]=P[F]$

```ad-dem (da ricontrollare, mi sa che il prof l'abbia sbagliata)
$P[E\cap F]=P[E|F]P[F]=P[E]P[F]$
$P[E\cap F]=P[F|E]P[E]=P[E]P[F]$
$P[F|E]=P[F]$
allora
$P[E\cap F]=P[E]P[F]$
$P[E\cap F]=P[E|F]P[F]$
```
#### Proposizione
Se $E$ ed $F$ sono indipendenti allora sono indipendenti anche $E$ e $\bar{F}$

```ad-dem
$E=(E\cap F)\cup(E\cap\bar{F})$
$P[E]=P[E\cap F]+P[E\cap\bar{F}]=P[E]P[F]+P[E\cap\bar{F}]$
$P[E\cap\bar{F}]=P[E]-P[E]P[F]=P[E](1-P[F])=P[E]P[\bar{F}]$
```

```ad-def
Una famiglia di $n$ eventi $E_1,E_2,\ldots,E_n$ si dice famiglia di eventi indipendenti se gli eventi $\{E_i\}$ sono a due a due , a tre a tre,... e così via fino ad $n$ ad $n$ indipendenti
```
## Combinatoria
### Disposti
Si dice che $n$ oggetti sono ordinati (o disposti) in un allinemaneto quando sono collocati in n posti numerati da 1 ad n
### Permutazione
Si dice permutazione di $n$ oggetti distinti ogni allineamento deli oggetti stessi, due permutazioni sono distinte quando differiscono per il posto occupato da almeno un oggetto.
Indicheremo con $P_{n}$ il numero di permutazioni

$P_n=n!$

```ad-th
Il numero di permutazioni distinte di n oggetti qei quali $q_1$ uguali tra loro, $q_2$ uguali tra loro e distinti dai precedenti,..., $q_h$ uguali tra loro e distinti dai precedenti(dove $q_1+q_2+\ldots+q_h=n$) è
$P^{*}_{q_1q_2\dots q_h}=\frac{n}{q_1!\cdot q_2!\cdot\ldots\cdot q_h!}$
Osservazione:
se gli oggetti sono solo di due tipo $(k,n-k)$
$P^{*}_{k,n-k}=\frac{n!}{k!(n-k)!}=\binom{n}{k}$
```
### Disposizioni
Si dice disposizione semplice di n oggetti di classe m ogni allineamento di m oggetti scelti fra gli n
$D_{n,k}=\frac{n!}{(n-k)!}$
Si dice disposizione con ripetizione di n oggetti di classe m ogni allineamento di m oggetti scelti fra gli n con la convenzione che ogni oggetto può essere ripetuto una o più volte
$D^{*}_{n,k}=n^k$
### Combinazioni
Si dice combinazione di n oggetti di classe k, ogni raggruppamento di k oggetti comunque scelti tra gli n
$C_{n,k}=\binom{n}{k}$
Si dice combinazione con ripetizione di n oggetti di classe k, ogni raggruppamento di k oggetti comunque scelti tra gli n con la convenzione che ogni oggetto può essere ripetuto più volte
$C^{*}_{n,k}=\binom{n+k-1}{k}$
## Variabili aleatorie
consideriamo lo spazio di probabilità $(\Omega,\mathscr{F},P)$
$X:\Omega\to\mathbb{R}\;\;\;\;\;\;X(\omega)=x\;\;\;\;x\in\mathbb{R}$
$\Omega=\{\omega_1,\omega_2,\ldots,\omega_n\}$

```ad-def
title: variabile aleatoria
Dato uno spazio di probabilità $(\Omega,\mathscr{F},P)$ si dice variabile aleatoria una corrispondenza tra gli evlementi di $\Omega$ e i numeri (reali), tale corrispondenza deve soddisfare la condizione
$A_t=\{\omega|X(\omega)\leq t\}\in\mathscr{F}\;\;\;\;\forall t\in\mathbb{R}$
```

È detto supporto l'insieme dei valori che la variabile aleatoria può assumere

```ad-def
title: Funzione di ripartizione
Data la variabile aleatoria $X$, è detta funzione di ripartizione di $X$ la funzione
$F_{X}(t)=P[X\leq t]=P[A_{t}]$
$F_{X}(t):\mathbb{R}\to[0,1]$
```
### Proprietà
1. $F_{X}$ è monotona non decrescente, cioè
   $F_x(t_1)\leq F_x(t_2)\impliedby t_1\leq t_2$
   $A_{t_1}\subseteq A_{t_2}\implies P[A_{t_1}]\leq P[A_{t_2}]$
2. $\lim\limits_{t\to-\infty}F_{X}(t)=0$ $\lim\limits_{t\to+\infty}F_{X}(t)=1$
3. Per ogni valore $x_{0}\in\mathbb{R}$
   $P[X=x_{0}]=\lim\limits_{t\to x_{0}^{+}}F_{X}(t)-\lim\limits_{t\to x_{0}^{-}}F_{X}(t)$
4. La funzione di ripartizione $F_{X}$ è continua a destra, ossia:
   per ogni valore $x_{0}\in\mathbb{R}$
   $F_{X}(x_{0}) = P[X\leq x_{0}] = \lim\limits_{t\to x_{0}^{+}}F_{X}(t)$

```ad-def
title: Variabile aleatoria discreta
Se la variabile aleatoria $X$ può assumere solo un numero finito (o al più numerabile) di valori, la relativa $F_{X}$ sarà costante a tratti
e la variabile viene detta discreta
Se $X$ può assumere i valori di un internvallo $I\subset\mathbb{R}$, allora $F_{X}$ è generalmente continua e la variabile è detta continua
```
### Densità di variabili aleatorie
#### Caso discreto
Una variabile aleatoria $X$ discreta può assumeresolo alcuni valori $x_i$ ($i=1,\ldots,n$ / $i=1,\ldots$)
$P[X=x_i]\rightarrow\sum\limits_i{P[X=x_i]}=1$

```ad-def
title: Densità di probabilità
La funzione $P_{X}:\mathbb{R}\to[0,1]$ definita dalla relazione
$P_{X}(x)=P[X=x]=\begin{cases}P[X=x_{i}]&x=x_{i} &\text{per un certo i}\\0 &x\neq x_{i} &\forall i\end{cases}$
```

$A=\{x_{i}|a<x_{i}\leq b\}$
$P[a<X\leq b]=\sum\limits_{i\in A} P[X=x_{i}]=\sum\limits_{i\in A} P_{X}(x_{i})$
assioma:
$P[a<X\leq b]=P[a<X<b]+P[X=b]$
$P[a<X\leq b]\neq P[a<X<b]$

$F_{X}(t)=P[X\leq t]=\sum\limits_{x_{i}<t}P_{X}(x_{i})$
#### Caso Continuo
Per definire la probabilità consideriamo la funzione di ripartizione
$F_x(a)=P[X\leq a]$
$F_{x}(t)=\int\limits_{-\infty}^{t}f_{X}(x)dx$
la funzione $f_{X}(x)$ è detta funzione densità

$P[a\leq X\leq b] = F_{X}(b)-F_{X}(a)=\int\limits_{a}^{b}f_{X}(x)dx$

```ad-dem
$I_a=(-\infty,a)$
$I_b=(-\infty,b)$
$I_{ab}=[a,b]$
$P[X\in I_b]=P[I_b]=P[I_{a}\cup I_{ab}]=P[I_{a}] + P[I_{ab}]$
$P[I_{a}\cup I_{ab}]=P[I_{b}]-P[I_{a}]=P[X\leq b]-P[X\leq a]=F_{X}(b)-F_{X}(a)=\int\limits_{-\infty}^{b}f_X(x)dx-\int\limits_{-\infty}^{a}f_X(x)dx=\int\limits_{a}^{b}f_X(x)dx$
```

```ad-def
title: Densità di probabilità
Sia $X$ una variabile aleatoria continua, se esiste una funzione $f_X$ tale che $\forall a,b\in\mathbb{R}$
$P[a<X\leq b]=\int\limits_{a}^{b}f_X(x)dx$
allora $f_X$ è detta funzione densità di probabilità
```
#### Osservazioni
1. $f_{X}(x)=0$ se $x\not\in I\subseteq\mathbb{R}$ dove $I$ è il supporto di $X$
2. $P[a<X\leq b]=P[a<X<b]$
#### Proprietà
Se $f_X$ è la funzione densità di una variabile aleatoria continua allora

1. $f_{X}(x)\geq0\quad\forall x\in\mathbb{R}$ e $f(x)>0$ se $x\in I$
2. $\int\limits_{-\infty}^{+\infty}f_{X}(x)dx=1$

````ad-th
Sia $X$ una variabile aleatoria continua e sia $Y=g(X)$
Se $g$ è una funzione invertibile nel supporto $I$ di $X$ e $h$ è la sua inversa, allora
$f_Y(y)=f_X(h(y))|h'(y)|$
```ad-dem
$\int\limits_{a}^{b}f_X(x)dx=\int\limits_{g(a)}^{g(b)}f_{X}(h(y))|\frac{dx}{dy}|dy=\int\limits_{g(a)}^{g(b)}f_{X}(h(y))|h'(y)|dy$
````
### Valore Atteso
Data una variabile aleatoria $X$, dotata di funzione di ripartizione, il suo valore atteso (valore medio o speranza matematica), se esiste, è data da
$E[X]=\int\limits_{0}^{+\infty}[1-F_X(t)]dt-\int\limits_{-\infty}^{0}F_{X}(t)dt$
si dimostra che:

- caso discreto: $E[X]=\sum\limits_{i}x_{i}P[X=x_{i}]$
- caso continuo: $E[X]=\int\limits_{-\infty}^{+\infty}xf_X(x)$

```ad-def
title: Moda
Sia $X$ una variabile aleatoria, discreta o continua, si chiama moda di $X$ il valore, se esiste, per cui è massima la densità
```

```ad-def
title: Quantile
Dato $\alpha\in(0,1)$, si dice quantile di ordine $\alpha$ della variabile aleatoria $X$ il più piccolo numero $x_\alpha$ tale che
$P[X<x_{\alpha}]\leq \alpha \leq P[X\leq x_{\alpha}]$
```

```ad-def
title: Mediana
Si dice mediana della variabile aleatoria $X$ il quantile di ordine $0.5$($x_{0.5}$)
```

```ad-def
title: Varianza
Data una variabile aleatoria $X$, il cui valore atteso vale $E[X]=\mu$ si chiama varianza di $X$, e si indica con $Var[X]$, il seguente valore atteso
$Var[X]=E[(X-\mu)^2]$
```
#### Proprietà
$Var[X]=E[X^2]-\mu^2$

```ad-dem
$Var[X]=E[(X-\mu)^{2}]=$
$=E[(X^{2}+\mu^{2}-2X\mu)]=$
$=E[X^{2}]+E[\mu^{2}]-E[2X\mu]=$
$=E[X^{2}]+\mu^{2}-2\mu E[X]=$
$=E[X^{2}]+\mu^{2}-2\mu^{2}=E[X^{2}]-\mu^{2}$
```
### Disuguaglianza di Markov
Sia $X$ una variabile aleatoria e $g:\mathbb{R}\to\mathbb{R}$ tale che $g(x)\geq0\quad\forall x\in\mathbb{R}$
Allora, se esiste $E[g(x)]$, si ha:
$P[g(x)\geq N]\leq \frac{E[g(x)]}{N}\quad\forall N>0$

```ad-dem
$E[x]=\int\limits_{-\infty}^{+\infty}xf_{X}(x)dx$
$E[g(x)]\int\limits_{-\infty}^{+\infty}g(x)f_{X}(x)dx$
$E[g(x)]\int\limits_{-\infty}^{+\infty}g(x)f_{X}(x)dx\geq$
$\geq\int\limits_{\{x|g(x)\leq N\}}g(x)f_X(x)dx\geq\int\limits_{\{x|g(x)\leq N\}}Nf_X(x)dx=$
$=N\int\limits_{\{x|g(x)\leq N\}}f_X(x)dx=NP[g(x)\geq N]$
$E[g(x)]\geq N\cdot P[g(x)\geq N]$
```
### Disuguaglianza di Cebicev
$P[|X-E[X]|\geq \epsilon]\leq \frac{Var[X]}{\epsilon^{2}}\quad\quad\forall\epsilon>0$

```ad-def Momenti di una variabile aleatoria
Si dice momento $k$-esimo di una variabile aleatoria $X$, e si indica con $\mu_k$, la seguente quantità
$\mu_{k}=E[X^{k}]$

- Caso discreto: $\mu_{k}=\sum\limits\limits_{i}x_{i}^{k}P_{X}(x_{i})$
- Caso continuo: $\int\limits_{-\infty}^{+\infty}x^{k}f_{X}(x)dx$
```
#### Osservazione
$Var[X]=\mu_2-(\mu_1)^2$

```ad-def
title: Funzione generativa dei momenti
$\mu_{X}(t)=E[e^{tx}]$
```
#### Proprietà
- $\mu_{1}=\left[\frac{d}{dt}\mu_{X}(t)\right]_{t=0}$
  ```ad-dem
  $\mu_1=\int\limits_{-\infty}^{+\infty}xf_X(x)dx$
  $\mu_{X}(t)=\int\limits_{-\infty}^{+\infty}e^{tx}f_{X}(x)dx$
  $\frac{d}{dt}\mu_{X}(t)=\int\limits_{-\infty}^{+\infty}xe^{tx}f_{X}(x)dx$
  $[\frac{d}{dt}\mu_{X}(t)]_{t=0}=\int\limits_{-\infty}^{+\infty}xf_X(x)dx=\mu_1$
  ```
- $\frac{d^{k}}{dt^{k}}(e^{tx})=x^{k}e^{tx}$
- $\mu_{k}=\left[\frac{d^{k}}{dt^{k}}\mu_{X}(t)\right]_{t=0}$
- Siano $X$ e $Y$ due variabili aleatorie, se
  $\mu_{X}(t)=\mu_{Y}(t)\quad\forall t\in[-t_{0},t_{0}]$
  allora $X$ e $Y$ hanno la medesima densità
- Se $X$ possiede la funzione generatrice dei momenti e $Y=aX+b$, allora esiste anche $\mu_{Y}(t)$ e
  $\mu_{Y}(t)=e^{tb}\mu_{X}(at)$
## Schemi e distribuzioni
### Schema di Bernoulli
Consideriamo un esperimento che si può concludere solo in due modi chiamati convenzionalmente successo ed insuccesso; un esperimento di questo tipo è detto di ***Bernoulli***

Sia $p$ la probabilità che si verifichi il successo e $q$ quella dell'insuccesso $q = 1-p$

Una sequenza di **prove di Bernanilli**, tra di loro indipendenti, per le quali la probabilità del successo si mantiene invariata è detto ***schema di Bernoulli***
### Distribuzione di Bernoulli
Una variabile aleatoria $X$ che vale $1$ se la **prova di Bernoulli** si è conclusa con il successo e $0$ altrimenti è detta **variabile aleatoria di Bernoulli** di parametro $p$ in simboli $X\sim Ber(p)$
#### Densità
$P[X=n] = p^{n}q^{1-n}$

$P[X=1] = p$; $P[X=0] = q$
#### Momenti
```ad-def
$\mu_{X}(t) = E[e^{Xt}]$; $E[X] = \frac{d}{dt}\mu_{X}(t)|_{t=0}$
```

$\mu_{X}(t) = pe^{t}+q$; $E[X] = p$; $Var[X] = pq$

```ad-dem
$E[X] = pe^{t}|_{t=0} = p$
$[Var[X]=E[(X-E[X])^{2}]]=E[X^{2}]-E^{2}[X]$
$E[X^{2}]= \frac{d^{2}}{dt^{2}}\mu_{X}(t)|_{t=0} = pe^{t}|_{t=0}=p$
$Var[X] = p-p^{2} = p(1-p) = pq$
```
### Distribuzione Binomiale
Le variabili aleatorie $X$ che conta il numero di successi in un prova di uno **schema di Bernoulli**, dove $p$ è la probabilita del singolo successo, è detta *Binomiale*.

In simboli
$X\sim Bin(p)$
#### Densità
$P[X=k] = \binom{n}{k}p^{k}q^{n-k}$

```ad-dem
$n$ tentativi
$k$ successi, $n-k$ insuccessi

Probabilità di $k$ successi è $p^{k}$
Probabilità di $n-k$ insuccessi è $q^{n-k}$
```
#### Momenti
$\mu_{X}(t) = (pe^{t}+q)^{n}$; $E[X] = np$; $Var[X] = npq$

```ad-dem
$\mu_{X(t)}= \sum\limits_{k=0}{n}e^{tk}\binom{n}{k}p^{k}q^{n-k} = \sum\limits_{k=0}{n}\binom{n}{k}(pe^{t})^{k}q^{n-k} = (pe^{t}+q)^{n}$
$E[X] = \frac{d}{dt}m_X(t)|_{t=0} = n(pe^{t}+q)^{n-1}pe^{t}|_{t=0} = np$
$E[X^{2}] = \frac{d^{2}}{dt^{2}}\mu_{X}(t)|_{t=0} =$
$= np[(n-1)(pe^{t}+q)^{n-2}pe^{2t}+(pe^{t}+q)^{n-1}e^{t}]|_{t=0} =$
$= np[(n-1)p+1] = np[np-p+1] = n^{2}p^{2}-np^{2}+np$
$Var[X] = E[X^{2}] - E^{2}[X] = n^{2}p^{2}-np^{2}+np-n^{2}p^{2} = np(1-p) = npq$
```
### Distribuzione geometrica
La variabile aleatoria che conta il numero di prove di uno **schema di Bernoulli** fino alla comparsa del primo successo è detta ***geometrica*** di parametro $p$, dove $p$ rappresenta la probabilità del singolo successo;
$X\sim Geo(p)$
#### Densità
$P[X=k] = pq^{k-1}$

```ad-dem
$\{X=k\}$ corrisponde alla situazione in cui si sono verificati $k-1$ successi ed un successo
$P[X=k] = \underbrace{P[\text{insuccesso}]\cdot\ldots\cdot P[\text{insuccesso}]}_{k-1\text{ volte}}\cdot P[\text{successo}] = q^{k-1}p$
```
#### Momenti
$\mu_{X}(t) = \frac{pe^{t}}{1-qe^{t}}\;\;\;t<ln\frac{1}{q}$; $E[X] = \frac{1}{p}$; $Var[X] = \frac{q}{p^{2}}$

```ad-dem
$\mu_{X(t)}= \sum\limits_{k=1}^{\infty}e^{tk}q^{k-1}p = p\sum\limits_{k=1}^{\infty}e^{tk}q^{k-1} = pe^{t}\sum\limits_{k=1}^{\infty}e^{t(k-1)}q^{k-1} = pe^{t}\sum\limits_{k=1}^{\infty}(qe^{t})^{k-1} = pe^{t}\sum\limits_{k=0}^{\infty}(qe^{t})^{k} = \frac{pe^{t}}{1-qe^{t}}$
$t<ln\frac{1}{q}$
$E[X] = \frac{d}{dt}m_X(t)|_{t=0} = \frac{pe^{t}(1-qe^{t})-pe^{t}(-qe^{t})}{(1-qe^{t})^{2}}|_{t=0} = \frac{pe^{t}}{(1-qe^{t})^{2}}|_{t=0} = \frac{p}{p^{2}} = \frac{1}{p}$
$E[X^{2}] = = \frac{pe^{t}[(1-qe^{t})^{2} - 2(1-qe^{t})(-qe^{t})]}{(1-qe^{t})^{4}}|_{t=0} = \frac{p[(1-q)^{2} - 2(1-q)(-q)]}{(1-q)^{4}} = \frac{1+q}{p^{2}}$
$Var[X] = E[X^{2}] - E^{2}[X] = \frac{(1+q)}{p^{2}} - \frac{1}{p^{2}} = \frac{q}{p^{2}}$
```
### Distribuzione binomiale negativa
La variabile aleatoria che conta il numero di tentativi necessari al verificarsi dell'$n$-esimo successo di uno **schema di Bernoulli** è detta ***binomiale negativa*** di parametri $n$ e $p$
$X\sim \overline{Bin}(n,p)$
#### Densità
$P[X=k] = \binom{k-1}{n-1}p^{n}q^{k-n}$
#### Momenti
$\mu_{X}(t) = \left(\frac{pe^{t}}{1-qe^{t}}\right)^{n}\;\;\;t<ln\frac{1}{q}$; $E[X] = \frac{n}{p}$; $Var[X] = n\frac{q}{p^{2}}$
### Distribuzione di Poisson
***Distribuzio di Poisson*** come caso limite della **distribuzione binomiale** con $n\to\infty$; $p\to0$; $np\to\mu\neq0$

$$
\displaylines{
P[X=k] = \binom{n}{k}p^{k}q^{n-k} = \\
= \frac{n!}{k!(n-k)!}p^{k}\frac{q^{n}}{q^{k}} = 
\frac{1}{k!} \frac{n!}{(n-k)!} p^{k} \frac{(1-p)^{n}}{(1-p)^{k}} = \\
= \frac{1}{k!} \underbrace{\frac{n!}{(n-k)!} \frac{1}{n^{k}} (np)^{k}} (1-p)^{n} \frac{1}{(1-p)^{k}} \\
\\
\frac{n!}{(n-k)!}\frac{1}{n^{k}}\sim1 \\
\frac{n!}{(n-k)!}\frac{1}{n^{k}}(np)^{k}\sim\mu^{k} \\
(1-p)^{n} \to \left(1- \frac{np}{n}\right)^{n} \sim
\left(1-\frac{\mu}{n}\right)^{n} \to e^{-\mu} \\
\frac{1}{(1-p)^{k}} \overset{p\to0}{\to} 1 \\ 
\\
P[X=k] = \frac{1}{k!} \mu^{k} e^{-\mu} = \frac{\mu^{k}e^{-\mu}}{k!}
}
$$

La variabile aleatoria avente densità $P[X=k] = \frac{\mu^{k}e^{-\mu}}{k!}$ è detta ***variabile di Poisson*** di parametro $\mu$
$X\sim Poi(\mu)$
#### Densità
$P[X=k] = \frac{\mu^{k}e^{-\mu}}{k!}$
#### Momenti
$\mu_{X}(t) = e^{\mu(e^{t}-1)}$; $E[X] = Var[X] = \mu$

```ad-dem
$\mu_{X}(t) = \sum\limits_{k=0}^{\infty}e^{tk} \frac{e^{-\mu}\mu^{k}}{k!} = e^{-\mu}\sum\limits_{k=0}^{\infty}\frac{(e^{t}\mu)^{k}}{k!} = e^{-\mu}e^{\mu e^{t}} = e^{\mu(e^{t}-1)}$
$E[X] = \frac{d}{dt}m_X(t)|_{t=0} = \mu e^{\mu(e^{t}-1)} e^{t}|_{t=0} = \mu$
$E[X^{2}] = \frac{d^{2}}{dt^{2}}\mu_{X}(t)|_{t=0} = \mu [e^{\mu(e^{t}-1)}\mu e^{t}e^{t} + e^{\mu(e^{t}-1)}e^{t}] |_{t=0} = \mu [e^{\mu(e^{t}-1)}\mu e^{2t} + e^{t}e^{\mu(e^{t}-1)}]_{t=0} = \mu(\mu + 1)$
$Var[X] = E[X^{2}] - E^{2}[X] = \mu(\mu + 1) - \mu^{2} = \mu$

```
### Schema di Poisson
In un certo intervallo di tempo (o di spazio) si manifestano degli eventi, chiamati "arrivi", che soddisfano le seguenti condizioni:

1. non vi sono più arrivi simultanei (non ci sono sovrapposizioni)
2. il numero medio di arrivi nell'unità di tempo è costante (intensità è costante)
3. ciascun arrivo avviene in modo indipendente dagli altri
### Processo di Poisson
```ad-def
La variabile aleatoria $N_{t}$ che conta in un certo intervallo di tempo $t$ il numero di arrivi in uno *schema di Poisson* di intensità $1$ è detta ***Processo di Poisson***
```
#### Caratteristiche
1. $N_{0} = 0$
2. $N_{t+s}=N_{t}+N_{s}$
3. se $\Delta t\to0$
   $P[N_{t+\Delta t}-N_{t} = 1] = \lambda\Delta t +o(\Delta t)$
   $P[N_{t+\Delta t}-N_{t} \geq 1] = o(\Delta t)$
   $P[N_{t+\Delta t}-N_{t} = 0] = 1 - \lambda\Delta t +o(\Delta t)$
#### Proprietà
Sia $N_{t}$ un **processo di Poisson** di intensità $\lambda$, allora
$N_{t}\sim Poi(\mu=\lambda t)$
### Distribuzione Esponenziale
La variabile aleatoria "tempo di attesa del primo arrivo in un processo di Poisson di intensità $\lambda$" è detta ***Esponenziale di variabile $\lambda$***
#### Densità
$f_{X(x) =}\begin{cases} 0 & x<0 \\ \lambda e^{-\lambda x} &x>0 \end{cases}$

```ad-dem
$F_{X}(t) = P[X\leq t]$
$P[X>t] = 1-P[X\leq t] = 1-F_{X}(t) \implies F_X(t) = 1-P[X>t] = 1-P[N_{t} = 0] = 1-i^{\lambda t} \implies f_{X(t)}= \frac{d}{dt}F_{X(t)}= \lambdae^{-\lambda t}$
```
#### Momenti
$\mu_{X}(t) = \frac{\lambda}{\lambda-t}\;\;\;t<\lambda$; $E[X] = \frac{1}{\lambda}$; $Var[X] = \frac{1}{\lambda^{2}}$

```ad-dem
$\mu_{X}(t) = \int\limits_{-\infty}^{+\infty}d^{tx}f_{X}(x)dx = \int\limits_{0}^{+\infty}d^{tx}\lambda e^{-\lambda x}dx = \lambda\int\limits_{0}^{\infty}e^{(t-\lambda)x}dx = \lambda \left[\frac{e^{(t-\lambda)x}}{t-\lambda}\right]_{0}^{\infty} = \lambda \left[\frac{e^{(t-\lambda)\infty}}{t-\lambda} - \frac{1}{t-\lambda}\right] = \frac{\lambda}{\lambda-t}$
```
#### Proprietà (Assenza di memoria)
$P[X>t+s|X>t] = P[X>t+s]$
### Distribuzione Gamma
La variabile aleatoria "tempo di attesa dell'$n$-esimo arrivo di un **processo di Poisson**" è detta ***Gamma*** di parametri $n$ e $\lambda$
$X\sim\Gamma(n,\lambda)$
#### Densità
$f_{X}(x) = \begin{cases} 0 & x<0 \\ \frac{1}{(n-1)!}\lambda^{n}x^{n-1}e^{-\lambda x} & x>0 \end{cases}$
### Distribuzione di Weibul
Sia $Y\sim Esp(\lambda)$ e sia $\lambda>0$, è detta ***variabile di Weibul*** la variabile aleatoria
$X=Y^{\frac{1}{\alpha}}$;
$X\sim Wei(\alpha,\lambda)$
#### Densità
Densità di **Weibul**: Funzione rischio
$f_{X}(x) = \begin{cases} 0 & x<0 \\ \lambda\alpha x^{\lambda-1}e^{-\lambda x^{\alpha}} & x>0 \end{cases}$
$F_{X(x)}= \begin{cases} 0 & x<0 \\ 1-e^{-\lambda x\alpha} & x\geq0 \end{cases}$

```ad-dem
$Y\geq0,X=Y^{\frac{1}{\alpha}}$
$F_{X}(x) = P[X\leq x]=P\left[Y^{\frac{1}{\alpha}}\leq x\right]= P[Y\leq x^{\alpha}] = F_{Y}(x^{\alpha}) = 1-e^{-\lambda x\alpha}$
$f_{X}(x) = F'_X(x)$
```
##### Osservazione
$E[X] = \alpha^{\frac{-1}{\lambda}} [\Gamma(1+\frac{1}{\lambda})$
$Var[X] = \alpha^{\frac{-1}{\lambda}}\left[\Gamma\left(1+\frac{1}{\lambda}\right)-\Gamma\left(1+\frac{1}{\lambda}\right)\right]$
#### Funzione di rischio
Variabile aleatoria $T$ = "tempo di funzionamento"
Probabilità che, condizionatamente al fatto che fino all'istante $\bar{t}$  l'apparecchio fosse in funzione esso si guasti immediatamente dopo ossia all'istante $\bar{t}+\Delta t$ è
$P[T\leq \bar{t}+\Delta t|T>\bar{t}]$
### Distribuzione di Gauss o Normale
Una variabile aleatoria $X$ è detta distribuita secondo una normale (o gaussiana) di parametri $\mu\in\mathbb{R}$ .
$\sigma\in\mathbb{R}^{+}$ se ha densità di probabilità
$f_{X}(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^{2}}{2\sigma^{2}}}$
#### Proprietà
1. $F_{X}(x)$ è simmetrica rispetto alla retta $x=\mu$
2. ha un massimo assoluto in $(\mu, \frac{1}{\sigma\sqrt{2\pi}})$
3. ha asintoto orizzontale $y=0$
4. ha due flessi in $(\mu-\sigma, \frac{1}{\sigma\sqrt{2\pi e}})$, $(\mu+\sigma, \frac{1}{\sigma\sqrt{2\pi e}})$
5. $\int\limits_{-\infty}^{+\infty}f_{X}(x)dx = 1$
6. all'aumentare di $\sigma$ il $max$ diminuisce
7. se $\mu=0$ è simmetrica rispetto all'asse $\vec{y}$
8. $E[X] = \mu$, $Var[X] = \sigma^{2}$
#### Funzione di ripartizione
$F_{X}(t) = P[X\leq t] = \int\limits_{-\infty}^{+\infty} \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{1}{2}\frac{(x-\mu)^{2}}{\sigma^{2}}}dx$
### Distribuzione normale standardizzata
$f(x) = \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}x^{2}}$

```ad-dem
$f_{X}(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{1}{2}z^{2}}$
$z = \frac{x-\mu}{\sigma}$; $x = \sigma z+\mu$; $dx = \sigma dz$
$\frac{1}{\sigma\sqrt{2\pi}}\int\limits_{-\infty}^{+\infty}e^{-\frac{1}{2} \left(\frac{x-\mu}{\sigma}\right)^{2}}dx \frac{1}{\sigma\sqrt{2\pi}}\int\limits_{-\infty}^{+\infty}e^{-\frac{1}{2}z^{2}} \sigma dz = \frac{1}{\sqrt{2\pi}}\int\limits_{-\infty}^{+\infty}e^{-\frac{1}{2}z^{2}} dz$
$f(z) = \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}z^{2}}$
```
## Vettori Aleatori
```ad-def
È detto ***vettore aleatorio***, o ***variabile aleatoria*** multidimensionale, un vettore le cui componenti sono variabili aleatorie
$X\equiv(X_{1},X_{2},\ldots,X_{n})$
```

$P[(X_{1}\cap X_{2}\cap\ldots\cap X_{n})]\equiv P[X_{1},X_{2},\ldots,X_{n}]$
Se abbiamo le variavili aleatorie $X$, $Y$ discrete

- $\sum\limits_{i}\sum\limits_{j}P[X=i,Y=j] = 1$, $\sum\limits_{i}P[X=i] = 1$, $\sum\limits_{j}P[Y=j = 1$
- I valori $P[X=i,Y=j]$ formano la densità discreta congiungta del vettore $(X,Y)$
- Le densità $P[X=i]$, $P[Y=j]$ sono dette densità marginali

Osservazione:
è sempre possibile ricreare le prob. marginali dalle prob. congiunte, ma non è vero il viceversa

```ad-def
title: Funzione di ripartizione congiunta
Dato un vettore aleatorio $(X,Y)$, è detta funzione di ripartizione congiunta la funzione
$F_{XY}(x,y) = P[X\leq x,Y\leq y]$
```

```ad-def
title: Funzione di ripartizione marginale
Dato una funzione di ripartizione congiunta $F_{XY}$, è definita la funzione di ripartizione marginale come
$F_{X}(x) = P[X\leq x] = P[X\leq x,Y<+\infty] = \lim\limits_{y\to+\infty}F_{XY}(x,y)$
```
### Proprietà
$\forall x\in\mathbb{R} \lim\limits_{y\to-\infty}F_{XY}(x,y)=0, \lim\limits_{y\to+\infty}F_{XY}(x,y)=F_{X}(x)$
$\forall y\in\mathbb{R} \lim\limits_{x\to-\infty}F_{XY}(x,y)=0, \lim\limits_{x\to+\infty}F_{XY}(x,y)=F_{Y}(y)$
### Densità congiunta (caso discreto)
Si dice densita congiunta del vettore aleatorio discreto $(X,Y)$, e si indica con $P_{XY}$, l'insieme dei valori
$P_{XY}(x_{i},y_{j}) = P[X=x_{i},Y=y_{j}]$
#### Densità marginale
$P_{X}(x_{i}) = \sum\limits_{j(y_{j})}P_{XY}(x_{i},y_{j})$
$P_{Y}(y_{j}) = \sum\limits_{i(x_{i})}P_{XY}(x_{i},y_{j})$
### Densità congiunta (caso continuo)
Dato un vettore aleatorio continuo $(X,Y)$, è detta funzione di densità di probabilità la funzione $f_{XY}(x,y)$ per la quale, per ogni scelta di $a,b,c,d\in\mathbb{R}$

$$
\displaylines{
P[a<X<b,c<Y<d] = \\
= \int\limits_{a}^{b}\left(\int\limits_{c}^{d}f_{XY}(x,y)dy\right)dx = \\
= \int\limits_{c}^{d}\left(\int\limits_{a}^{b}f_{XY}(x,y)dx\right)dy\\
\int\limits_{a}^{b}dx\int\limits_{c}^{d}dy\;f_{XY}(x,y) \\
}
$$

Si dimostra che
$F_{XY}(s,t) = P[X<s,Y<t] = \int\limits_{-\infty}^{s}dx\int\limits_{-\infty}^{t}dy\;f_{XY}(x,y)$

$f_{X}(x) = \frac{dF_{X}(x)}{dx}$
$f_{Y}(y) = \frac{dF_{Y}(y)}{dy}$
$f_{XY}(x,y) = \frac{\delta^{2}}{\delta x\delta y} F_{XY}(x,y)$
#### Funzione densità marginale
Sono dette funzioni densità marginale
$f_{X}(x) = \int\limits_{-\infty}^{+\infty}f_{XY}(x,y)dy$
$f_{Y}(y) = \int\limits_{-\infty}^{+\infty}f_{XY}(x,y)dx$

Osservazione:
$\int\limits_{-\infty}^{+\infty}f_{X}(x)dx = 1$
$\int\limits_{-\infty}^{+\infty}f_{Y}(y)dy = 1$
## Variabili aleatorie indipendenti
Date $n$ variabili aleatorie $X_{i}$, con $i=1,\ldots,n$, esse si dicono indipendenti se, per ogni scelta degli intervalli $A_{i}$, si ha che
$P[X_{1}\in A_{1},X_{2}\in A_{2},\ldots,X_{n}\in A_{n}] = P[X_{1}\in A_{1}]\cdot P[X_{2}\in A_{2}]\cdot\ldots\cdot P[X_{n}\in A_{n}]$

Si dimostra che (nel caso di variabili indipendenti)
$P_{XY}(x_{i},y_{i}) = P_{X}(x_{i})P_{Y}(y_{i})$
$f_{XY}(x_{i},y_{i}) = f_{X}(x_{i})f_{Y}(y_{i})$
$F_{XY}(x,y) = F_{X}(x)F_{Y}(y)$
## Combinazioni di variabili aleatorie
```ad-th
Dato un vettore aleatorio $(X,Y)$ (discreto o continuo) la somma $U=X+Y$ delle sue componenti ha densità
$P_{U}(u) = \sum\limits_{k}P_{XY}(k,u-k)$ caso discreto
$f_{U}(u) = \int\limits_{-\infty}^{+\infty}f_{XY}(t,u-t)dt$ caso continuo
```

```ad-def
Sia $(X,Y)$ un vettore aleatorio e $g(X,Y)$ una funzione, $E[g(X,Y)]$, se esiste, è dato da
$$
\displaylines{
E[g(X,Y)] = \sum\limits_{i}\sum\limits_{j}g(x_{i},y_{j})P_{XY}(x_{i},y_{j})\;\;\;\text{c.d.} \\
E[g(X,Y)] = \int\limits^{+\infty}dx\int\limits^{+\infty}dy\;g(x,y)f_{XY}(x,y)\;\;\;\text{c.c.}
}
$$
```
### Proprietà
Per ogni copia di variabili aleatorie $(X,Y)$, il valore atteso della somma è uguale alla somma dei valori attesi
$E[X+Y]=E[X]+E[Y]$
### Covarianza
$Cov[X,Y] = E[(X-E[X])(Y-E[Y])]$
#### Proprietà
- $Cov[X,Y] = E[XY]-E[X]E[Y]$
- $Cov[X,\alpha] = 0$
- $Cov[X,Y] = Cov[Y,X]$
- $Cov[X,X] = Var[X]$
- $Cov[\alpha X,\beta Y] = \alpha\beta Cov[X,Y]$
- $Cov[X+Y,U+W] = Cov[X,V] +Cov[X,W] +Cov[Y,U] +Cov[Y,W]$
### Matrice di convarianza
Dato $X=(X_{1},X_{2},\ldots,X_{n})$, la matrice di convarianza($C_{X}$) è la matrice di elementi
$(C_{X})_{ij} = Cov[X_{i},X_{j}]$
### Coeficiente di correlazione
Date due variabili aleatorie $X$, $Y$, è detto ***coeficiente di correlazione*** ($\rho_{XY}$)
$\rho_{XY}= \frac{Cov[X,Y]}{\sqrt{Var[X]Var[Y]}}$

```ad-def
Si dicono incorrelate due variabili aleatorie $X$, $Y$ per cui $Cov[X,Y] = 0$
```
#### Proprietà
- $-1<\rho_{XY}<1$
- $|\rho_{XY}| = 1$ se unicamente tra $X$ e $Y$ esiste un valore deterministico lineare $Y=aX+b$ con $a,b\in\mathbb{R}$ che hanno lo stesso segno
- Se $X$ e $Y$ sono indipendenti, allora sono incorrelate
  ```ad-dem
  $Cov[X,Y] = E[XY]-E[X]E[Y]$
  $E[XY] = \sum\limits_{i}\sum\limits_{j}x_{i}y_{j}P[x_{i},y_{j}] = \sum\limits_{i}\sum\limits_{j}x_{i}y_{j}P[x_{i}]P[y_{j}] = \left(\sum\limits_{i}x_{i}P[x_{i}]\right)\left(\sum\limits_{j}y_{j}P[y_{j}]\right) = E[X]E[Y]$
  ```
- $Var[X+Y] = Var[X]+Var[Y]+2Cov[X,Y]$
- $Var[X-Y] = Var[X]+Var[Y]-2Cov[X,Y]$
- Se $X_{i}$ sono indipendenti $\implies Var\left[\sum\limits_{i}X_{i}\right] = \sum\limits_{i}Var[X_{i}]$
## Trasformazioni di vettori aleatori
$(X,Y)\to(U,V)$
$\begin{cases} u &= g_{1}(x,y) \\ v &= g_{2}(x,y) \end{cases}\iff\begin{cases} x &= h_{1}(u,v) \\ y &= h_{2}(u,v) \end{cases}$

```ad-th
Sia $(X,Y)$ un **vettore aleatorio**, continuo e sia $(U,V)=g(X,Y)$ una trasformazione invertibile con trasformazione inversa $h(U,V)$ allora
$f_{UV}(u,v) = f_{XY}(h_{1}(u,v),h_{2}(u,v))\cdot|det J|$
$J=\begin{bmatrix} \frac{\delta h_{1}}{\delta u} & \frac{\delta h_{1}}{\delta v} \\ \frac{\delta h_{2}}{\delta u} & \frac{\delta h_{2}}{\delta v} \end{bmatrix} \left(\equiv \frac{\delta(h_{1},h_{2})}{\delta(u,v)}\right)$
```
## Distribuzioni
### Distribuzione di Bernoulli
Une **variabile aleatoria** $X$ è distribuita secondo una **bernanlliana** di parametro $p\in[0,1]$, se essa può assumere valori $1$ e $0$ rispettivamente con probabilità $p$ e $1-p$
$p(s) = \begin{cases} p &\text{se }s=1 \\ 1-p &\text{se }s=0 \\ 0 &\text{altrimenti}\end{cases}$
$F_X(t) = \begin{cases} 0 &\text{se }t<0 \\ 1-p &\text{se }0\leq t<1 \\ 1 &\text{se }t\geq1\end{cases}$
### Distribuzione Binomiale
Siano $X_{1},X_{2},\ldots,X_{n}$ $n$ variabili **bernoulliane** diuguale parametro $p$ e indipendenti fra di loro
Sia $X=X_{1}+X_{2}+\ldots+X_{n}$. Questa **variabile aleatoria** è detta distribuita secondo una **binomiale** di parametro $n$ e $p$

```ad-th
$X$ può assumere $\forall k\in \mathbb{N}$ con $0\leq k\leq n$ con probailità
$P(X=k) = \binom{n}{k}p^{k}(1-p)^{n-k}$
```
### Distribuzione di Poisson
Si può considerare come caso particolare della **distribuzione Binomiale** che si otiene quando

1. il numero di variabili $X_{i}$ è $n\to\infty$
2. il parametro $p\to0$, ma $np=\lambda\in\mathbb{R}^{+}$
   $P(k) = \frac{\lambda^{k}}{k!}e^{-\lambda}\;\;\;k=0,1,2,\ldots$
   - $\lambda$ è un qualsiasi valore positivo equivalente al numero di successi che ci si aspetta che si verifichino in un dato intervallo di tempo (la frequenza media di accadimento edll'evento osservato)
   - $k$ p il numero delle occorrenza (successi) per cui si vuole prevedere la probabilità
### Distribuzione uniforme
È la distribuzione che assume un valore contenuto in un intervallo $[a,b]$

Una **variabile aleatoria** $X$ ha distribuzione uniforme in $[a,b]\subset\mathbb{R}$, se è assolutamente continua con densità di probabilità
$f_{X}(t)=\begin{cases} \frac{1}{b-a} &\text{se }t\in[a,b] \\ 0 &\text{altrimenti} \end{cases}$
$F_{X}(t)=\begin{cases} 0 &\text{se }t<a \\ \frac{t-a}{b-a} &\text{se }t\in[a,b] \\ 1 &\text{se }t>b \end{cases}$
$E[X] = \frac{a+b}{2}$
$Var[X] = \frac{(b-a)^{2}}{12}$
### Distribuzione esponenziale
Una **variabile aleatoria** $X$ è detta distribuita secondo un'**esponenziale** di parametro $\lambda\in\mathbb{R}^{+}$ se è assolutamente continua con densità di probabilità
$f_{X}(t)=\begin{cases} 0 &\text{se }t\leq0 \\ \lambda-e^{-\lambda t} &\text{se }t>0 \end{cases}$
$F_{X}(t)=\begin{cases} 0 &\text{se }t<0 \\ 1-e^{-\lambda t} &\text{se }t\geq0 \end{cases}$
#### Proprietà
$P[X>s+t|X>s] = P[X>t] \forall t,s\in\mathbb{R}^{+}$
### Distribuzione di Weibull
Uuna variabile aleatoria $X$ è detta distribuita secondo una **Weibull** di parametri $\alpha,\beta\in\mathbb{R}^{+}$ se è assolutamente continua con densità di probabilità
$f_{X}(t)=\begin{cases} 0 &\text{se }t<0 \\ \alpha\beta t^{\beta-1}e^{-\alpha t^{\beta}} &\text{se }t\geq0 \end{cases}$
$F_{X}(t)=\begin{cases} 0 &\text{se }t<0 \\ 1-e^{-\alpha t^{\beta}} &\text{se }t\geq0 \end{cases}$
### Distribuzione Normale (di Gauss)
Una variabile aleatoria $X$ è detta distribuita secondo una **normale** di parametri $\mu\in\mathbb{R},\sigma\in\mathbb{R}^{+}$ se ha densità di probabilità
$f_{X}(x)= \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^{2}}$

$B(n,p)\overset{n\to\infty}\to N(\mu,\sigma)\overset{\lambda\to\infty}\leftarrow Pois(\lambda)$
### Distribuzione $X^{2}$ (chi-quadra)
Siano $X_{1},X_{2},\ldots,X_{n}$ $n$ **variabili aleatorie** con **distribuzione normale** $N(0,1)$ indipendenti tra loro.
Sia $X$ la variabile aleatoria
$X=X_{1}^{2}+X_{2}^{2}+\ldots+X_{n}^{2}$
allora si prova che questa **variabile aleatoria** è distribuita secondo una distribuzione ***chi-quadra***

Diremo che la **variabile aleatoria** $X$ è distribuita secondo una $X^{2}(n)$ con $n$ gradi di libertà se è assolutamente continua con densità di probabilità
$f_{X}(t)=\begin{cases} 0 &\text{se }t<0 \\ \frac{1}{\Gamma\left(\frac{n}{2}\right)} \left(\frac{1}{2}\right)^{\frac{n}{2}}t^{\frac{n}{2}-1}e^{-\frac{1}{2}t} &\text{se }t\geq0 \end{cases}$
con $\Gamma(\alpha) = \int\limits_{0}^{+\infty}e^{-x}x^{\alpha-1}dx$ (***Gamma di Eulero***)

Si prova che $E[X] = n$, $Var[X]=2n$
### Distribuzione t di Student
Siano $Z\simeq N(0,1)$ e $Y=X^{2}(n)$ due **variabili aleatorie** indipendenti.
Definiamo $X= \frac{Z}{sqrt{\frac{Y}{n}}}$ e si prova che $X$ è una **variabile aleatoria** distribuita secondo una ***t di Student*** con $n$ gradi di liberta.

Diremo che la **variabile aleatoria** $X$ è distribuita secondo una t di Student con $n$ gradi di libertà, se è assolutamente continua con densità di probabilità
$f_{X}(t)= \frac{\Gamma\left(\frac{n+1}{2}\right)}{\Gamma\left(\frac{n}{2}\right)} \frac{1}{\sqrt{n\pi}} \left(1+ \frac{t^{2}}{n}\right)^{-\frac{1}{2}(n+1)}$

Si prova che

- $E[X] = 0$ se $n=1$, $Var[X] = \frac{n}{n+1}$ se $n>1$
- Per $n\geq30$ la **t di Student** approssima $N(0,1)$
## Campione casuale
Consideriamo $X_{1},X_{2},\ldots,X_{n}$ una $n$-upla di variabili *indipendenti* ed *indipendentemente distribuite* (**iid**)

Data una **variabile aleatoria** $X$, chiameremo ***campione casuale*** (o più brevemente *campione*) di ampiezza $n$ una $n$-upla di **variabili aleatorie** tra di loro *indipendenti*, ciascuna delle quali *distribuita come la popolazione* $X$.
### Media campionaria
La ***media campionaria*** di un campione casuale di ampiezza $n$  $X_{1},X_{2},\ldots,X_{n}$ è data da
$\bar{X_{n}} = \frac{X_{1}+X_{2}+\ldots+X_{n}}{n} = \frac{1}{n}\sum\limits_{i=1}^{n}X_{i}$
#### Valore atteso e varianza
Se la *popolazione* è dotata di **media di varianza** ($E[X]=m$ e $Var[X]=\nu$), allora, dato un campione **iid** $X_{1},X_{2},\ldots,X_{n}$, si ha
$E[\bar{X_{n}}]=m$,$Var[\bar{X_{n}}] = \frac{1}{n}\nu$

```ad-dem
$$
\displaylines{
E[\bar{X_{n}}] = E\left[\frac{X_{1}+X_{2}+\ldots+X_{n}}{n}\right] = \\
= \frac{1}{n} E[X_{1}+X_{2}+\ldots+X_{n}] \equiv \frac{1}{n}nE[X]=m \\
\\
Var[\bar{X_{n}}] = Var\left[\frac{X_{1}+X_{2}+\ldots+X_{n}}{n}\right] = \\
= \frac{1}{n^{2}} (Var[X_{1}]+Var[X_{2}]+\ldots+Var[X_{n}]) = \\
= \frac{1}{n^{2}} n Var[X] = \frac{\nu}{n}
}
$$
```
#### Distribuzione della media campionaria
Sia $X_{1},X_{2},\ldots,X_{n}$ un campione estratto da una popolazione $X\sim Norm(\mu=m,\sigma^{2}=\nu)$ allora

- detta $\bar{X_{n}}$ la media campionaria, si ha
  $\bar{X_{n}}\sim Norm(\mu=m,\sigma^{2}=\frac{\nu}{n})$
- detta $S_{0}^{2}$ la varianza campionaria(a media nota), si ha
  $S_{0}^{2}\sim \frac{\nu}{n}X^{2}(\nu=n)$
  Invece, a media incognita
  $S_{n}^{2}\sim \frac{\nu}{n-1}X^{2}(\nu=n-1)$
- $\frac{\bar{X_{n}}-m}{\sqrt{\frac{S_{n}^{2}}{n}}}\sim T(\nu=n-1)$
### Momento campionario di ordine $k$
$M_{n}^{(k)}= \frac{X_{1}^{k}+X_{2}^{k}+\ldots+X_{n}^{k}}{n} = \frac{1}{n}\sum\limits_{i=1}^{n}X_{i}^{k}$
### Variazione campionaria
1. Valore atteso noto ($E[X]=m$)
   $S_{0}^{2} = \frac{1}{n}\sum\limits_{i=1}^{n}(x_{i}-m)^{2}$
2. Valore atteso incognito
   $S_{n}^{2} = \frac{1}{n-1}\sum\limits_{i=1}^{n}(x_{i}-\bar X_{n})^{2}$
#### Proposizione
Se è nota la media della popolazione $X$, allora
$S_{0}^{2} = M_{n}^{(2)}-2m\bar{X_{n}}+m^{2}$
Se la media della popolazione è incognita, allora
$S_{n}^{2} = \frac{1}{n-1}(nM_{n}^{(2)}-n\bar{X_{n}^{2}})$
#### Valore atteso
Se la popolazione $X$ è dotata di media e varianza ($E[X]=m,Var[X]=\nu$), allora, dato un campione  $X_{1},X_{2},\ldots,X_{n}$, si ha
$E[S_{0}^{2}]=\nu$; $E[S_{n}^{2}]=\nu$
## Convergenze
### Convergenza di una distribuzione
Si dice che la *successione* di **variabili aleatorie** $\{X_{n}\}$ converge in distribuzione alla **variabile aleatoria** $X$, se
$\lim\limits_{n\to\infty}F_{X_{n}}(x) = F_X(x)$
$X_n\overset{d}\to X$ in simboli
per tutti i valori di $x$ ove $F_{X}(x)$ è continua
### Convergenza in probabilità
Si dice che la successione di **variabili aleatorie** $\{X_{n}\}$ converge in probabilità alla **variabvile aleatoria** $X$ se
$\forall\epsilon>0\;\;\;\;\lim\limits_{n\to\infty}P[|X_{n}-X|<\epsilon] = 1$
$X_{n}\overset{P}\to X$ in simboli
### Convergenza quasi certa
Si dice che la *successione* di **variabili aleatorie** $\{X_{n}\}$ converga quasi certamente alla **variabile aleatoria** $X$, se
$\forall\epsilon>0\;\;\;\;P[\lim\limits_{n\to\infty}|X_{n}-X|<\epsilon] = 1$
$X_{n}\overset{q.c.}\to X$ in simboli
### Convergenza in media quadratica
Si dice che la *successione* di **variabili aleatorie** $\{X_{n}\}$ converga quasi certamente alla **variabile aleatoria** $X$, se
$\lim\limits_{n\to\infty}E[(X_{n}-X)^2] = 0$
$X_{n}\overset{m.q.}\to X$ in simboli
### Proprietà
$(X_{n}\overset{m.q.}\to X \land X_{n}\overset{q.c.}\to X) \implies X_{n}\overset{P}\to X \implies X_n\overset{d}\to X$
### Teorema (Legge debole dei grandi numeri)
Sia $X_{n}$ una *successione* di **variabili aleatorie** **i.i.d.** proveniente da una popolazione $X$ dotata di media($E[X] = m$), allora
$\forall\epsilon>0\;\;\;\;\lim\limits_{n\to\infty}P[|\bar{X_{n}}-m|<\epsilon] = 1$
cioè, la *successione* della **media campionaria** ***converge in probabilità*** ad $m$, il **valore atteso** di tutte le $X_{n}$
### Teorema (Legge forte dei grandi numeri)
Sia $X_{n}$ una *successione* di **variabili aleatorie** **i.i.d.** proveniente da una popolazione $X$ dotata di media($E[X] = m$), allora
$\forall\epsilon>0\;\;\;\;P[\lim\limits_{n\to\infty}|\bar{X_{n}}-m|<\epsilon] = 1$
cioè, la *successione* della **media campionaria** ***converge quasi certamente*** ad $m$, il **valore atteso** di tutte le $X_{n}$
### Teorema centrale del limite
Sia $X_{n}$ una *successione* di **variabili aleatorie** **i.i.d.** proveniente da una popolazione $X$ dotata di media e varianza ($E[X] = m$, $Var[X]=\nu$), allora per ogni $x\in\mathbb{R}$
$\lim\limits_{n\to\infty}P\left[\frac{\bar{X_{n}}-m}{\sqrt{\frac{S_{n}^{2}}{n}}}\leq x\right] = \phi(x)$ (distribuzione normale)
cioè, la *successione* della **media campionaria** ***converge in legge*** ad una $Norm(\mu=0,\sigma^{2}=1)$
$\bar{X_{n}}\sim Norm\left(\mu=m,\sigma^{2}=\frac{\nu}{n}\right)$
### Osservazioni
1. $Bin(n,p)\approx Norm(\mu=np,\sigma^{2}=np)$
   se $n\geq30$, $np\geq5$,$nq\geq5$
2. $\overline{Bin}(n,p)\approx Norm\left(\mu=\frac{n}{p},\sigma^{2}=\frac{n(1-p)}{p^{2}}\right)$
   se $n\geq30$
3. $Poi(\lambda)\approx Norm(\mu=\lambda,\sigma^{2}=\lambda)$
   se $\lambda\geq30$
## ~~To define~~
### Statistica
Si dice ***statistica*** di una **variabile aleatoria** $t$, funzione nota delle **variabili aleatorie** $X_{1},X_{2},\ldots,X_{n}$
$t(X_{1},X_{2},\ldots,X_{n}) = T(X)$
### Stimatore
Data una popolazione dipendente da un parametro $\theta$, e un campèione casuale $X_{1},X_{2},\ldots,X_{n}$, si dice ***stimatore*** una **statistica** $t$ che non dipende da $\theta$ e che seve per *stimare* $\theta$
### Correttezza, Correttezza asintotica
Uno **stimatore** si dice ***corretto***( o non distorto) se il suo valore atteso coincide con la quantità da stimare
$E[t_{n}] = \theta$
Si dirà asintoticamente corretto se
$E[t_{n}]\overset{n\to\infty}\to\theta$
### Consistenza
Uno stimatore si dice consistente in **media quadratica** se
$E[(t_{n}-\theta)^{2}]\overset{n\to\infty}\to0$
Si dirà consistente in **probabilità** se
$P[|T_{n}-\theta|<\epsilon]\overset{n\to\infty}\to0\;\;\;\;\forall\epsilon>0$
### Asintotica normalità
$\frac{t_{n}-E[t_{n}]}{\sqrt{Var[t_{n}]}}\overset{n\to\infty}\sim Norm(0,1)$
### Metodo della massima verosomiglianza
$\mathscr{L}(x_{1},x_{2},\ldots,x_{n},\theta) = \rho_X(x_{1},\theta)\cdot\rho_X(x_{2},\theta)\cdot\ldots\cdot\rho_X(x_{n},\theta)=\prod\limits_{i=1}^{n}\rho_{X}(x_{i},\theta)$
## Verifica di ipotesi
Struttura di un test d'ipotesi
### Ipotesi
L'ipotesi di partenza è detta **ipotesi nulla** ed è indicata con $H_{0}$

ad-eg
$H_{0}: \mu=S$ **ipotesi semplice**
$H_{0}: \mu\leq \text{ opp.} H_{0}: \mu\geq S$ **ipotesi composta**

il contrario dell'ipotesi nulla è l'**ipotesi alternativa** e verrà indicata con $H_{1}$ o $H_{a}$.

Si tratta di ciò che dovremmo accettare per vero nel caso in cui rigettassimo l'**ipotesi nulla**
### Statistica test ($U$)
Si tratta di una variabile aleatoria della quale almeno approssimativamente possiamo specificare la distribuzione Indicheremo con $u$ il valore di $U$
### Regione critica
Si rifiuta $H_{0}$ se $u\in C$
Non si rifiuta $H_{0}$ se $u\not\in C$
### Errori possibili
Gli errori che si possono commettere sono i seguenti:

- non si sbaglia
  $H_{0}$ è vero se non si rifiuta
  $H_{0}$ è falso se si rifiuta
- Errore del I tipo
  $H_{0}$ è vero se si rifiuta
- Errore del II tipo
  $H_{0}$ è falso se non si rifiuta
### Livello di significatività ($\alpha$)
Livello di soglia $\alpha$ tale che la probabilità di commettere l'errore del I tipo sia non superiore ad $\alpha$.
Solitamente $\alpha$ = 10%, 5%, 1%
### Funzione potenza
Se il test è un test *parametrico*, cioè riguarda un parametro, la probabilità di rifiutare l'*ipotesi* dipende dal valore incognito del parametro ($\theta$)

Questa probabilità è detta **funzione potenza** del test
$\pi(\theta) = P_{\theta}[\text{rifiutare }H_{0}]$ opp.
$\pi(\theta) = P_{\theta}[u\in C]$
### $p$-value
Ci si può chiedere a quale livello di **signifivatività** corrisponderebbe una *regione critica* la cui frontiera fosse costituita proprio da $u$, cioè per quale livello il valore osservato di $u$ valica la frontiera di $C$. Questo valore prende il nome di **$p$-value**
$p\text{-value} = \sup{\{\alpha:u\not\in C\}} = \inf{\{\alpha:u\in C\}}$

Dato un certo test, rifiuteremo $H_{0}$ per tutti i livelli maggiori del **$p$-value** e non lo rifiuteremo per tutti i livelli inferiori
### Test riguardanti una sola popolazione
#### Test riguardanti la media di una Normale
Supponiamo $X\sim Norm(\mu,\sigma^{2})$ e sia $n$ il numero di osservazioni di tale variabile aleatoria

Tipologia di ipotesi che si possono dare su $\mu$:
Tipo I $\begin{cases} H_{0}: \mu=\mu_{0} \\ H_{1}: \mu\neq\mu_{0} \end{cases}$
Tipo II $\begin{cases} H_{0}: \mu=\mu_{0} &\text{ o }\mu\leq\mu_{0} \\ H_{1}: \mu>\mu_{0} \end{cases}$
Tipo III $\begin{cases} H_{0}: \mu=\mu_{0} &\text{ o }\mu\geq\mu_{0} \\ H_{1}: \mu<\mu_{0} \end{cases}$

La **statistica test** $U$ utilizzata è diversa se $\sigma^{2}$ è noto o incognito. Nei due casi variano anche la regione critica ed il **$p$-value**

Caso 1: $\sigma^{2}$ noto, $z$-test
$\bar{X_{n}}\sim Norm(\mu,\sigma^{2}=\nu)$
$\frac{\bar{X_{n}}-\mu}{\sqrt{\frac{\nu}{n}}}\sim Norm(0,1)$

Scegliamo come statistica la standardizzazione che sarebbe corretta eseguire, se fosse vera $H_{0}$, ossia scegliamo per $\mu$ il valore $\mu_{0}$
$U=\frac{\bar{X_{n}}-\mu_{0}}{\sqrt{\frac{\nu}{n}}}$
Scriveremo
$U=\frac{\bar{X_{n}}-\mu_{0}}{\sqrt{\frac{\nu}{n}}} \overset{H_{0}}\sim Norm(0,1)$

1. Tipo I, dobbiamo decidere tra
   $H_{0}:\mu=\mu_{0}$ e $H_{1}:\mu\neq\mu_{0}$
   prependeremo per $H_{0}$ se il valore osservato $u$ di $U$ sarà "vicino a 0", mentre prependeremo per $H_{1}$ se $u$ si trova in una delle due code della distribuzione
   ![[Test media normale - Tipo I.jpg]]
   Si deve stabilire il valore di $\bar{z}$ in corrispondenza del quale si inizia a rifiutare $H_{0}$; poichè il nostro test ha livello di significatività $\alpha$, vogliamo che
   $\alpha = \max P[\text{Errore del I Tipo}] = \max P[|u|>\bar{z}|H_{0}\text{ vero}]$
   cioè $\alpha$ deve essere il valore massimo per cui $u$, che nell'ipotesi è una normale standard, finisce in una delle due code.
   $\begin{cases} U\sim Norm(0,1) \\ P[|u|>\bar{z}>\alpha] \end{cases}\implies\bar{z}=z_{1-\frac{\alpha}{2}}$
   quindi rifiuteremo $H_{0}$ se $|u|>z_{1-\frac{\alpha}{2}}$
2. Tipo II, dobbiamo decidere tra
   $H_{0}:\mu=\mu_{0}$ e $H_{1}:\mu>\mu_{0}$
   prependeremo per $H_{0}$ se il valore osservato $u$ di $U$ sarà "vicino a 0", mentre il fatto di aver utilizzato nella creazione della statistica test un valore "troppo piccolo" per la media ci farà prependere per $H_{1}$, se $u$ si trova nella coda a destra
   ![[Test media normale - Tipo II.jpg]]
   con conti simili ai precedenti, si trova $\bar{z}=z_{1-\alpha}$ e per tanto rifiuteremo $H_{0}$ se $u>z_{1-\alpha}$
3. Tipo III, dobbiamo decidere tra
   $H_{0}:\mu=\mu_{0}$ e $H_{1}:\mu<\mu_{0}$
   i conti si svolgono in maniera esattamente speculare al caso precedente e rifiuteremo $H_{0}$ se $u<-z_{1-\alpha}$ che equivale a $-u>z_{1-\alpha}$

Ricapitolando

| Tipo | Rifiuto di $H_{0}$ se           |
| ---- | ------------------------------- |
| I    | $abs(u)>z_{1-\frac{\alpha}{2}}$ |
| II   | $u>z_{1-\alpha}$                |
| III  | $u<-z_{1-\alpha}$               |

---

Caso 2: $\sigma^{2}$ incognito, il $t$-test
$U=\frac{\bar{X_{n}}-\mu_{0}}{\sqrt{\frac{S_{n}^{2}}{n}}} \overset{H_{0}}\sim T(\nu=n-1)$

| Tipo | Rifiuto di $H_{0}$ se           |
| ---- | ------------------------------- |
| I    | $abs(u)>t_{1-\frac{\alpha}{2}}$ |
| II   | $u>t_{1-\alpha}$                |
| III  | $u<-t_{1-\alpha}$               |

---
#### Test riguardanti la varianza di una Normale
Supponiamo $X\sim Norm(\mu,\sigma^{2})$ e sia $n$ il numero di osservazioni di tale variabile aleatoria

Tipologia di ipotesi che si possono dare su $\sigma^{2}$:
Tipo I $\begin{cases} H_{0}: \sigma^{2}=\sigma^{2}_{0} \\ H_{1}: \sigma^{2}\neq\sigma^{2}_{0} \end{cases}$
Tipo II $\begin{cases} H_{0}: \sigma^{2}=\sigma^{2}_{0} &\text{ o }\sigma^{2}\leq\sigma^{2}_{0} \\ H_{1}: \sigma^{2}>\sigma^{2}_{0} \end{cases}$
Tipo III $\begin{cases} H_{0}: \sigma^{2}=\sigma^{2}_{0} &\text{ o }\sigma^{2}\geq\sigma^{2}_{0} \\ H_{1}: \sigma^{2}<\sigma^{2}_{0} \end{cases}$

Caso 1: $\mu$ noto
$S_{0}^{2} = \frac{1}{n}\sum\limits_{i=1}^{n}(x_{i}-m)^{2}$
Sappiamo che
$S_{0}^{2}\sim \frac{\sigma^{2}}{n}X^{2}(\nu=n) \iff \frac{n}{\sigma^{2}}S_{0}^{2}\sim X^{2}(\nu=n)$
$U= \frac{n}{\sigma^{2}}S_{0}^{2}\overset{H_{0}}\sim X^{2}(\nu=n)$

1. Tipo I, dobbiamo decidere tra
   $H_{0}:\sigma^{2}=\sigma^{2}_{0}$ e $H_{1}:\sigma^{2}\neq\sigma^{2}_{0}$
   prependeremo per $H_{0}$ se il valore osservato $u$ di $U$ si trova in corrispondenza della regione dove la densità della $X^{2}$ è maggiore, mentre prependeremo per $H_{1}$ se $u$ si troverà in una delle due code
   ![[Test varianza normale - Tipo I.jpg]]
   $\bar{c_{1}}=X^{2}_{\frac{\sigma}{2};n}$
   $\bar{c_{2}}=X^{2}_{1-\frac{\sigma}{2};n}$
   rifiuteremo quindi $H_{0}$ in uno dei due casi
   $u<X^{2}_{\frac{\sigma}{2}}$ oppure $u>X^{2}_{1-\frac{\sigma}{2}}$
2. Tipo II, dobbiamo decidere tra
   $H_{0}:\sigma^{2}=\sigma^{2}_{0}$ e $H_{1}:\sigma^{2}>\sigma^{2}_{0}$
   rifiuteremo $H_{0}$ se $u>X^{2}_{1-\alpha}$
3. Tipo III, dobbiamo decidere tra
   $H_{0}:\sigma^{2}=\sigma^{2}_{0}$ e $H_{1}:\sigma^{2}<\sigma^{2}_{0}$
   rifiuteremo $H_{0}$ se $u<X^{2}_{\alpha}$

Ricapitolando

| Tipo | Rifiuto se                                                         |
| ---- | ------------------------------------------------------------------ |
| I    | $u<X^{2}_{\frac{\alpha}{2}}$ oppure $u>X^{2}_{1-\frac{\alpha}{2}}$ |
| II   | $u>X^{2}_{1-\alpha}$                                               |
| III  | $u<X^{2}_{\alpha}$                                                 |

---

Caso 2: $\mu$ incognito
Sappiamo che
$U= \frac{(n-1)}{\sigma^{2}}S_{n}^{2}\overset{H_{0}}\sim X^{2}(\nu=n-1)$

| Tipo | Rifiuto se                                                         |
| ---- | ------------------------------------------------------------------ |
| I    | $u<X^{2}_{\frac{\alpha}{2}}$ oppure $u>X^{2}_{1-\frac{\alpha}{2}}$ |
| II   | $u>X^{2}_{1-\alpha}$                                               |
| III  | $u<X^{2}_{\alpha}$                                                 |

---
### Test parametrici di confronto fra due popolazioni
Supponiamo di avere due popolazioni
$X_{1},X_{2},\ldots,X_{n}$
$Y_{1},Y_{2},\ldots,Y_{m}$
con $n,m\in\mathbb{N}$
$X\sim Norm(\mu=\mu_{X},\sigma^{2}=\sigma_{X}^{2})$
$Y\sim Norm(\mu=\mu_{Y},\sigma^{2}=\sigma_{Y}^{2})$

Test

1. Tipo I: $\begin{cases} H_{0}: \mu_{X} = \mu_{Y} \\ H_{1}: \mu_{X}\neq\mu_{Y} \end{cases}$
2. Tipo II: $\begin{cases} H_{0}: \mu_{X} = \mu_{Y}  &\text{ opp. }\mu_{X}\leq \mu_{Y}\\ H_{1}: \mu_{X}>\mu_{Y} \end{cases}$
3. Tipo III: $\begin{cases} H_{0}: \mu_{X} = \mu_{Y}  &\text{ opp. }\mu_{X}\geq \mu_{Y}\\ H_{1}: \mu_{X}<\mu_{Y} \end{cases}$

Si osserva che
$\bar{X_{n}}\sim Norm\left(\mu=\mu_{X},\sigma^{2}=\frac{\sigma_{X}^{2}}{n}\right)$
$\bar{Y_{m}}\sim Norm\left(\mu=\mu_{Y},\sigma^{2}=\frac{\sigma_{Y}^{2}}{m}\right)$
quindi
$\bar{X_{n}}-\bar{Y_{m}}\sim Norm\left(\mu=\mu_{X}-\mu_{Y}, \sigma^{2}= \frac{\sigma_{X}^{2}}{n}+\frac{\sigma_{Y}^{2}}{m}\right)$

Caso 1: Varianza nota
$\frac{(\bar{X_{n}}-\bar{Y_{m}})-(\mu_{X}-\mu_{Y})}{\sqrt{\frac{\sigma_{X}^{2}}{n}+\frac{\sigma_{Y}^{2}}{m}}}\sim Norm(0,1)$
Allora
$U=\frac{(\bar{X_{n}}-\bar{Y_{m}})-(\mu_{X}-\mu_{Y})}{\sqrt{\frac{\sigma_{X}^{2}}{n}+\frac{\sigma_{Y}^{2}}{m}}}\overset{H_{0}}\sim Norm(0,1)$

| Tipo | Rifiuto se                      |
| ---- | ------------------------------- |
| I    | $abs(u)>z_{1-\frac{\alpha}{2}}$ |
| II   | $u>z_{1-\alpha}$                |
| III  | $u<-z_{1-\alpha}$               |

---

Caso 2: Varianza incognita, ufuali
$\sigma_{X}^{2} = \sigma_{Y}^{2} = \nu$
$S_{X}^{2}=\frac{1}{n-1} \sum\limits_{i=1}^{n}(X_{i}-\bar{X_{n}})^{2}$
$S_{Y}^{2}=\frac{1}{m-1} \sum\limits_{i=1}^{m}(Y_{i}-\bar{Y_{m}})^{2}$
$\hat\nu=S_{p}^{2}=\frac{(n-1)S_{X}^{2}+(m-1)S_{Y}^{2}}{n+m-2}$

$\hat\nu$ prende il nome di **varianza combinata**

La **statistica test** è data da
$U=\frac{\bar{X_{n}}-\bar{Y_{m}}}{\sqrt{S_{p}^{2}(\frac{1}{n}+\frac{1}{m})}}\overset{H_{0}}\sim T(\nu=n+m-2)$

| Tipo | Rifiuto se                  |
| ---- | --------------------------- |
| I    | $abs(u)>t_{1-\alpha;n+m-2}$ |
| II   | $u>t_{1-\alpha;n+m-2}$      |
| III  | $u<-t_{1-\alpha;n+m-2}$     |

---

Caso 3: Varianza incognita, non uguali
$U=\frac{\bar{X_{n}}-\bar{Y_{m}}}{\sqrt{\frac{S_{X}^{2}}{n}+\frac{S_{Y}^{2}}{m}}}\overset{H_{0}}\sim T(\nu=\nu^{*})$
$\nu^{*}=\left\lfloor\left(\frac{\left(\frac{S_{X}}{n} + \frac{S_{Y}}{m}\right)^{2}}{\frac{1}{n-1} \left(\frac{S_{X}^{2}}{n}\right)^{2}+ \frac{1}{m-1} \left(\frac{S_{Y}^{2}}{m}\right)^{2}}\right)\right\rfloor$
$*$ Confronto di due Normali, a campioni accoppiati
Abbiamo un campione di ampezza $n$, cioè formati da $n$ coppie di osservazioni
$(X_{1},Y_{1}),(X_{2},Y_{2}),\ldots,(X_{n},Y_{n})$
$X$ e $Y$ sono normali e la loro differenza ($W=X-Y$) sarà anch'essa normalmente distribuita
$W\sim Norm(\mu_{W},\sigma_{W}^{2})$
con $\mu_{W} = \mu_{X}-\mu_{Y}$ e $\sigma_{W}^{2}$ incognita

Tipo I $\begin{cases} H_{0}: \mu_{W}=0 \\ H_{1}: \mu_{W}\neq0 \end{cases}$
Tipo II $\begin{cases} H_{0}: \mu_{W}=0 &\text{ o }\mu_{W}\leq0 \\ H_{1}: \mu_{W}>0 \end{cases}$
Tipo III $\begin{cases} H_{0}: \mu_{W}=0 &\text{ o }\mu_{W}\geq0 \\ H_{1}: \mu_{W}<0 \end{cases}$

$S_{W}^{2}=\frac{1}{n-1}\sum\limits_{i=1}^{n}(W_{i}-\bar{W_{n}})$
$U=\frac{\bar{W_{n}}}{\sqrt{\frac{S_{W}^{2}}{n}}}\overset{H_{0}}\sim T(\nu=n-1)$

| Tipo                   | Rifiuto se                          |
| ---------------------- | ----------------------------------- |
| I                      | $abs(u)>z_{1-\frac{\alpha}{2};n-1}$ |
| II                     | $u>z_{1-\alpha;n-1}$                |
| III                    | $u<-z_{1-\alpha;n-1}$               |
| ## Regressione lineare |                                     |
