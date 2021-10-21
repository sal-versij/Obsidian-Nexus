# Insieme degli eventi $\mathscr{F}$
```ad-def
> Una $\sigma$-algebra che rispetti i seguenti assiomi

1. $\Omega\in\mathscr{F}$
2. $E\in\mathscr{F} \implies \bar{E}\in\mathscr{F}$
3. $E,F\in\mathscr{F} \implies E\cup F\in\mathscr{F}$
```
## Osservazioni
- > $E,F\in\mathscr{F} \implies E\cap F\in\mathscr{F}$
  $$
  \begin{gather}
  E,F\in\mathscr{F} \implies 
  \bar{E},\bar{F}\in\mathscr{F} \implies \\
  \bar{E}\cup\bar{F}\in\mathscr{F} \implies 
  \bar{\bar{E}\cup\bar{F}\in\mathscr{F}} \implies \\
  E\cap F\in\mathscr{F}
  \end{gather}
  $$
- > $\mathscr{F}\subseteq P(\Omega)$
