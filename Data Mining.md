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
1. Statistiche di una distribuzione
	- Media ($\mathbb{E}[X]=\mu_{X}=\sum\limits_{x\in R(X)}xP(X=x)$)
	- Varianza ($\mathbb{E}[(X-\mu_{X})^{2}]=\sigma_{X}^{2}=\sum\limits_{x\in R(X)}(x-\mu_{X})^{2}P(X=x)$)
	- Entropia ($H(P(X))=-\sum\limits_{x\in R(X)}P(X=x)\log P(X=x)$)
		- Entropia relativa ($H(P||Q)=\sum\limits_{x\in R(X)}P(X=x)\log\frac{P(X=x)}{Q(X=x)}$)
		- Divergenza ($J(P||Q) = H(P||Q) + H(Q||P)$)
	- Covarianza ($\sigma_{X,Y}=\mathbb{E}[(X-\mu_{X})(Y-\mu_{Y})]$)
		- Matrice di covarianza ($\Sigma$)
	- Correlazione (di Pearson) ($\rho_{X,Y}=\frac{\sigma_{X,Y}}{\sigma_{X}\sigma_{Y}}$)
2. Distribuzioni discrete notevoli
	- Distribuzione di Bernoulli
	- Distribuzione binomiale
	- Distribuzione uniforme
	- Distribuzione geometrica
	- Distribuzione binomiale negativa
	- Distribuzione di Poisson
	- Distribuzione multinomiale
3. Distribuzioni continue
	- Variabili aleatorie continue
	- Distribuzione uniforme
	- Distribuzione normale
	- Distribuzione esponenziale
	- Distribuzione Chi-quadro
	- Distribuzione T-student
	- Distribuzione normale multivariata
