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
   $P[E]\in\mathscr{R}$; $0\leq P[E]\leq1$
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
$P[E_h|F]=\frac{P[E|E_h]\cdot P[E_h]}{\sum\limits_{i}{P[F|E-i]\cdot P[E_i]}}$

```ad-dem
$P[E_h\cap F]=P[F|E_h]P[E_h]=P[E_h|F]P[F]$
$P[E_h|F]=\frac{P[F|E_h]\cdot P[E_h]}{P[F]}=$
$=\frac{P[E|E_h]\cdot P[E_h]}{\sum\limits_{i}{P[F|E-i]\cdot P[E_i]}}$
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
Si dice permutazione di n oggetti distinti ogni allineamento deli oggetti stessi, due permutazioni sono distinte quando differiscono per il posto occupato da almeno un oggetto.
Indicheremo con P_n il numero di permutazioni

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
$F_x(t)=P[X\leq t]=P[A_t]$
$F_x(t):\mathbb{R}\to[0,1]$
```
### Proprietà
1. $F_x$ è monotona non decrescente, cioè
   $F_x(t_1)\leq F_x(t_2)\impliedby t_1\leq t_2$
   $A_{t_1}\subseteq A_{t_2}\implies P[A_{t_1}]\leq P[A_{t_2}]$
2. $\lim\limits_{t\to-\infty}F_x(t)=0$ $\lim\limits_{t\to+\infty}F_x(t)=1$
3. Per ogni valore $x_0\in\mathbb{R}$
   $P[X=x_0]=\lim\limits_{t\to x_0^+}F_x(t)-\lim\limits_{t\to x_0^-}F_x(t)$
4. La funzione di ripartizione $F_x$ è continua e destra, ossia:
   per ogni valore $x_0\in\mathbb{R}$
   $F_x[x_0](=P[X\leq x_0])=\lim\limits_{t\to x_0^+}F_x(t)$

```ad-def
title: Variabile aleatoria discreta
Se la variabile aleatoria X può assumere solo un numero finito (o al più numerabile) di valori, la relativa $F_{x}$ sarà costante a tratti
e la variabile viene detta discreta
Se X può assumere i valori di un internvallo $I\subset\mathbb{R}$, allora F_x è generalmente continua e la variabile è detta continua
```
### Densità di variabili aleatorie
#### Caso discreto
Una variabile aleatoria $X$ discreta può assumeresolo alcuni valori $x_i$ ($i=1,\ldots,n$ / $i=1,\ldots$)
$P[X=x_i]\rightarrow\sum\limits_i{P[X=x_i]}=1$

```ad-def
title: Densità di probabilità
La funzione $P_x:\mathbb{R}\to[0,1]$ definita dalla relazione
$P_X(x)=P[X=x]=\begin{cases}P[X=x_i]&x=x_1 &\text{per un certo i}\\0 &x\neq x_i &\forall i\end{cases}$
```

$A=\{x_1|a<x_{i}\leq b\}$
$P[a<X\leq b]=\sum\limits_{i\in A} P[X=x_i]=\sum\limits_{i\in A} P_X(x_i)$
assioma:
$P[a<X\leq b]=P[a<X<b]+P[X=b]$
$P[a<X\leq b]\neq P[a<X<b]$

$F_x(t)OP[X\leq t]=\sum\limits_{x_{i}<t}P_{X}(x_{i})$
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
Sia $X$ una variabile aleatoria, discreta o continua, si chiama moda di X il valore, se esiste, per cui è massima la densità
```

```ad-def
title: Quantile
Dato $\alpha\in(0,1)$, si dice quantile di ordine $\alpha$ della variabile aleatoria $X$ il più piccolo numero $x_\alpha$ tale che
$P[X<x_{\alpha}]\leq \alpha \leq P[X\leq x_{\alpha}]$
```

```ad-def
title: Mediana
Si dice mediana della vbariabile aleatoria $X$ il quantile di ordine $0.5$($x_{0.5}$)
```

```ad-def
title: Varianza
Data una variabile aleatoria $X$, il cui valore atteso vale $E[X]=\mu$ si chiama varianza di $X$, e si indica con $Var[X]$, il seguente valore atteso
$Var[X]=E[(X-\mu)^2]$
```
#### Proprietà
$Var[X]=E[X^2]-\mu^2$

```ad-dem
$Var[X]=E[(x-\mu)^2]=$
$=E[(x^2+\mu^2-2X\mu)]=$
$=E[x^2]+E[\mu^2]-E[2X\mu]=$
$=E[x^2]+\mu^{2-2\mu}E[X]=$
$=E[x^2]+\mu^2-2\mu^2=E[X^2]-\mu^2$
```
### Disuguaglianza di Markov
Sia $X$ una variabile aleatoria e $g:\mathbb{R}\to\mathbb{R}$ tale che $g(x)\geq0\quad\forall x\in\mathbb{R}$
Allora, se esiste $E[g(X)]$, si ha:
$P[g(X)\geq N]\leq \frac{E[g(x)]}{N}\quad\forall N>0$

```ad-dem
$E[x]=\int\limits_{-\infty}^{+\infty}xf_X(x)dx$
$E[g(x)]\int\limits_{-\infty}^{+\infty}g(x)f_X(x)dx$
$E[g(x)]\int\limits_{-\infty}^{+\infty}g(x)f_X(x)dx\geq$
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

```ad-def Funzione generatrive dei momenti
$\mu_{X}(t)=E[e^{tx}]$
```
#### Proprietà
- $\mu_{1}=[\frac{d}{dt}\mu_{X}(t)]_{t=0}$
  ```ad-dem
  $\mu_1=\int\limits_{-\infty}^{+\infty}xf_X(x)dx$
  $\mu_{X}(t)=\int\limits_{-\infty}^{+\infty}e^{tx}f_{X}(x)dx$
  $\frac{d}{dt}\mu_{X}(t)=\int\limits_{-\infty}^{+\infty}xe^{tx}f_{X}(x)dx$
  $[\frac{d}{dt}\mu_{X}(t)]_{t=0}=\int\limits_{-\infty}^{+\infty}xf_X(x)dx=\mu_1$
  ```
- $\frac{d^{k}}{dt^{k}}(e^{tx})=x^{k}e^{tx}$
- $\mu_{k}=[\frac{d^{k}}{dt^{k}}m_x(t)]_{t=0}$
- Siano $X$ e $Y$ due variabili aleatorie, se
  $\mu_{X}(t)=m_{y}(t)\quad\forall t\in[-t_{0},t_{0}]$
  allora $X$ e $Y$ hanno la medesima densità
- Se $X$ possiede la funzione generatrice dei momenti e $Y=aX+b$, allora esiste anche $m_y(t)$ e
  $m_{y}(t)=e^{tb}m_x(at)$
## Schemi e distribuzioni
### Schema di Bernoulli
Consideriamo un esperimento che si può concludere solo in due modi chiamati convenzionalmente successo ed insuccesso; un esperimento di questo tipo è detto di ***Bernoulli***

Sia $p$ la probabilità che si verifichi il successo e $q$ quella dell'insuccesso $q = 1-p$

Una sequenza di **prove di Bernanilli**, tra di loro indipendenti, per le quali la probabilità del successo si mantiene invariata è detto ***schema di Bernoulli***
### Distribuzione di Bernoulli
Una variabile aleatoria $X$ che vale $1$ se la **prova di Bernoulli** si è conclusa con il successo e $0$ altrimenti è detta **variabile aleatoria di Bernoulli** di parametro $p$ in simboli $X\sim Ber(p)$
#### Densità
$P[X=1] = p$; $P[X=0] = q$

```ad-dem
$P[X=n] = p^{n}q^{1-n}$
```
#### Momenti
```ad-def
$\mu_{X}(t) = E[e^{Xt}]$; $E[X] = \frac{d}{dt}m_X(t)|_{t=0}$
```

$\mu_{X}(t) = pe^{t}+q$; $E[X] = 1$; $Var[X] = pq$

```ad-dem
$E[X] = pe^{t}+q|_{t=0} = p+q = 1$
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
$m_{X(t)}= \sum\limits_{k=0}{n}e^{tk}\binom{n}{k}p^{k}q^{n-k} = \sum\limits_{k=0}{n}\binom{n}{k}(pe^{t})^{k}q^{n-k} = (pe^{t}+q)^{n}$
$E[X] = \frac{d}{dt}m_X(t)|_{t=0} = n(pe^{t}+q)^{n-1}pe^{t}|_{t=0} = np$
$E[X^{2}] = \frac{d^{2}}{dt^{2}}\mu_{X}(t)|_{t=0} = np[(n-1)(pe^{t}+q)^{n-2}pe^{2t}+(pe^{t}+q)^{n-1}e^{t}]|_{t=0} = np[(n-1)p+1] = np[np-p+1] = n^{2}p^{2}-np^{2}+np$
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
$m_{X(t)}= \sum\limits_{k=1}{\infty}e^{tk}q^{k-1}p = p\sum\limits_{k=1}{\infty}e^{tk}q^{k-1} = pe^{t}\sum\limits_{k=1}{\infty}e^{t(k-1)}q^{k-1} = pe^{t}\sum\limits_{k=1}{\infty}(qe^{t})^{k-1} = pe^{t}\sum\limits_{k=0}{\infty}(qe^{t})^{k} = \frac{pe^{t}}{1-qe^{t}}$
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

- Densità congiunta (caso discre)