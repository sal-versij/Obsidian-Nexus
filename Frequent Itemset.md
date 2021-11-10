# Frequent Itemset
In the [[Market-basket]] analysis a curious problem is finding the **frequent itemsets**

```ad-def
title:Frequence 
The concept of frequence is based on the threshold $\sigma$

if the support of an itemset is greater than $\sigma$ then it's frequent
```

```ad-def
title: Support
The support of an itemset is the number of baskets where is found the itemset
```
## Example
```ad-def
collapse:true
title:DataSet
$$
\begin{gather}
B_1 = \{ m,c,b \} \newline
B_2 = \{ m,p,j \} \newline
B_3 = \{ m,b \} \newline
B_4 = \{ c,j \} \newline
B_5 = \{ m,p,b \} \newline
B_6 = \{ m,c,b,j \} \newline
B_7 = \{ c,b,j \} \newline
B_8 = \{ b,c \} \newline
\end{gather}
$$
```

> Soglia  $\sigma=2$

| itemset | support |  itemset  | support |   itemset   | support |    itemset    | support |     itemset     | support |
| :-----: | :-----: | :-------: | :-----: | :---------: | :-----: | :-----------: | :-----: | :-------------: | :-----: |
| $\{b\}$ |  **6**  | $\{b,c\}$ |  **4**  | $\{b,c,j\}$ |  **2**  | $\{b,c,j,m\}$ |    1    | $\{b,c,j,m,p\}$ |    0    |
| $\{c\}$ |  **5**  | $\{b,j\}$ |  **2**  | $\{b,c,m\}$ |  **2**  | $\{b,c,j,p\}$ |    0    |                 |         |
| $\{j\}$ |  **4**  | $\{b,m\}$ |  **4**  | $\{b,c,p\}$ |    0    | $\{b,c,m,p\}$ |    0    |                 |         |
| $\{m\}$ |  **5**  | $\{b,p\}$ |    1    | $\{b,j,m\}$ |    1    | $\{b,j,m,p\}$ |    0    |                 |         |
| $\{p\}$ |  **2**  | $\{c,j\}$ |  **3**  | $\{b,j,p\}$ |    0    | $\{c,j,m,p\}$ |    0    |                 |         |
|         |         | $\{c,m\}$ |  **2**  | $\{b,m,p\}$ |    1    |               |         |                 |         |
|         |         | $\{c,p\}$ |    0    | $\{c,j,m\}$ |    1    |               |         |                 |         |
|         |         | $\{j,m\}$ |  **2**  | $\{c,j,p\}$ |    0    |               |         |                 |         |
|         |         | $\{j,p\}$ |    1    | $\{c,m,p\}$ |    0    |               |         |                 |         |
|         |         | $\{m,p\}$ |  **2**  | $\{j,m,p\}$ |    1    |               |         |                 |         |
