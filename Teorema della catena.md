# Teorema della catena
Dati $n$ eventi $E_1,E_2,\ldots E_n$ tale che $P[E_1\cap E_2 \cap \ldots \cap E_n]\gt0$, si ha:
$$
\begin{gather}
P[E_1\cap E_2 \cap \ldots \cap E_n] = \newline
P[E_1] \cdot
P[E_2|E_1] \cdot
P[E_3|E_1\cap E_2] \cdot
P[E_4|E_1\cap E_2\cap E_3] \cdot
\ldots \cdot
P[E_n|E_1\cap E_2 \cap \dots \cap E_{n-1}]
\end{gather}
$$