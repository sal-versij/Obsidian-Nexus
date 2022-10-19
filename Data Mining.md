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
   - Distribuzione geometrica ($P(X=k)=qp^{k}$)
   - Distribuzione di Poisson ($P(X=k)=\frac{e^{-\lambda}\lambda^{k}}{k!}$, $\mu_{X}=\sigma_{X}^{2}=\lambda$)
   - Distribuzione multinomiale ($P(X_{1}=k_{1},\ldots,X_{n}=k_{n})=\frac{m!}{\prod\limits_{i=1}^{n}k_{i}!}\prod\limits_{i=1}^{n}p_{i}^{k_{i}}$)
4. Distribuzioni continue
   - Distribuzione uniforme ($f(x)=\frac{1}{b-a}$ con $x\in[a,b]$, $\mu_{X}=\frac{a+b}{2}$,$\sigma_{X}^{2}=\frac{(b-a)^{2}}{12}$)
   - Distribuzione normale ($f(x)=\frac{1}{\sqrt{2\pi}\beta}e^{-\frac{(x-\alpha)^{2}}{2\beta^{2}}}$, $\mu_{X}=\alpha$,$\sigma_{X}^{2}=\beta^{2}$)
   - Distribuzione normale standard ($f(z)=\frac{1}{\sqrt{2\pi}}e^{- \frac{z^{2}}{2}}$, $\mu_{X}=0$,$\sigma_{X}^{2}=1$) ($X=N(\mu,\sigma^{2}) \implies Z=\frac{X-\mu}{\sigma}$ chiamato **z-score**)
   - Distribuzione esponenziale ($f(x)=\lambda e^{-\lambda x}$, $\mu_{X}=\frac{1}{\lambda}$,$\sigma_{X}^{2}=\frac{1}{\lambda^{2}}$)
   - Distribuzione Chi-quadro ($f(x)=\begin{cases} 0 &\text{se} x<0\\  \end{cases}$, $\mu_{X}=$,$\sigma_{X}^{2}=$)
   - Distribuzione T-student ($f(x)=$, $\mu_{X}=$,$\sigma_{X}^{2}=$)
   - Distribuzione normale multivariata ($f(x)=$, $\mu_{X}=$,$\sigma_{X}^{2}=$)
