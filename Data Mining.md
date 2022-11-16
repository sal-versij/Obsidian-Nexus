# Data Mining
## Calcolo Probabilità
1. Concetti di base
   - Eventi
   - Variabili aleatorie 
   - Probabilità ($R(X)$. $P(X=x)$)
   - Distribuzione di probabilità ($P$)
   - Densità di probabilità ($F$)
   - Probabilità:
     - congiunta ($P(X,Y)$)
     - condizionata ($P(X=x|Y=y)=\frac{P(X=x,Y=y)}{P(Y=y)}$)
     - marginale ($P(X=x)=\sum\limits_{y\in R(Y)}P(X=x,Y=y)$)
2. Statistiche di una distribuzione
   - Media ($\mathbb{E}[X]=\mu_{X}=\sum\limits_{x\in R(X)}xP(X=x)$)
   - Varianza ($\mathbb{E}[(X-\mu_{X})^{2}]=\sigma_{X}^{2}=\sum\limits_{x\in R(X)}(x-\mu_{X})^{2}P(X=x)$)
   - Entropia ($H(P(X))=-\sum\limits_{x\in R(X)}P(X=x)\log P(X=x)$)
     - Entropia relativa ($H(P||Q)=\sum\limits_{x\in R(X)}P(X=x)\log\frac{P(X=x)}{Q(X=x)}$)
     - Divergenza ($J(P||Q) = H(P||Q) + H(Q||P)$)
   - Covarianza ($\sigma_{X,Y}=\mathbb{E}[(X-\mu_{X})(Y-\mu_{Y})]$)
     - Matrice di covarianza ($\Sigma$)
   - Correlazione
     - di Pearson ($[-1,1]\ni\rho_{X,Y}=\frac{\sigma_{X,Y}}{\sigma_{X}\sigma_{Y}}$)
       - Matrice di correlazione ($P$)
     - di Spearman ($\rho_{X,Y}=\frac{\sigma_{R_{X},R_{Y}}}{\sigma_{R_{X}}\sigma_{R_{Y}}}$)
       > Il rank di un valore è la sua posizione nell’insieme dei valori ordinato dal valore più piccolo a quello più grande.
3. Distribuzioni discrete notevoli
   - Distribuzione di Bernoulli ($P(X=k)=p^{k}q^{1-k}$, $\mu_{X}=p$, $\sigma_{X}^{2}=pq$)
   - Distribuzione binomiale ($P(X=k)=\binom{n}{k}p^{k}q^{n-k}$, $\mu_{X}=np$, $\sigma_{X}^{2}=npq$)
   - Distribuzione ipergeometrica ($P(X=k)=\frac{\binom{n}{k}\binom{N-n}{m-k}}{\binom{N}{m}}$ con $k\in[\max(0,n+m-N),\min(n,m)]$)
   - Distribuzione uniforme ($P(X=k)=\frac{1}{b}$ con $k\in[a,a+b-1]$, $\mu_{X}=a+\frac{b-1}{2}$, $\sigma_{X}^{2}=\frac{b^{2}-1}{12}$)
   - Distribuzione geometrica ($P(X=k)=qp^{k}$)
   - Distribuzione di Poisson ($P(X=k)=\frac{e^{-\lambda}\lambda^{k}}{k!}$, $\mu_{X}=\sigma_{X}^{2}=\lambda$)
   - Distribuzione multinomiale ($P(X_{1}=k_{1},\ldots,X_{n}=k_{n})=\frac{m!}{\prod\limits_{i=1}^{n}k_{i}!}\prod\limits_{i=1}^{n}p_{i}^{k_{i}}$)
4. Distribuzioni continue
   - Distribuzione uniforme ($f(x)=\frac{1}{b-a}$ con $x\in[a,b]$, $\mu_{X}=\frac{a+b}{2}$,$\sigma_{X}^{2}=\frac{(b-a)^{2}}{12}$)
   - Distribuzione normale ($f(x)=\frac{1}{\sqrt{2\pi}\beta}e^{-\frac{(x-\alpha)^{2}}{2\beta^{2}}}$, $\mu_{X}=\alpha$,$\sigma_{X}^{2}=\beta^{2}$)
   - Distribuzione normale standard ($f(z)=\frac{1}{\sqrt{2\pi}}e^{- \frac{z^{2}}{2}}$, $\mu_{X}=0$,$\sigma_{X}^{2}=1$) ($X=N(\mu,\sigma^{2}) \implies Z=\frac{X-\mu}{\sigma}$ chiamato **z-score**)
   - Distribuzione esponenziale ($f(x)=\lambda e^{-\lambda x}$, $\mu_{X}=\frac{1}{\lambda}$,$\sigma_{X}^{2}=\frac{1}{\lambda^{2}}$)
   - Distribuzione Chi-quadro \left($f(x)=\begin{cases} 0 &\text{ se } x<0\\ \frac{1}{\Gamma\left(\frac{n}{2}\right)}\left(\frac{1}{2}\right)^{\frac{n}{2}}X^{\frac{n}{2}-1}e^{\frac-{1}{2}x} &\text{ se } x\geq0 \end{cases}$, $\mu_{X}=n$,$\sigma_{X}^{2}=2n$)
   - Distribuzione T-student ($f(x)=\frac{\Gamma\left(\frac{n+1}{2}\right)}{\Gamma\left(\frac{n}{2}\right)} \frac{1}{\sqrt{n\pi}} \left(1+ \frac{x^{2}}{n}\right)^{-\frac{1}{2}(n+1)}$, $\mu_{X}=0$ se $n>1$,$\sigma_{X}^{2}=\frac{n}{n-1}$ se $n>2$)
   - Distribuzione normale multivariata ($f(x)=\frac{1}{(2\pi)^{\frac{n}{2}}\left|\Sigma\right|^{\frac{1}{2}}}e^{-\frac{1}{2}(\vec{x}-\vec{\mu})'\Sigma^{-1}(\vec{x}-\vec{\mu})}$)
## Insiemi Frequenti
1. Definizione del problema
   - Market-basket model
   - Insiemi frequenti
   - Regole di associazione ($I\to j$)
     - Supporto regola ($Supp(I\cup\{j\})$)
     - Coverage ($Supp(I)$)
     - Confidenza ($Conf(I\to j) = \frac{Supp(I\cup\{j\})}{Supp(I)}$)
     - Interesse ($Int(I\to j)=Conf(I\to j)-\frac{Supp(j)}{N}$)
     - Lift ($Lift(I\to j) = N\times \frac{Supp(I\cup\{j\})}{Supp(I)\times Supp(j)}$)
   - Insiemi frequenti massimali
   > non esiste un suo super-insieme frequente
   - Insiemi frequenti chiusi
     > non esiste un suo super-insieme che ha lo stesso supporto
2. Algoritmo Apriori
   - Principio Apriori
   - Descrizione dell’algoritmo
   - Strategie per il calcolo del supporto degli itemset.
3. Ottimizzazioni dell’Apriori
   - Algoritmi basati su funzioni hash (PCY, Multistage, Multihash) {Da rivedere}
   - Algoritmi randomizzati (SON, Toivonen) {Da rivedere}
## Clustering
> Il clustering è un processo che consiste nel raggruppare un insieme di oggetti in gruppi detti cluster, sulla base di una nozione di «distanza» tra gli oggetti.
> L’obbiettivo del clustering è quello di raggruppare nello stesso cluster oggetti «simili» tra loro (o con bassa distanza reciproca) e in cluster diversi oggetti «dissimili» tra loro (o ad elevata distanza).

1. Concetti generali
   - Spazi metrici
     - Euclideo
       - Distanza Euclidea ($D(x,y)=\sqrt{\sum\limits_{i=1}^{n}(x_{i}-y_{i})^{2}}$)
       - Distanza di Manhattan ($D(x,y)=\sum\limits_{i=1}^{n}|x_{i}-y_{i}|$)
       - Norma $L_{r}$ ($D(x,y)=\sqrt[r]{\sum\limits_{i=1}^{n}|x_{i}-y_{i}|^{r}}$)
       - Norma $L_{\infty}$ ($D(x,y)=\max\limits_{1\leq i\leq n}|x_{i}-y_{i}|$)
       - Distanza del coseno ($D(x,y)=\arccos\frac{\sum\limits_{i=1}^{n}x_{i}y_{i}}{\sqrt{\sum\limits_{i=1}^{n}x_{i}^{2}}\sqrt{\sum\limits_{i=1}^{n}y_{i}^{2}}}$)
     - Insiemi
       - Distanza di Jaccard ($D(S,T)=1-\frac{|S\cap T|}{|S\cup T|}$)
     - Stringhe
       - Distanza di edit (**il minimo numero di operazioni di cancellazione o inserzione di caratteri da effettuare partendo da x per ottenere y.**)
       - Distanza di Hamming (**il numero di componenti in corrispondenza delle quali x e y differiscono**)
   - Misure di distanza
     - Proprietà
       - $D(X,Y)\geq0\forall X,Y\in S$ e $D(X,Y)=0$ se e solo se $X=Y$
       - $D(X,Y)=D(Y,X)\forall X,Y\in S$ (Proprietà Simmetrica)
       - $D(X,Y)+D(Y,Z)\geq D(X,Z)\forall X,Y,Z\in S$ (Proprietà triangolare)
   - Tassonomia degli algoritmi di clustering
     - Metodi gerarchici o agglomerativi
     - Metodi di partizionamento (**K-means**)
     - Metodi basati sulla densità (**DBSCAN**, **OPTICS**)
     - Metodi bassati sulla griglia (**STING**)
     - Metodi basati sul moedllo (**EM**, **COBWEB**, **SOM**)
   - Problema della dimensionalità {da rivedere}
2. Clustering gerarchico ($O(n^{3})$ ottimizzabile fino a $O(n^{2}\log n)$)
   - Dendogramma
   - Criteri di combinazione
     - Distanza tra cluster
       - Centroidi
       - Medoidi
       - Single link (min)
       - Complete link (max)
       - Average link (avg)
     - Raggio del cluster
     - Diametro del cluster
     - Cluster aglomerativo vs divisivo
3. Clustering partizionale: algoritmo K-means
   - su big data (**BFR**, **CURE**)
4. Clustering basato su densità: algoritmo DBSCAN ($O(n\log n)$)
   - Definizioni
     - **$\epsilon$-intorno di un punto $Q$** ($N_{\epsilon}(Q) = \{\forall P|D(Q,P)\leq\epsilon\}$)
     - $P$ **Punto direttamente raggiungibile per densità** ($P\in N_{\epsilon}(Q) \land |N_{\epsilon}(Q)|\geq MinPts$)
     - $P$ **Punto raggiungibile per densità** ($A_{1}=Q, \ldots, A_{n}=P | A_{i+1}\in N_{\epsilon}(A_{i})$)
     - $P$ **Punto connesso per densità** ad un punto $Q$ (esiste un punto $O$ raggiungibile per densità sia da $P$ che da $Q$)
     - Cluster
       - $\forall P, Q\in D$, se $P\in C$ e $Q$ è raggiungibile per densità da $P$ allora $Q\in C$ (Massimilità)
       - $\forall P, Q\in C$, $P$ è connesso per densità a $Q$ (Connettività)
     - Stima di MinPts ($\geq D+1$) più alto quanto:
       - Più ampio è il dataset di punti
       - Maggiore è il rumore presente
     - Stima di $\epsilon$, si possono ordinare(Decrescente) i punti deldataset sulla base della distanza dal k-esimo punto più vicino, e plottarli, si otterrà una curva simile a quella per il clustering gerarchico, si seleziona la ordinata del punto del grafico in cui la curva piega maggiormente
5. Conclusioni
   - Scalabilità
   - Capacità di trappare tipi diiversi di attributi
   - Capacità di ricercare cluster di forma diversa
   - Facilità nell'uso e nella comprensione dei parametri di input
   - Capacità di gestire dati con outlier e rumore
   - Insensibilità all'ordine dei record in input e all'aggiunta di nuovi dati
   - Capacità di gestire dati ad elevata dimensionalità
   - Interpretabilità e usabilità dei risultati ottenuti
## Classificazione e predizione
> ***Classificazione***
> Predice l’etichetta della classe categoriale di appartenenza (discreta o nominale)
>
> Classifica i dati (attraverso un modello) basandosi sul training set ed i valori (etichette di classe) dell’attributo classificatore sono usati per classificare nuovi dati

> ***Predizione***
> modella funzioni continue e consente la predizione di dati sconosciuti o mancanti

1. Alberi decisionali
   - Algoritmi ***ID3, C4.5, CART***
   - Pruning
     - pre-pruning
     - post-pruning
       - C4.3: ***pessimistic pruning*** (**reduced error pruning**)
       - CART: ***cost-complexity pruning***
   - Estrazione di regole
     - Qualità di una regola
       - Coverage
       - Accuratezza
       - Esempi Positivi/Negativi
     - Risoluzione di conflitti
     - Algoritmi di covering
       - FOIL ($foilGain(R)=pos'\times \left(\log_{2}\frac{pos'}{pos'+neg'}-\log_{2}\frac{pos}{pos+neg}\right)$)
       - AQ
       - CN2
       - RIPPER
2. Classificatori bayesiani:
   - Naive Bayes
3. Classificatori discriminativi:
   - Perceptron ($wX+b$)
   - Support Vector Machines (SVM)
     - Hard margin ($\begin{cases} \min{||\vec{w}||} \\ y_{i}(\vec{w}\cdot\vec{x}_{i}-b)\geq1\;\forall 1\leq i\leq n \end{cases}$)
     - Soft margin ($\begin{cases} \min\left(\frac{1}{n}\sum\limits_{i=1}^{n}\epsilon_{i} +\lambda||\vec{w}||^{2}\right) \\ y_{i}(\vec{w}\cdot\vec{x}_{i}-b)\leq1-\epsilon_{i}\;\forall 1\leq i\leq n \\ \epsilon_{i}\geq0\;\forall1\leq i\leq n\end{cases}$) (duale lagringiano)
     - Mapping con kernel
4. Apprendimento lazy:
   - Algoritmo K-nearest neighbor.
5. Predizione:
   - Regressione
     - Lineare Semplice ($y=w_{0}+w_{1}x$ ove $w_{1}=\frac{\sum\limits_{i=1}^{n}(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sum\limits_{i=1}^{n}(x_{i}-\bar{x})^{2}}\;\;w_{0}=\bar{y}-w_{1}\bar{x}$)
     - Lineare Multipla (Caso $n$-dimensionale:  $y=w_{0} +w_{1}x_{1} +\ldots +w_{n}x_{n}$)
     -
6. Apprendimento ensemble:
   - Bootstrap;
   - Algoritmo Random Forest.
7. Validazione di un classificatore:
   - Misure di accuratezza
     - Recall / Sensitività / True Positive Rate: $Rec(M)= TPR(M)= \frac{T_{Pos}}{Pos}$
     - Specificità / True Negative Rate: $Spec(M)= \frac{T_{Neg}}{Neg}$
     - False Positive Rate: $FPR(M)= \frac{F_{Pos}}{Neg}$
     - False Discovery Rate: $FDR(M)= \frac{F_{Pos}}{T_{Pos}+F_{Pos}}$
     - Precisione: $Prec(M)= \frac{T_{Pos}}{T_{Pos}+F_{Pos}}$
     - Accuratezza: $Acc(m)= \frac{T_{Pos}+T_{Neg}}{Pos+Neg}$
     - F1 Score: $F1(M)= 2\times\frac{Prec(M)\times Rec(M)}{Prec(M)+Rec(M)}$
     - AUC
       - Curva ROC ($TPR$~$FPR$)
       - Curva PR ($Prec$~$Rec$)
   - Holdout
   - K-fold cross-validation
### Alberi decisionali
#### Algoritmo ID3
> Entropia distribuzione etichette
>
> $A:\max gain(A)$

- Sia $S_{x}$ avente n classi differenti $C_{1},\ldots,C_{n}$
- $H(S_{X}) = -\sum\limits_{i=1}^{n}\frac{freq(C_{i},S_{X})}{|S_{X}|}\log_{2}\frac{freq(C_{i},S_{X})}{|S_{X}|}$
- $\bar{H}_{A}(S_{x})=\sum\limits_{j=1}^{k}\frac{|S_{j}|}{|S_{k}|}\times H(S_{j})$
- $gain(A)=H(S_{X})-\bar{H}_{A}(S_{X})$
#### Algoritmo C4.5
> Migliora ID3 togliendo bias dovuto alla dimensionsione delle partizioni ottenute
>
> $A: \max(gainRatio(A))$

- $splitInfo(A)=-\sum\limits_{i=1}^{k}\frac{|S_{i}|}{|S_{X}|}\log_{2}\frac{|S_{i}|}{|S_{X}|}$
- $gainRatio(A)= \frac{gain(A)}{splitInfo(A)}$
#### Algoritmo CART (***Gini Index***)
> Chiamato anche ***Gini impurity***, misura l'impurità di un insieme di tuple $S_{X}$ associato ad un nodo dell'albero decisionale;
>
> Sia $i$ una classe e $T$ una tupla di classe $i$ scelta a caso da $S_{X}$;
>
> Supponiamo di assegnare a $T$ una classe $j$ random sulla base della distribuzione delle frequenze delle classi in $S_{X}$;
>
> Il Gini index misura la probabilità che $i\neq j$

Per ricavare la formula del ***Gini Index*** occore considerare:
a. $p_{i}$: La probabilità di scegliere un'osservazione di $S_{X}$ con classe $i$
b. $\sum\limits_{j=1,j\neq i}^{n}p_{j} = 1-p_{i}$: La probabilità di scegliere una class $j$ diversa da $i$ a partire dalla distribuzione delle frequenze delle classi

- $gini(S_{X}) = 1-\sum\limits_{i=1}^{n}p_{i}^{2}$
- $gini_{split}(S_{X})=\sum\limits_{i=1}^{k}\frac{|S_{i}|}{|S_{X}|}gini(S_{i})$
## Sistemi di raccomandazione
1. Sistemi di raccomandazione content-based
2. Sistemi di raccomandazione collaborative filtering
3. Singular Value Decomposition (SVD)
4. Valutazione di qualità di un sistema di raccomandazione
## Reti e modelli random
1. Concetti fondamentali sulle reti
   - Grafo e tipi di grafi
   - Grado di un nodo
   - Connettività del grafo: cammini, cicli e diametro del grafo
   - Coefficiente di clustering ($C_{n}=\frac{2L_{n}}{k_{n}\times(k_{n}-1)}$; $\braket{C}=\frac{1}{N}\sum\limits_{i=1}^{N}C_{i}$; $C_{\Delta}$)
   - Centrality
     - Degree
     - Betweenness
     - Closeness
     - PageRank ($PR(u)=\sum\limits_{v\in B_{u}}\frac{PR(v)}{k_{v}}$)
2. Modelli random
   - Modello di Erdos-Renyi (**metodo probabilitstico**)
     - $G(N,p)$
     - $G(N,L)$
     - Proprietà
       - $p_{k}=\binom{N-1}{k}p^{k}(1-p)^{N-1-k}$
       - $\braket{k}=p(N-1)$
       - $N>>\braket{k} \implies p_{k}=e^{-\braket{k}\frac{\braket{k}^{k}}{k!}}$
       - $\braket{d}\approx\frac{\ln N}{\ln \braket{k}}$ (small world)
       - $\braket{L_{n}}=p\frac{k_{n}(k_{n}-1)}{2}$
       - $C_{n}=\frac{\braket{L_{n}}}{\left(\frac{k_{n}(k_{n}-1)}{2}\right)}=p=\frac{\braket{k}}{N-1}$
     - Non Approssima bene le reti reali (ha solo la proprietà di distanza di un caso small world)
   - Reti small-world e modello di Watts-Strogatz (interpolazione tra **regolare** e **random** al variare di $p\in[0,1]$)
     - Input: $N$, $p$, $d$
     - Proprietà
       - $p_{k}=e^{-\braket{k}\frac{\braket{k}^{k}}{k!}}$
     - reti small world ed il giusto clustering, ma non ha la giusta distribuzione di gradi: Power-Law
   - Reti scale-free e modello di Albert-Barabasi (**random** + **growth** with **preferential attachment**)
     - Proprietà
       - $p_{k}\sim k^{-\gamma}\;\;2<\gamma<3$ (Power-Law)
     - Robustezza data dalla presenza di hub dovuto alla distribuzione Power-Law
## Graph Matching
1. Isomorfismo
2. Algoritmi di subgraph matching
   - Algoritmo di Ullman (grade pruning) (Best: $\Theta(n^{3})$; Worst: $\Theta(n!n^{3})$, Space: $\Theta(N^{3})$)
   - Algoritmo VF (State Space Represemtatopm) (Best: $\Theta(n^{2})$; Worst: $\Theta(n!n)$, Space: $\Theta(N^{2})$ o $\Theta(N)$ con VF2)
   - Algoritmo RI (Ordinamento + grade pruning)
3. Graph matching in un database di grafi
   - Algoritmo SING
## Graph Mining
1. Mining in un database di grafi
   - Algoritmo FSM
     - BFS / DFS
     - Join-based / Extend-based
   - Algoritmo FSG
     - BFS
     - single nodes join-based
     - forma canonica
   - Algoritmo GSPAN
2. Mining in un singolo grafo
   - Strategie di ricerca
     - network-centric
     - motif-centric
     - set-centric
   - Ricerca esatta vs sampling
## Reti Neurali
