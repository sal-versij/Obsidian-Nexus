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
| ### Altro             |            |             |       |

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
### Altro
- Leggi della forza gravitazionale ($F_{12} = F_{21} = G \frac{m_{1}m_{2}}{r^{2}}$)
- forza peso ($F=mg$)
- forza elastica ($F = kx$)
- Reazioni vincolari
- Tensione dei fili
- Diagramma del corpo libero
- Moto lungo un piano inclinato liscio
- Forza di attrito radente
- Moto lungo un piano inclinato scabro
- Moti circolari: Forze centripete
- Quantità di moto
- Impulso
- Momento angolare
- Momento meccanico
## Conservazione dell'energia
- Generalità sui principi di conservazione
- Principio di conservazione dell’energia
- Lavoro
- Energia cinetica
- Teorema delle forze vive
- Forze conservative
- Energia potenziale
- Calcolo di energia potenziale
- Conservazione dell’energia meccanica
- Forze non conservative
- Potenza
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
## Dinamica dei sistemi di punti materiali
- Sistemi di punti.
  - Forze interne
  - forze esterne
- Centro di massa
- Moto del centro di massa
- Conservazione della quantità di moto
- Urti tra punti materiali
  - elastico
  - anelastico
  - completamente anelastico
- Urto elastico frontale
- Momento angolare
- Momento meccanico
- Teorema del momento angolare
- Conservazione del momento angolare
## Dinamica del corpo rigido
- Corpo rigido
- Moto di un corpo rigido
- Equazione del moto di un corpo rotante
- Rotazioni rigide attorno ad un asse fisso in un sistema di riferimento inerziale
- Momento di inerzia rispetto ad un asse fisso
- Lavoro ed energia cinetica nel moto rotatorio-
- Teorema di HuygensSteiner
- Leggi di conservazione nel moto di un corpo rigido
- Moto rototraslatorio
- Moto di puro rotolamento
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
