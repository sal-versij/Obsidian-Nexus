# Forza di attrito radente
#todo #physics
!def
La forza di attrito radente si oppone al movimento tra due superfici a contatto che strisciano l’una sull’altra. Tale forza dipende dalla natura delle superfici a contatto (materiali e livello di finitura) e dal carico applicato nella direzione perpendicolare a quella del moto (forza Normale).

!theorem Attrito statico
$F_s$
!theorem Attrito dinamico
$F_k$

!note Risultati sperimentali sull'attrito

- Proporzionalità al modulo della forza normale
- Indipendenza dall'area di contatto
- Dipendenza dalle superfici a contatto
- $\vec{F_s}$ è opposta alla forza applicata e può assumere valori
  $F_s\leq \mu_sN$
- $\vec{F_k}$ è opposta alla direzione del moto:
  $F_k = \mu_kN$

!theorem
$\vec{F_{attr}}$
## Coeficiente di attrito
$\mu: [0.05,1.5]$
$\mu_k\lt\mu_s$
### Determinazione Sperimentale
#### Caso Statico
![[determinare-mu-statico.jpg]]

$$
\begin{gather}
\vec{F_s} + \vec{N} + \vec{P} = 0 \newline
\newline
\begin{cases}
F_s\leq\mu_sN \\
N &= mg\cos\theta \\
-F_s + mg\sin\theta &=0
\end{cases}\newline
\newline
F_s \text{ massima per } \theta = \theta_s \newline
\mu_smg\cos\theta_s=mg\sin\theta_s\newline
\implies \mu_s=\tan\theta_s
\end{gather}
$$
#### Caso Dinamico
#todo 