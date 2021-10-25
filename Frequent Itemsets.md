# Frequent Itemsets
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
DataSet

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

itemset|support
-|-
$\{b\}$|6
$\{c\}$|5
$\{j\}$|4
$\{m\}$|5
$\{p\}$|2
$\{b,c\}$|4
$\{b,j\}$|2
$\{b,m\}$|4
$\{b,p\}$|1
$\{c,j\}$|3
$\{c,m\}$|2
$\{c,p\}$|0
$\{j,m\}$|2
$\{j,p\}$|1
$\{m,p\}$|2
$\{b,c,j\}$|2

$\{b,c,m\}$|2

$\{b,c,p\}$|0

$\{b,j,m\}$|1

$\{b,j,p\}$|0

$\{b,m,p\}$|1

$\{c,j,m\}$|1

$\{c,j,p\}$|0

$\{c,m,p\}$|0

$\{j,m,p\}$|1

$\{b,c,j,m\}$|1

$\{b,c,j,p\}$|0

$\{b,c,m,p\}$|0

$\{b,j,m,p\}$|0

$\{c,j,m,p\}$|0

$\{b,c,j,m,p\}$|0