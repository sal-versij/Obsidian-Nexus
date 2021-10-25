# Association rule learning
Following the original definition by [[Agrawal]], [[Imieliński]], [[Swami]] the problem of association rule mining is defined as:

Let $I=\{i_{1},i_{2},\ldots ,i_{n}\}$ be a set of $n$ binary attributes called *items*.

Let $D={t_{1},t_{2},\ldots ,t_{m}}$ be a set of transactions called the *database*.

Each *transaction* in $D$ has a unique transaction ID and contains a subset of the items in $I$.

A *rule* is defined as an implication of the form:

$X\rightarrow Y$, where $X,Y\subseteq I$.

In [[Agrawal]], [[Imieliński]], [[Swami]] a *rule* is defined only between a set and a single item, $X\rightarrow i_{j}$ for $i_{j}\in I$.

```ad-note
collapse:true
Every rule is composed by two different sets of items, also known as *itemsets*, $X$ and $Y$, where $X$ is called *antecedent* or left-hand-side (LHS) and $Y$ *consequent* or right-hand-side (RHS).
```
## Useful Concepts
> Let $X,Y$ be itemsets, $X\Rightarrow Y$ an association rule and $T$ a set of transactions of a given database.

```ad-def
title:Support
Support is an indication of how frequently the itemset appears in the dataset.

$$\mathrm{Supp}(X)={\frac {|{(i,t)\in T:X\subseteq t}|}{|T|}}$$
```

```ad-def
title:Confidence
Confidence is an indication of how often the rule has been found to be true.

Confidence is defined as:

$$\mathrm {Conf} (X\Rightarrow Y)=\mathrm {Supp} (X\cup Y)/\mathrm {Supp} (X)$$
```

```ad-def
title:Interest
!!!TODO!!!

$$\mathrm{Int}(I \rightarrow j) = \mathrm{Conf}(I \rightarrow j) - \frac{\mathrm{Supp}(j)}{N}$$

where $N$ is the number of baskets
```

```ad-def
title:Lift
The lift(see [[Lift (data mining)]]) of a rule is defined as:

$$\mathrm{Lift}(X\Rightarrow Y)={\frac {\mathrm {Supp} (X\cup Y)}{\mathrm {Supp} (X)\times \mathrm {Supp} (Y)}}$$

or the ratio of the observed support to that expected if X and Y were independent.

If the rule had a lift of 1, it would imply that the probability of occurrence of the antecedent and that of the consequent are independent of each other. When two events are independent of each other, no rule can be drawn involving those two events.

If the lift is > 1, that lets us know the degree to which those two occurrences are dependent on one another, and makes those rules potentially useful for predicting the consequent in future data sets.

If the lift is < 1, that lets us know the items are substitute to each other. This means that presence of one item has negative effect on presence of other item and vice versa.
```

```ad-def
title:Conviction
The *conviction* of a rule is defined as 
$$\mathrm {Conv} (X\Rightarrow Y)={\frac {1-\mathrm {Supp} (Y)}{1-\mathrm {Conf} (X\Rightarrow Y)}}$$

can be defined as the ratio of the expected frequency that $X$ occurs without $Y$ (that is to say, the frequency that the rule makes an incorrect prediction) if $X$ and $Y$ were independent divided by the observed frequency of incorrect predictions.
```

```ad-note
copllapse:true
title:Alternative measures of interestingness
In addition to confidence, other measures of *interestingness* for rules have been proposed. Some popular measures are:

- [All-confidence](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-allconfidence-7>)
- [Collective strength](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-collectivestrength-8>)
- [Leverage](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-leverage-9>)

Several more measures are presented and compared by:
- [Tan et al.](https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-measurescomp-10>)
- [Hahsler](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-michael.hahsler.net-4>) Looking for techniques 
that can model what the user has known (and using these models as interestingness measures) is currently an active research trend under the name of "[[Subjective Interestingness]]".

```

## References
[[Maximal and Closed Frequent Items]]
