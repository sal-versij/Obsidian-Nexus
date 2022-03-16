# Metodi Matematici e Statistici
## Spazi campionati ed eventi
!def esperimento
Chiameremo esperimenti i fenomeni aleatori di cui ci occupiamo e chiameremo esiti i risultati di tali esperimenti
def!
!def spazio campionario
Dato un esperimento, è detto spazio campionario l'insieme di tutti gli esiti possibili

$\Omega$: generico spazio campionario
$\omega$: generici esiti

Risultati dell'esperimento: insieme
Esiti dell'esperimento: elementi dell'insieme
def!
!def
eventi sono sottoinsiemi di $\Omega$

$\Omega$: Evento certo
$\emptyset$: Evento impossibile
def!
!def
Due eventi di dicono mutuamente esclusivi se
E cap F = emptyset dove E subseteq Omega, F subseteq Omega
def!
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

```ad-demonstration
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
&Egrave; uscita testa per la prima volta all'$n$-esimo lancio
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
!example
Dato $\Omega$ la più piccola $\sigma$-algebra è $\mathscr{F} = \{\emptyset,\Omega\}$, la più estesa è $\mathscr{P}(\Omega)$
example!

!def

def!