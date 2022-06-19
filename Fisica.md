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
- Corpo rigido
- Moto di un corpo rigido
- Equazione del moto di un corpo rotante
- Rotazioni rigide attorno ad un asse fisso in un sistema di riferimento inerziale
- Momento di inerzia rispetto ad un asse fisso
- Lavoro ed energia cinetica nel moto rotatorio
- Teorema di Huygens-Steiner
- Leggi di conservazione nel moto di un corpo rigido
- Moto rototraslatorio
- Moto di puro rotolamento
## Oscillazioni
- Oscillatore armonico semplice
- Sistema massa-molla: equazione del moto e soluzione
- Energia cinetica e potenziale nei moti armonici semplici
- Pendolo semplice
- Oscillatore armonico smorzato
- Oscillatore armonico smorzato
  - smorzamento forte
  - critico
  - smorzamento debole
- Oscillatore armonico forzato
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
