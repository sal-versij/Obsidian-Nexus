# Funzione di ripartizione
#todo #matematica #statistica
!def
Data la variabile aleatoria $X$ è detta **funzione di ripartizione** di $X$ la funzione
$F_x(t)=P[X\leq t]=P[A_t]$
$F_x(t):\mathbb{R}\to[0,1]$
## Proprietà
1. $F_x$ è monotona non decrescente
   $t_1\leq t_2 \implies F_x(t_1)\leq F_x(t_2)$
   $A_{t_1}\subseteq A_{t_2} \implies P[A_{t_1}]$
2. $\lim\limits_{t\to-\infty} F_x(t) = 0$; $\lim\limits_{t\to+\infty} F_x(t) = 1$
3. Per ogni valore $c_o\in\mathbb{R}$
   $P[X=x_0] = \lim\limits_{t\to x_0^{+}} F_x(t) - \lim\limits_{t\to x_0^{-}} F_x(t)$
4. $F_x$ è continua a destra
   $F_x[x_0](=P[X\leq x_0])=\lim\limits_{t\to x_0^{+}} F_x(t)\;\forall x_0\in\mathbb{R}$

!note
Se la variabile aleatoria $X$ può assumere solo un numero finito (o al più numerabile) di valori, la relativa $F_x$ sarà costante a tratti e la variabile viene detta discreta
Se $X$ può assumere i valori di un intervallo $I\subset\mathbb{R}$, allora $F_x$ è generalmente continua e la variabile è detta continua