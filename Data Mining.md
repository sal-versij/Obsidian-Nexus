# Data Mining
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
   - Distribuzione geometrica ($P(X=k)=qp^{k}$, $\mu_{X}=$, $\sigma_{X}^{2}=$)
   - Distribuzione binomiale negativa ($P(X=k)=$, $\mu_{X}=$, $\sigma_{X}^{2}=$)
   - Distribuzione di Poisson ($P(X=k)=$, $\mu_{X}=$, $\sigma_{X}^{2}=$)
   - Distribuzione multinomiale ($P(X=k)=$, $\mu_{X}=$, $\sigma_{X}^{2}=$)
4. Distribuzioni continue
   - Variabili aleatorie continue
   - Distribuzione uniforme
   - Distribuzione normale
   - Distribuzione esponenziale
   - Distribuzione Chi-quadro
   - Distribuzione T-student
   - Distribuzione normale multivariata
