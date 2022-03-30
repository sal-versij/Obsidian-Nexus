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

!def Disposizioni
Si dice disposizione semplice di n oggetti di classe m ogni allineamento di m oggetti scelti fra gli n
!th
$D_{n,k}=\frac{n!}{(n-k)!}$
th!
Si dice disposizione con ripetizione di n oggetti di classe m ogni allineamento di m oggetti scelti fra gli n con la convenzione che ogni oggetto può essere ripetuto una o più volte
$D^{*}_{n,k}=n^k$
def!

!def Combinazioni
Si dice combinazione di n oggetti di classe k, ogni raggruppamento di k oggetti comunque scelti tra gli n
!th
$C_{n,k}=\binom{n}{k}$
th!
Si dice combinazione con ripetizione di n oggetti di classe k, ogni raggruppamento di k oggetti comunque scelti tra gli n con la convenzione che ogni oggetto può essere ripetuto più volte
!th
$C^{*}_{n,k}=\binom{n+k-1}{k}$
th!
def!

Variabili aleatorie
consideriamo lo spazio di probabilità $(\Omega,\mathscr{F},P)$
$X:\Omega\to\mathbb{R}\;\;\;\;\;\;X(\omega)=x\;\;\;\;x\in\mathbb{R}$
$\Omega=\{\omega_1,\omega_2,\ldots,\omega_n\}$
!def
Dato uno spazio di probabilità $(\Omega,\mathscr{F},P)$ si dice variabile aleatoria una corrispondenza tra gli evlementi di \Omega e i numeri (reali), tale corrispondenza deve soddisfare la condizione
$A_t=\{\omega|X(\omega)\leq t\}\in\mathscr{F}\;\;\;\;\forall t\in\mathbb{R}$
def!

&Egrave; detto supporto l'insieme dei valori che la variabile aleatoria può assumere
!def Funzioni di ripartizione
Data la variabile aleatoria $X$, è detta funzione di rpartizione di $X$ la funzione
$F_x(t)=P[X\leq t]=P[A_t]$
$F_x(t):\mathbb{R}\to[0,1]$
def!

Proprietà
1. F_x è monotona non decrescente, cioè
   $F_x(t_1)\leq F_x(t_2)\impliedby t_1\leq t_2$
   $A_{t_1}\subseteq A_{t_2}\implies P[A_{t_1}]\leq P[A_{t_2}]$
2. $\lim\limits_{t\to-\infty}F_x(t)=0$ $\lim\limits_{t\to+\infty}F_x(t)=1$
3. Per ogni valore $x_0\in\mathbb{R}$
   $P[X=x_0]=\lim\limits_{t\to x_0^+}F_x(t)-\lim\limits_{t\to x_0^-}F_x(t)$
4. La funzione di ripartizione $F_x$ è continua e destra, ossia:
   per ogni valore $x_0\in\mathbb{R}$
   $F_x[x_0](=P[X\leq x_0])=\lim\limits_{t\to x_0^+}F_x(t)$

!def
Se la variabile aleatoria X può assumere solo un numero finito( o al più numerabile) di valori, la relativa F_x sarà costante a tratti
e la variabile viene detta descreta
Se X può assumere i valori di un internvallo $I\subset\mathbb{R}$, allora F_x è generalmente continua e la variabile è detta continua
def!

### Densità di variabili aleatorie
#### Caso discreto
Una variabile aleatoria $X$ discreta può assumeresolo alcuni valori $x_i$ ($i=1,\ldots,n$ / $i=1,\ldots$)
$P[X=x_i]\rightarrow\sum\limits_i{P[X=x_i]}=1$
!def Densità di probabilità
La funzione $P_x:\mathbb{R}\to[0,1]$ definita dalla relazione
$P_X(x)=P[X=x]=\begin{cases}P[X=x_i]&x=x_1 &\text{per un certo i}\\0 &x\neq x_i &\forall i\end{cases}$
def!

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
!dem
$I_a=(-\infty,a)$
$I_b=(-\infty,b)$
$I_{ab}=[a,b]$
$P[X\in I_b]=P[I_b]=P[I_{a}\cup I_{ab}]=P[I_{a}] + P[I_{ab}]$
$P[I_{a}\cup I_{ab}]=P[I_{b}]-P[I_{a}]=P[X\leq b]-P[X\leq a]=F_{X}(b)-F_{X}(a)=\int\limits_{-\infty}^{b}f_X(x)dx-\int\limits_{-\infty}^{a}f_X(x)dx=\int\limits_{a}^{b}f_X(x)dx$
dem!

!def
Sia $X$ una variabile aleatoria continua, se esiste una funzione $f_X$ tale che $\forall a,b\in\mathbb{R}$
$P[a<X\leq b]=\int\limits_{a}^{b}f_X(x)dx$
allora $f_X$ è detta funzione densità di probabilità
def!

osservazioni:
1. $f_{X}(x)=0$ se $x\not\in I\subseteq\mathbb{R}$ dove $I$ è il supporto di $X$
2. $P[a<X\leq b]=P[a<X<b]$
Proprietà:
Se $f_X$ è la funzione densità di una variabile aleatoria continua allora
1. $f_{X}(x)\geq0\quad\forall x\in\mathbb{R}$ e $f(x)>0$ se $x\in I$
2. $\int\limits_{-\infty}^{+\infty}f_{X}(x)dx=1$

!th
Sia $X$ una variabile aleatoria continua e sia $Y=g(X)$
Se $g$ è una funzione invertibile nel supporto $I$ di $X$ e $h$ è la sua inversa, allora
$f_Y(y)=f_X(h(y))|h'(y)|$
!dem
$\int\limits_{a}^{b}f_X(x)dx=\int\limits_{g(a)}^{g(b)}f_{X}(h(y))|\frac{dx}{dy}|dy=\int\limits_{g(a)}^{g(b)}f_{X}(h(y))|h'(y)|dy$
dem!
th!

!def Valore Atteso
Data una variabile aleatoria $X$, dotata di funzione di ripartizione, il suo valore atteso (valore medio o speranza matematica), se esiste, è data da
$E[X]=\int\limits_{0}^{+\infty}[1-F_X(t)]dt-\int\limits_{-\infty}^{0}F_{X}(t)dt$
si dimostra che
- caso discreto: $E[X]=\sum\limits_{i}x_{i}P[X=x_{i}]$
- caso continuo: $E[X]=\int\limits_{-\infty}^{+\infty}xf_X(x)$
def!

!def Moda
Sia $X$ una variabile aleatoria, discreta o continua, si chiama moda di X il valore, se esiste, per cui è massima la densità
def!

!def Quantile
Dato $\alpha\in(0,1)$, si dice quantile di ordine $\alpha$ della variabile aleatoria $X$ il più piccolo numero $x_\alpha$ tale che
$P[X<x_{\alpha}]\leq \alpha \leq P[X\leq x_{\alpha}]$
def!

!def Mediana
Si dice mediana della vbariabile aleatoria $X$ il quantile di ordine $0.5$($x_{0.5}$)
def!

!def Varianza
Data una variabile aleatoria $X$, il cui valore atteso vale $E[X]=\mu$ si chiama varianza di $X$, e si indica con $Var[X]$, il seguente valore atteso
$Var[X]=E[(X-\mu)^2]$
def!

Proprietà:
$Var[X]=E[X^2]-\mu^2$
!dem
$Var[X]=E[(x-\mu)^2]=$
$=E[(x^2+\mu^2-2X\mu)]=$
$=E[x^2]+E[\mu^2]-E[2X\mu]=$
$=E[x^2]+\mu^{2-2\mu}E[X]=$
$=E[x^2]+\mu^2-2\mu^2=E[X^2]-\mu^2$
dem!

!th Disuguaglianza di Markov
Sia $X$ una variabile aleatoria e $g:\mathbb{R}\to\mathbb{R}$ tale che $g(x)\geq0\quad\forall x\in\mathbb{R}$
Allora, se esiste $E[g(X)]$, si h
th!