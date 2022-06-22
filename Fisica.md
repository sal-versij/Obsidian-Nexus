# Fisica
## Introduzione
### Grandezza fisica
È definita quando abbiamo stabilito un procedimento, ovvero un insieme di norme atte a misurare tale grandezza e ad assegnarle un'unità di misura
### Sistema Internazionale
#### MKSA
| Grandezza             | Simbolo    | Misura      | Unità |
| --------------------- | ---------- | ----------- | ----- |
| Lunghezza             | $[L]$      | Metro       | `m`   |
| Massa                 | $[M]$      | Chilogrammo | `kg`  |
| Tempo                 | $[T]$      | Secondo     | `s`   |
| Intensità di corrente | $[I]$      | Ampère      | `A`   |
| Temperatura           | $[\Theta]$ | Kelvin      | `K`   |
| Intensità luminosa    | $[J]$      | Candela     | `cd`  |
| Quantità di materia   | $[N]$      | mole        | `mol` |

---
### Altro
- Equazione dimensionale
- Errori di misura
- Approssimazione
- Notazione scientifica
- Grandezze scalari e grandezze vettoriali
- Somma di vettori
- Componenti di un vettore
- Prodotto scalare e prodotto vettoriale
- Prodotto scalare: Proprietà
## Cinematica
### Moti rettilinei
Velocità: $v_{x}= \frac{dx}{dt}$
Accelerazione: $a_{x}= \frac{dv_{x}}{dt}$
N.B. $v_{x}dv_{x} = v_{x}a_{x}dt = a_{x}dx$
#### Moto rettilineo uniforme
> $a_{x}(t)=0$
> $v_{x}(t)={v_{x}}_{0}$
> Eq. Orarie
> $x(t)=x_{0}+{v_{x}}_{0}t$
#### Moto rettilineo uniformemente accelerato
> $a_{x}(t)={a_{x}}_{0}$
> Eq. Orarie
> $x(t)=x_{0} + {v_{x}}_{0}t + \frac{1}{2}a_{x}t^{2}$
> $v_{x}(t) = {v_{x}}_{0} + a_{x}t$
### Moto parabolico
> Eq. Orarie
> $\begin{cases} x={v_{x}}_{0}t \\ y={v_{y}}_{0}t - \frac{1}{2}gt^{2} \end{cases}$
### Moti circolari
Raggio: $r$
Arco: $s$
Posizione angolare: $\theta = \theta(t) = \frac{s}{r}$
Velocità angolare media: $\omega_{m}= \frac{\theta_{2}-\theta_{1}}{t_{2}-t_{1}} = \frac{\Delta\theta}{\Delta t}$
Velocità angolare: $\omega = \omega(t)= \lim\limits_{\Delta t\to0} \frac{\Delta\theta}{\Delta t} = \frac{d\theta}{dt}$
Accellerazione angolare media: $\alpha_{m} = \frac{\omega_{2}-\omega_{1}}{t_{2}-t_{1}} = \frac{\Delta\omega}{\Delta t}$
Accellerazione angolare: $\alpha = \alpha(t)= \lim\limits_{\Delta t\to0} \frac{\Delta\omega}{\Delta t} = \frac{d\omega}{dt} = \frac{d^{2}\theta}{dt^2}$

Introducendo il sistema di riferimeno cartesiano $O_{xy}$
$x(t) = r \cos[\theta(t)]$
$y(t) = r \sin[\theta(t)]$
#### Moto circolare uniforme
> $v = \frac{ds}{dt} = \text{costante}$
> $\omega = \frac{d\theta}{dt}=\frac{d}{dt} \left( \frac{1}{r} \right) = \frac{1}{r} \frac{ds}{dt} = \frac{v}{r} = \text{costante}$
> Eq. Oraria
> $s(t) = s_0 + vt$
> $\theta(t)=\theta_{0} + \omega t$
#### Moto circolare uniformemente accelerato
> $\alpha = \text{costante}$
> Eq. Oraria
> $\theta(t)=\theta_{0} + \omega_0 t + \frac{1}{2}\alpha t^2$
> $\omega(t) = \omega_{0} + \alpha t$
### Cinematica rotazionale
$s=\theta r$
$v = \frac{ds}{dt}=r\frac{d\theta}{dt} = r\omega \implies v = r\omega$
$a_{T} = \frac{dv}{dt} = r \frac{d\omega}{dt}=r\alpha \implies a_{T} = r\alpha$
$a_{R} = \frac{v^{2}}{r} \implies a_{R} = r\omega^{2}$
### Altro
- Prodotto vettoriale: Proprietà
- Derivata di un vettore
- Velocità
- Accelerazione
- Somma integrale di vettori
- Legge oraria
- Moto nel piano
## Dinamica del punto materiale
Glossario

| Nome      | definizione                                                                                                                        |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Legge     | Relazione determinata  e costante fra grandezze variabili che entrano in un fenomeno                                               |
| Principio | Idea originaria, criterio dal quale deriva un sistema di idee o sul quale si fondano gli elementi di una speculazione              |
| Postulato | Proposizione non dimostrata (e non necessariamente evidente), ma ammessa come vera per fondare un procedimento o una dimostrazione |
| Assioma   | Principio iniziale evidente ed indimostrabile che può fare da premessa ad un ragionamento, una teoria, etc.                        |

In matematica
Assioma $\equiv$ Postulato

In fisica
Legge $\equiv$ Principio
### Leggi di newton
#### Principio di inerzia
Un corpo non soggetto a forze esterne permane nel suo stato di quiete o di moto rettiliineo uniforme

Massa inerziale
$m_{1} = m_{0} \frac{a_{0}}{a_{1}}$
#### Forza
$\vec{F}=m\vec{a}$
#### Principio di Azione e Reazione
Quando due corpiinteragiscono la forza $\vec{F}_{12}$(**azione**)  che il corpo 1 esercita sul corpo 2 è uguale ed opposta alla forza $\vec{F}_{21}$(**reazione**) che il corpo 2 esercita sul corpo 1
$\vec{F}_{12} = -\vec{F}_{21}$
Unità di misura
$[F] = [m][a] = [M][LT^{-2}] = [MLT^{-2}]$
$\frac{\text{kg m}}{\text{s}^{2}}\equiv\text{N}$ (**Newton**)
### Reazioni vincolari
- Reazione Normale ($\vec{N}$)
- Tensione Molla ($\vec{T}$)
- Tensione dei fili ($\vec{F}_{T}$)
- Diagramma del corpo libero
  - Moto lungo un piano inclinato liscio
  - Moto lungo un piano inclinato scabro
- Forza di attrito radente ($\vec{F}_{att} = \mu N(-\hat{s})$)
  - statico ($F < F_{s} \implies v = 0$, $F_{s} \leq \mu_{s}N$)
  - dinamico ($F = F_{k} \implies v = \text{cost}$, $F_{k} = \mu_{k}N$)
- Moti circolari: Forze centripete ($a_{r} = \frac{v^{2}}{r}$, $\vec{F}_{\text{cent.}} = \frac{mv^{2}}{r}$, $\min\mu_{s} = \frac{v^{2}}{gr}$)
### Dinamica Rotazionale
Momento meccanico ($\vec{\tau} = \vec{r}\land\vec{F}$, $[\tau]=[Nm]$)
Momento angolare ($\vec{L} = \vec{r}\land\vec{p}$,$[L]=\left[\frac{m^{2}\,kg}{s}\right]$)
Correlazione

$$
\frac{d\vec{L}}{dt} =
\frac{d}{dt} \left( \vec{r} \land \vec{p} \right) = 
\frac{d\vec{r}}{dt} \land \vec{p} + \vec{r} \land \frac{d\vec{p}}{dt} = 
\vec{v} \land m\vec{v} + \vec{r} \land \vec{F} = 
\vec{r} \land \vec{F} = 
\vec{\tau}
$$

Conservazione del momento angolare
$\vec{\tau} = 0 \implies \vec{L} = \text{const}$
### Altro
- Leggi della forza gravitazionale ($F_{12} = F_{21} = G \frac{m_{1}m_{2}}{r^{2}}$)
- forza peso ($F=mg$)
- forza elastica ($F = kx$)
- Quantità di moto ($\vec{p} = m\vec{v}$, $\vec{F} = \frac{d\vec{p}}{dt}$)
- Impulso ($\vec{J} = \int\limits_{0}^{t}\vec{F}dt \implies \vec{J} = \Delta\vec{p}$)
## Conservazione dell'energia
### Calcolo di energia potenziale
#### Forza peso:
$U(P) = U(y) = -\int\limits_{0}^{P}\vec{P}\cdot d\, \vec{y} +U(0) = -\int\limits_{0}^{y}(-mg)dy +U(0) = mgy +U(0)$
$U(0) = 0 \implies U(y) = mgy$
#### Forza elastica:
$U(P) = U(x) = -\int\limits_{0}^{P}\vec{F_{el}}\cdot d\, \vec{x} +U(0) = -\int\limits_{0}^{x}(-kx)dx +U(0) = \frac{1}{2}kx^{2} +U(0)$
$U(0) = 0 \implies U(y) = \frac{1}{2}kx^{2}$
#### Gravitazionale:
$F_{G} = -G\frac{Mm}{r^{2}}\hat{r}$
$\Delta U = U(P) - U(P_{0}) = -\int\limits_{P_{0}}^{P} \vec{F_{G}} \cdot d\,\vec{r} = -\int\limits_{P_{0}}^{P} -G\frac{Mm}{r^{2}}\hat{r} \cdot d\,\vec{r} = GMm \int\limits_{r_{0}}^{r} \frac{dr}{r^{2}} = -GMm \left( \frac{1}{r} - \frac{1}{r_{0}} \right)$
### Forze non conservative
#### Forza di attrito
$W = \int\limits_{la}^{b}\vec{F_{a}} \cdot d\,\vec{r} = \int\limits_{la}^{b}\mu N(-\hat{s}) \cdot d\,\vec{r}$
dove
$\hat{s} \parallel d\,\vec{r} \implies \hat{s} \cdot d\,\vec{r} = dr$

$W = -\mu N \int\limits_{la}^{b}dr$
In base al percorso: $W = -\mu Nl$
### Altro
- Generalità sui principi di conservazione
- Principio di conservazione dell’energia
- Lavoro ($W = \vec{F}\cdot\vec{\Delta r}$ $[J] = [MS^{2}T^{-2}]$)
- Energia cinetica ($K= \frac{1}{2}mv^{2}$)
- Teorema dell'energia cinetica (o delle forze vive) ($W = K_{b} - K_{a} = \Delta K$)
- Forze conservative
  1. Una forza si dice conservativa se l'energia cinetica della particella su cui agisce torna ad assumere il suo valore iniziale dopo ogni qualsiasi percorso chiuso
  2. Una forza si dice conservativa se il lavoro compiuto dalla forza su un punto materiale che si muove su un qualsiasi percorso chiuso è nullo
  3. Una forza si dice conservativa se il lavoro compiuto dalla forza per spostare un punto materiale da un punto ad un altro dipende soltanto da questi due punti e non dal percorso
- Energia potenziale ($U | W_{c} = -(U_{B} - U_{A}) = -\Delta U$)
- Conservazione dell’energia meccanica ($E = K + U$; $W = \Delta K = W_{nc} + W_{c} \overset{W_{c} = -\Delta U}{\implies} \Delta K = W_{nc} - \Delta U \implies W_{nc} = \Delta K + \Delta U = \Delta E \implies (W_{nc} = 0 \implies E = \text{const})$)
  - Potenza ($P_{m} = \frac{W}{\Delta t}$; $P = \frac{dW}{dt}$; $[W]=[J/s]=[MS^{2}T^{-3}]$) ($\begin{cases} dW &= P dt \\ dW &= \vec{F}\cdot d\,\vec{r} = \vec{F}\cdot\vec{v} dt \end{cases}\implies P=\vec{F}\cdot\vec{v}$)
## Dinamica dei sistemi di punti materiali
- Sistemi di punti
  - Forze interne ($F_{i}^{(I)}$ generalmente $=0$)
  - Forze esterne ($F_{i}^{(E)}$)
- Centro di massa ($\vec{r}_{CM} = \frac{\sum\limits_{i=1}^{n}m_{i}\vec{r}_{i}}{M}$; $M=\sum\limits_{i=1}^{n}m_{i}$)
- Moto del centro di massa ($\vec{P}_{tot} = M \vec{v}_{CM}$; $F_{tot}^{(E)} = M\vec{a}_{CM} = \frac{d}{dt}\vec{P}_{tot}$)
- Conservazione della quantità di moto ($\Delta \vec{P}_{tot} = 0$)
- Urti tra punti materiali
  - elastico ($\Delta K_{tot} = 0$; $\Delta \vec{P}_{tot} = 0$)
  - anelastico ($\Delta K \neq 0$; $\Delta \vec{P}_{tot} \neq 0$)
  - completamente anelastico ($P_{tot}=\text{const}$)
- Urto elastico frontale ($\begin{cases} w_{1} &= \frac{m_{1}-m_{2}}{m_{1}+m_{2}} v_{1} &+ \frac{2m_{2}}{m_{1}+m_{2}} v_{2} \\ w_{2} &= \frac{2m_{1}}{m_{1}+m_{2}} v_{1} &+ \frac{m_{2}-m_{1}}{m_{1}+m_{2}} v_{2} \end{cases}$)
- Momenti
  - Momento angolare ($\vec{L}_{tot} = \sum\limits_{i=1}^{n}\vec{L}_{i} = \sum\limits_{i=1}^{n}\vec{r}_{i} \wedge m_{i}\vec{v}_{i}$)
  - Momento meccanico ($\vec{\tau}_{tot} = \sum\limits_{i=1}^{n}\vec{\tau}^{(I)}_{i} + \sum\limits_{i=1}^{n}\vec{\tau}^{(E)}_{i} \overset{\vec{\tau}^{(I)}_{tot}=0} \implies \vec{\tau}_{tot} = \vec{\tau}^{(E)}_{tot}$)
  - Correlazione
    - Polo Fisso
    $\frac{d\vec{L}_{tot}}{dt} = \vec{\tau}^{(E)}_{tot}$
    - Polo Mobile con velocità ($\vec{v}_{0}$)
    $\frac{d\vec{L}_{tot}}{dt} = \vec{\tau}^{(E)}_{tot} - \vec{v}_{0} \wedge \vec{P}_{tot}$
    - Generalmente ($\vec{\tau}^{(E)}_{tot} = \frac{d\vec{L}_{tot}}{dt} + \vec{v}_{0} \wedge M \vec{v}_{CM}$)
- Teorema del momento angolare ($\vec{\tau}^{(E)}_{tot} = \frac{d\vec{L}_{tot}}{dt} \equiv \vec{v}_{0} \wedge M \vec{v}_{CM} = 0$)
  - $O$ fisso $\impliedby \vec{v}_{0}=0$
  - $CM$ fermo $\impliedby \vec{v}_{CM} = 0$
  - $O \equiv CM \impliedby \vec{v}_{CM} = \vec{v}_{O}$
  - $O$ si muove parallelemente al moto del $CM$$\impliedby \vec{v}_{O}\parallel\vec{v}_{CM}$
- Conservazione del momento angolare ($\tau^{(E)} = 0 \implies \vec{L} = \text{const}$)
## Dinamica del corpo rigido
### Corpo rigido
> sistema di punti materiali in cui le distanze tra tutte le possibili coppie di punti non possono variare
#### Densità
- Corpo ($\rho = \frac{dm}{dV} \left[\frac{kg}{m^{3}}\right]$)
- Superficiale ($\sigma = \frac{dm}{dS} \left[\frac{kg}{m^{2}}\right]$)
- Lineare ($\lambda = \frac{dm}{dL} \left[\frac{kg}{m}\right]$)
#### Massa
$M = \int_{V}\rho dV$
#### Corpo omogeneo
$\rho = \text{const} = \frac{M}{V}$
#### Centro di massa
$\vec{r}_{CM} = \frac{\int_{V}\vec{r}dm}{\int_{M}dm} = \frac{\int_{V}\vec{r}\rho dV}{M}$
$\rho = \text{const} \implies \vec{r}_{CM} = \frac{\rho\int_{V}\vec{r} dV}{M} = \frac{\int_{V}\vec{r} dV}{V}$
### Corpo continuo soggetto alla forza peso
$\vec{P}_{tot} = \int_{M}\vec{g}dm = \vec{g}\int_{M}dm = M\vec{g}$

$$
\displaylines{
\vec{\tau}_{tot} = \int_{M}\vec{r}\wedge\vec{g}dm = \left( \int_M\vec{r}dm \right)\wedge\vec{g} = M \frac{\int_M\vec{r}dm}{M}\wedge\vec{g} = \\
M\vec{r}_{CM}\wedge\vec{g} = \vec{r}_{CM}\wedge M\vec{g} = \\
\vec{r}_{CM}\wedge\vec{P}_{tot}
}
$$

> Se z è la quota dell’elemento di massa $dm$ rispetto alla quota di riferimento, esso avrà energia potenziale:

$dU = z g dm$
$U = \int_{M}zgdm = g\int_{M}zdm = gM \frac{\int_{M}zdm}{M} = M g z_{CM}$
### Moto di un corpo rigido
#### Moto di pura traslazione
> tutti i punti descrivono traiettorie eguali, percorse con la stessa velocità $v = v_{CM}$

$$
\displaylines{
\vec{v}_{i} = \vec{v}_{CM} \\
\vec{P}_{tot} = M\vec{v}_{CM} \\
\vec{F}^{(E)}_{tot} = M\vec{a}_{CM} = \frac{d\vec{P}_{tot}}{dt} \\
E_{cin} = \frac{1}{2}Mv_{CM}^{2} \\
}
$$
#### Moto di pura rotazione
> tutti i punti descrivono un moto circolare, le traiettorie sono archi di circonferenze diverse che stanno su piani paralleli e hanno il centro su uno stesso asse, l’asse di rotazione. In un dato istante tutti i punti hanno la stessa velocità angolare $\vec{\omega}$ che è parallela all’asse di rotazione

$$
\displaylines{
\tau^{(E)}_{tot} = \frac{d\vec{L}}{dt}
}
$$
#### Moto rispetto al centro di massa
> La velocità di ogni punto è la somma della velocità di traslazione ($\vec{v}_{CM}$) e della velocità lineare legata al moto di rotazione ($\vec{v}_{rot}= \vec{\omega}\wedge\vec{r}$)
#### Moto di rototraslazione
> traslazione infinitesima con velocità $\vec{v}$ + rotazione infinitesima con velocità angolare $\vec{\omega}$
>
> con $\vec{v}$ e $\vec{\omega}$ variabili nel tempo e indipendenti tra di loro

$K = \frac{1}{2}Mv_{CM}^{2} + \frac{1}{2}I_{CM}\omega^{2}$

```ad-note
La descrizione del moto di rotazione di un corpo rigido non è univoca.
$\vec{\omega}$ è unica, $\vec{v}$ dipende dall'asse di rotazione scelto.
```
##### Moto di rotolamento puro
> Si ha un ***MOTO DI ROTOLAMENTO PURO***, ovvero di **non scivolamento**, quando il punto di contatto è fermo:
> $v_{Q} = 0$ dato da $v_{CM} = \omega R$
> In questo caso
> $K = \frac{1}{2}Mv_{CM}^{2} + \frac{1}{2}I_{CM}\omega^{2} = \frac{1}{2}M(\omega R)^{2} + \frac{1}{2}I_{CM}\omega^{2} = \frac{1}{2}(I_{CM}+MR^{2})\omega^{2} = \frac{1}{2}I_{Q}\omega^{2}$

> Il moto è equivalente ad un *moto di pura rotazione*, con velocità angolare $\omega$, attorno ad un asse di istantanea rotazione passante per il punto di contatto $Q$.

```ad-eg
title: Applicazione di una forza costante
![[Moto di puro rotolamento - example.jpg]]
Eq. del moto

$$
\displaylines{
\begin{cases}
\vec{F}_{c,\;tot} &= M\vec{a}_{CM}\\
\vec{\tau}    &= I_{c}\vec{\alpha}
\end{cases} \\

\vec{F}_{tot} = M\vec{g} + \vec{F} + \vec{N} + \vec{f} \\
\vec{\tau}    = \vec{R}\wedge\vec{f} \\

\begin{cases}
F-f    &= M\vec{a}_{CM}\\
N - Mg &= 0 \\
Rf     &= I_{CM}\alpha
\end{cases};
\begin{cases}
f &= I_{CM} \frac{a_{CM}}{R^{2}}\\
N &= Mg \\
F &= Ma_{CM}+f
\end{cases} \\

a_{CM} = \frac{F}{M} \frac{1}{1+\frac{I_{CM}}{MR^{2}}} \\
f = \frac{F}{1+\frac{MR^{2}}{I_{CM}}}
}
$$
Condizione di non scivolamento
$f\leq\mu_{s}N = \mu_{s}Mg \implies F\leq\mu_sMg\left(1+\frac{MR^{2}}{I_{CM}}\right)$
```

```ad-eg
title: Applicazione di un momento costante
![[Moto di puro rotolamento - example (2).jpg]]
Eq. del moto

$$
\displaylines{
\begin{cases}
\vec{F}_{c,\;tot} &= M\vec{a}_{CM}\\
\vec{\tau}    &= I_{c}\vec{\alpha}
\end{cases} \\

\vec{F}_{tot}    = M\vec{g} + \vec{N} + \vec{f} \\
\vec{\tau}_{tot} = \vec{\tau} + \vec{R}\wedge\vec{f} \\

\begin{cases}
f          &= M\vec{a}_{CM} \\
N - Mg     &= 0              \\
-\tau + Rf &= -I\alpha        \\
\alpha     &= \frac{a_{CM}}{R} \\
\end{cases} \\

a_{CM} = \frac{\tau}{MR(1+\frac{I}{MR^{2}})} \\
f = \frac{\tau}{R(1+\frac{I}{MR^{2}})}
}
$$

Condizione di non scivolamento
$f\leq\mu_{s}N = \mu_{s}Mg \implies \tau\leq\mu_sMgR\left(1+\frac{I}{MR^{2}}\right)$
```
### Rotazioni rigide attorno ad un asse fisso in un sistema di riferimento inerziale
#### Momento Angolare
- asse di rotazione: asse $\hat{z}$
- velocità angolare $\vec{\omega} \parallel \hat{z}$
- accellerazione angolare $\vec{\alpha} = \frac{d\vec{\omega}}{dt} \parallel \hat{z}$
- momento angolare
  $d\vec{L} = \vec{r}\wedge dm\vec{v}$
  $\vec{r} \bot \vec{v}$
  $dL = r\,dm\,v = r\,dm\,\omega\,R$
- momento angolare assiale
  $dL_{z} = dL cos\left(\frac{\pi}{2}-\theta\right) = dL sin\theta = r\,dm\,\omega\,R\,sin\theta = \left(r\,sin\theta\right)dm\,\omega\,R = dm\,R^{2}\,\omega$
- momento angolare del corpo ($\vec{L} = \int d\vec{L}$; $L_{z} = \int dL_{z} = \int dm\,R^{2}\,\omega = \left(\int dm\,R^{2}\right)\omega$)
- momento di inerzia del corpo rispetto all’asse z
  $I_{z} = \int dm\,R^{2} = \int dm(x^{2}+y^{2})$
  $L_{z} = I_{z}\omega$
- componente ortogonale all’asse di rotazione
  $L_{\bot} = \int dL_{bot} = \int dL\,cos\theta = r\,dm\,\omega\,R\,cos\theta$
  $L_{bot} = 0 \iff \hat{z}$ è un'asse di simmetria e $\vec{L}\parallel\vec{\omega}$; $\vec{\tau}\parallel\vec{\alpha}$
### Lavoro ed energia cinetica nel moto rotatorio
Energia cinetica
$K_{tot} = \int \frac{1}{2}dm\,v^{2}= \int \frac{1}{2}dm (\omega R)^{2}= \frac{1}{2}\omega^{2}\int R^{2}dm = \frac{1}{2}I_{z}\omega^{2}$
Lavoro
$W= \Delta K = \frac{1}{2}I_{z}\omega_{f}^{2} - \frac{1}{2}I_{z}\omega_{i}^{2}$
$dW = dL = d\left(\frac{1}{2}I_{z}\omega^{2}\right) = \frac{1}{2}I_{z}d\left(\omega^{2}\right) = \frac{1}{2}I_{z}\left(2\omega d\omega\right) = I_{z}\omega d\omega$
$dW = I_{z}\omega d\omega = I_{z} \frac{d\theta}{dt} (\alpha dt) = I_{z}\alpha\,d\theta = \tau_{z}\,d\theta$
$W = \int\limits_{\theta_{0}}^{\theta}\tau_{z}d\theta$
Potenza meccanica
$P = \frac{dW}{dt} = \tau_{z} \frac{d\theta}{dt}= \tau_{z}\omega$
Momento di inerzia
$I = \int dm\,R^2$
### Teorema di Huygens-Steiner
> Si dimostra che il momento di inerzia $I$ di un corpo di massa $M$ rispetto ad un asse che dista $a$ dal $CM$ è dato da
> $I = I_{CM} + M\;a^2$
> ove $I_{CM}$ è il momento di inerzia rispetto ad un asse parallelo al precedente e passante per $CM$ (Teorema degli assi paralleli)
### Leggi di conservazione nel moto di un corpo rigido
#### Conservazione del momento angolare
$\vec{\tau}^{(E)}_{tot} = \frac{d\vec{L}_{tot}}{dt} + \vec{v}_{0} \wedge M \vec{v}_{CM}$
Se il polo $O$ è:

- fisso in un sistema di riferimento inerziale
- $O\equiv CM$ (potendo in questo caso essere anche mobile)

possiamo scrivere:
$\vec{\tau}^{(E)}_{tot} = \frac{d\vec{L}_{tot}}{dt}$
Quindi
$\vec{\tau}^{(E)}_{tot} = 0 \implies \vec{L}_{tot} = \text{const}$
Se l'asse di rotazione è un'asse di simmetria, potremo scrivere:
$\vec{L}_{tot} = I\vec{\omega} = \text{const}$
In ogni caso potremo scrivere in forma scalare per la componente $L_{z}$
$I_{z}\omega = \text{const}$
$\omega$ variabile se varia $I_{z}$ che piò essere fatta variare cambiando la posizione relativa delle singole parti del corpo
## Oscillazioni
### Equazione differenziale dello oscillatore armonico semplice
$\frac{d^{2}x}{dt^{2}} + \omega^{2}x = 0$
la soluzione più generale è:
$x(t) = a\sin\omega t+b\cos\omega t$
ovvero
$x(t) = A\sin(\omega t+\phi)$ $[a=A\cos\phi;b=A\sin\phi]$
$x(t) = B\cos(\omega t+\psi)$ $[a=-B\sin\psi;b=B\cos\psi]$
ove
$A=B=\sqrt{a^{2}+b^{2}}$; $\tan\phi = \frac{b}{a}$ ; $\tan\psi = -\frac{a}{b}$; $(\psi = \phi - \frac{\pi}{2})$
### Sistema massa-molla
$\frac{d^{2}x}{dt^{2}} + \frac{k}{m}x = 0$
$x(t) = A\sin(\omega t + \phi)$
$\frac{dx}{dt} = A\omega\cos(\omega t + \phi)$
$\frac{d^{2}x}{dt^{2}} = -A\omega^{2}\sin(\omega t + \phi)$
$\omega^{2} = \frac{k}{m}\implies\omega = \sqrt{\frac{k}{m}}$

$x\left(t + \frac{2\pi}{\omega}\right) = x(t)$
Periodo: $T = \frac{2\pi}{\omega} = 2\pi\sqrt{\frac{m}{k}}$
Frequenza: $\nu = \frac{1}{T} = \frac{1}{2\pi}\sqrt{\frac{k}{m}}$
#### Determinare $A$ e $\phi$
$$$
\displaylines{
\begin{cases}
x_{0} &= A\sin\phi\\
v_{0} &= A\omega\cos\phi\\
\end{cases}; 
\begin{cases}
A\sin\phi &= x_{0}               \\
A\cos\phi &= \frac{v_{0}}{\omega} \\
\end{cases} \\
\begin{cases}
A^{2}(\sin^{2}\phi+\cos^{2}\phi) &= x_{0}^{2} + \left(\frac{v_{0}}{\omega}\right)^{2}\\
\frac{\sin\phi}{\cos\phi} &= \frac{x_{0}}{\left(\frac{v_{0}}{\omega}\right)} \\
\end{cases} \\
\begin{cases}
A        &= \sqrt{x_{0}^{2} + \left(\frac{v_{0}}{\omega}\right)^{2}}\\
\tan\phi &= \frac{x_{0}\omega}{v_{0}} \\
\end{cases} \\
}$$
### Pendolo semplice
![[Pendolo semplice.jpg]]
$\vec{F}_{tot} = \vec{P}+\vec{T} = m\vec{a}$
Introducendo i versori $\hat{u}_{R}$ e $\hat{u}_{T}$
Forza centripeta: $T-P_{R} = ma_{R}$
Forza di richiamo: $-P_{T} = ma_{T}$
Posizione di equilibrio stabile: $\theta = 0$
$a_{T} = L\alpha = L \frac{d^{2}\theta}{dt^{2}}$
$P_{T} = mg\sin\theta$
Piccole oscillazioni: $\theta<<1rad\implies\sin\theta\cong\theta$
$-mg\theta = mL\frac{d^{2}\theta}{dt^{2}} \implies \frac{d^{2}\theta}{dt^{2}} + \frac{g}{L}\theta = 0$
$\theta(t) = \theta_{A}\sin(\omega_{0}t+\phi)$
$\omega_{0}^{2} = \frac{g}{L}$; $T = 2\pi\sqrt{\frac{L}{g}}$
### Oscillatore armonico smorzato da una forza viscosa
![[Oscillatore armonico smorzato da una forza viscosa.jpg]]
Posizione a riposo della molla: $x=0$
$m\vec{a} = \vec{F}_{molla}+\vec{R}_{mezzo}$
$\vec{R}_{mezzo} = -b\vec{v}$
$m \frac{d^{2}x}{dt^{2}} = -kx-bv$
$\frac{d^{2}x}{dt^{2}} + \frac{b}{m} \frac{dx}{dt} + \frac{k}{m}x=0$
Coeficiente di smorzamento: $\gamma\equiv \frac{b}{2m}$
Pulsazione propria: $\omega_{0}^{2}\equiv \frac{k}{m}$

Eq. differenziale dell'**Oscillatore armonico smorzato**
$\frac{d^{2}x}{dt^{2}} + 2\gamma\frac{dx}{dt} + \omega_{0}^{2}x=0$
Soluzione di prova
$x(t) = e^{\alpha t}$
$\frac{dx}{dt} = \alpha e^{\alpha t}$
$\frac{d^{2}x}{dt^{2}} = \alpha^{2} e^{\alpha t}$
Sostituendo:
$\alpha^{2} e^{\alpha t} + 2\gamma\alpha e^{\alpha t} + 1\omega_{0}^{2}e^{\alpha t} = 0$
$e^{\alpha t}\left(\alpha^{2} + 2\gamma\alpha + 1\omega_{0}^{2}\right) = 0$
Quindi $x(t) = e^{\alpha t}$ è soluzione solo se $\alpha$ è tale che:
$\alpha^{2} + 2\gamma\alpha+\omega_{0}^{2} = 0$ (Equazione caratteristica)
$\alpha = -\gamma\pm\sqrt{\gamma^{2}-\omega_{0}^{2}}$
Ci sono 3 casi
#### Smorzamento Forte ($\gamma^{2}>\omega_{0}^{2}$)
$\gamma^{2}>\omega_{0}^{2} \implies$ $\alpha_{1}$ e $\alpha_{2}$ reali distinte
Soluzioni reali dell'equazione caratteristica:
$\alpha_{1} = -\gamma +\sqrt{\gamma^{2}-\omega_{0}^{2}} = -\gamma +\beta$
$\alpha_{2} =  -\gamma -\sqrt{\gamma^{2}-\omega_{0}^{2}} = -\gamma -\beta$
ove $\beta=\sqrt{\gamma^{2}-\omega_{0}^{2}}<\gamma \implies \alpha_{1},\alpha_{2}<0$ 

Soluzione generale
$x(t) = Ae^{\alpha_{1} t} + Be^{\alpha_{2} t} = e^{-\gamma t}(Ae^{\beta t} + Be^{-\beta t})$

```ad-note
$A$ e $B$ dipendono dalle condizioni iniziali ($x(0)$ e $v(0)$)
```

$x(t)$ decrescente esponanzialmente $\implies$ non ci sono oscillazioni
#### Smorzamento Critico ($\gamma^{2}=\omega_{0}^{2}$)
$\gamma^{2}=\omega_{0}^{2} \implies$ $\alpha_{1} = \alpha_{2}$ reali e coincidenti

Soluzioni reali dell'equazione caratteristica:
$\alpha_{1} = \alpha_{2} =  -\gamma$ 

Soluzione generale
$x(t) = e^{-\gamma t}(At+B)$

```ad-note
$A$ e $B$ dipendono dalle condizioni iniziali ($x(0)$ e $v(0)$)
```

$x(t)$ decrescente esponanzialmente $\implies$ non ci sono oscillazioni
#### Smorzamento Debole ($\gamma^{2}<\omega_{0}^{2}$)
$\gamma^{2}<\omega_{0}^{2} \implies$ $\alpha_{1}$ e $\alpha_{2}$ immaginarie coniugate

Soluzioni reali dell'equazione caratteristica:
$\alpha_{1} = -\gamma +i\sqrt{\omega_{0}^{2}-\gamma^{2}} = -\gamma +i\omega$
$\alpha_{2} =  -\gamma -i\sqrt{\omega_{0}^{2}-\gamma^{2}} = -\gamma -i\omega$
ove $\omega^{2} = \omega_{0}^{2}-\gamma^{2}$

Soluzione generale
$x(t) = a_{1}e^{\alpha_{1} t} + a_{2}e^{\alpha_{2} t} = e^{-\gamma t}(a_{1}e^{i\omega t} + a_{2}e^{-i\omega t})$

utilizzando la *Formula di Eulero*:
$e^{\pm i\omega t} = \cos\omega t \pm i\sin\omega t$
la soluzione può essere riscritta come:
$x(t) = Ae^{-\gamma t}\sin(\omega t+\phi)$

```ad-note
$A$ e $\phi$ dipendono dalle condizioni iniziali ($x(0)$ e $v(0)$)
```

$\omega = \sqrt{\omega_{0}^{2}-\gamma^{2}}<\omega_{0}$
Pseudo periodo: $T = \frac{2\pi}{\omega}$
##### Determinare $A$ e $\phi$
$A$ e $\phi$ reali tali che:
$$
\displaylines{
\begin{cases}
a_{1} + a_{2}    &=  2a  &= A\sin\phi \\
i(a_{1} - a_{2}) &= -2b &= A\cos\phi  \\
\end{cases} \implies 
\begin{cases}
A^{2}    &= (2a)^{2}+(-2b)^{2} \\
\tan\phi &= -\frac{a}{b}  \\
\end{cases} \\
f(t) = A\sin(\omega t +\phi) \\
x(t) = Ae^{-\gamma t}\sin(\omega t +\phi)
}
$$
### Oscillatore armonico forzato
Oscillazione pesistente dovuta ad un'applicazione di forza sinusuidale
$m \frac{d^{2}x}{dt^{2}} = -kx -bv +F_{0}\sin\omega t$
Pulsazione propria: $\omega_{0}^{2} = \frac{k}{m}$
Coeff. di smorzamento $\gamma = \frac{b}{2m}$

Eq. differenziale dell'***Oscillatore Armonico Forzato***
$\frac{d^{2}x}{dt^{2}} + 2\gamma \frac{dx}{dt}+ \omega_{0}^{2}x = \frac{F_{0}}{m}\sin\omega t$
Soluzione generale
$x(t) = A\sin(\omega t +\phi) +a_{1}e^{\alpha_{1}t} +a_{2}e^{\alpha_{2}t}$
con:
- $\alpha_{1}$ e $\alpha_{2}$ soluzioni dell'equazione caratteristica $\alpha^{2}+ 2\gamma\alpha + \omega_{0}^{2} = 0$
- $\alpha_{1}$ e $\alpha_{2}$ dipendenti dalle condizioni iniziali

Fenomeno **transitorio**: $a_{1}e^{\alpha_{1}t} +a_{2}e^{\alpha_{2}t}$
Soluzione **persistente**: $x(t) = A\sin(\omega t +\phi)$
$\omega =$ pulsazione della forza esterna
$A$ e $\phi =$  funzioni di $\omega$ (N.B.; non più dipendenti dalle condizioni iniziali)
$A$ e $\phi$ tali che:
$$
\displaylines{
\begin{cases}
(\omega_{0}^{2}-\omega^{2})A\cos\phi -2\gamma\omega A\sin\phi &= \frac{F_{0}}{m} \\
(\omega_{0}^{2}-\omega^{2})A\sin\phi +2\gamma\omega A\cos\phi &= 0                \\
\end{cases} \\ 
\\
A(\omega)  = \frac{\left(\frac{F_{0}}{m}\right)}{\sqrt{(\omega_{0}^{2}-\omega^{2})^{2}+(2\gamma\omega)^{2}}} \\
\tan\phi(\omega) = - \frac{2\gamma\omega}{\omega_{0}^{2}-\omega^{2}} \\
\\
\begin{matrix}
\omega<<\omega_{0} & A\approx \frac{F_{0}}{k}                    & \phi\approx0      \\
\omega=\omega_{0}  & A=       \frac{F_{0}}{(2m\gamma\omega_{0})} & \phi=\frac{\pi}{2} \\
\omega>>\omega_{0} & A\approx \frac{F_{0}}{m\omega^{2}}          & \phi\approx\pi      \\
\end{matrix}
}
$$
### Altro
- Oscillatore armonico semplice
- Energia cinetica e potenziale nei moti armonici semplici ($U(t) = \frac{1}{2}kx^{2} = \frac{1}{2}kA^{2}\sin^{2}(\omega t+\phi)$;  $K(t) = \frac{1}{2}mv^{2} = \frac{1}{2}mA^{2}\omega^{2}\cos^{2}(\omega t+\phi) = \frac{1}{2}kA^{2}\cos^{2}(\omega t+\phi)$; $E = U(t) + K(t) = \frac{1}{2}kA^{2}$)
- Risonanza
## Proprietà meccaniche dei fluidi
- Generalità sui fluidi
- Pressione
- Equilibrio statico di un fluido
- Legge di Stevino
- Principio di Pascal
- Vasi comunicanti
- Paradosso idrostatico
- Principio di Archimede
- Galleggianti
- Fluido ideale
- Regime stazionario
- Portata
- Teorema di Bernoulli
- Teorema di Torricelli
- Tubo di Venturi
- Tubo di Pitot
- Paradosso idrodinamico
- Effetti dinamici: moto in un condotto orizzontale curvo
- Attrito interno: Moto laminare (cenni)
$$$
