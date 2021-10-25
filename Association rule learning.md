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

$$\mathrm{supp}(X)={\frac {|{(i,t)\in T:X\subseteq t}|}{|T|}}$$
```

```ad-def
title:Confidence
Confidence is an indication of how often the rule has been found to be true.

Confidence is defined as:

$$\mathrm {conf} (X\Rightarrow Y)=\mathrm {supp} (X\cup Y)/\mathrm {supp} (X)$$
```

```ad-def
title:Interest
!!!TODO!!!

$$\mathrm {int} (I \rightarrow j) = \mathrm {conf} (I \rightarrow j) - \mathrm {supp}$$
```

```ad-def
title:Lift
The *[lift](https://en.wikipedia.org/wiki/Lift_(data_mining) "Lift (data mining)")* of a rule is defined as:

{\displaystyle \mathrm {lift} (X\Rightarrow Y)={\frac {\mathrm {supp} (X\cup Y)}{\mathrm {supp} (X)\times \mathrm {supp} (Y)}}}![{\mathrm  {lift}}(X\Rightarrow Y)={\frac  {{\mathrm  {supp}}(X\cup Y)}{{\mathrm  {supp}}(X)\times {\mathrm  {supp}}(Y)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b6bfa25f817a13d911d1705766a5490d60d4f598)

or the ratio of the observed support to that expected if X and Y were [independent](https://en.wikipedia.org/wiki/Independence_(probability_theory) "Independence (probability theory)").

For example, the rule {\displaystyle {\mathrm {milk,bread} }\Rightarrow {\mathrm {butter} }}![{{\mathrm  {milk,bread}}}\Rightarrow {{\mathrm  {butter}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/31ebb0498a18c22794582ddd8c23e2e6394d6e45) has a lift of {\displaystyle {\frac {0.2}{0.4\times 0.4}}=1.25}![{\frac  {0.2}{0.4\times 0.4}}=1.25](https://wikimedia.org/api/rest_v1/media/math/render/svg/cc9a265b53d6b8b5328d1a2b9e7cd7742348d14a).

If the rule had a lift of 1, it would imply that the probability of occurrence of the antecedent and that of the consequent are independent of each other. When two events are independent of each other, no rule can be drawn involving those two events.

If the lift is > 1, that lets us know the degree to which those two occurrences are dependent on one another, and makes those rules potentially useful for predicting the consequent in future data sets.

If the lift is < 1, that lets us know the items are substitute to each other. This means that presence of one item has negative effect on presence of other item and vice versa.

The value of lift is that it considers both the support of the rule and the overall data set.[[3]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-:0-3>)
```

```ad-def
title:Conviction[[edit source](https://en.wikipedia.org/w/index.php?title=Association_rule_learning&action=edit&section=6 "Edit section: Conviction")]
The *conviction* of a rule is defined as {\displaystyle \mathrm {conv} (X\Rightarrow Y)={\frac {1-\mathrm {supp} (Y)}{1-\mathrm {conf} (X\Rightarrow Y)}}}![{\mathrm  {conv}}(X\Rightarrow Y)={\frac  {1-{\mathrm  {supp}}(Y)}{1-{\mathrm  {conf}}(X\Rightarrow Y)}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4c2228820d6a8cb5a84bd059d53764a6b9280386).[[6]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-brin-dynamic-itemset1-6>)

For example, the rule {\displaystyle {\mathrm {milk,bread} }\Rightarrow {\mathrm {butter} }}![{{\mathrm  {milk,bread}}}\Rightarrow {{\mathrm  {butter}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/31ebb0498a18c22794582ddd8c23e2e6394d6e45) has a conviction of {\displaystyle {\frac {1-0.4}{1-0.5}}=1.2}![\frac{1 - 0.4}{1 - 0.5} = 1.2 ](https://wikimedia.org/api/rest_v1/media/math/render/svg/bff27f4903bd267d0f956a631980450f49cd4d73), and can be interpreted as the ratio of the expected frequency that X occurs without Y (that is to say, the frequency that the rule makes an incorrect prediction) if X and Y were independent divided by the observed frequency of incorrect predictions. In this example, the conviction value of 1.2 shows that the rule {\displaystyle {\mathrm {milk,bread} }\Rightarrow {\mathrm {butter} }}![{{\mathrm  {milk,bread}}}\Rightarrow {{\mathrm  {butter}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/31ebb0498a18c22794582ddd8c23e2e6394d6e45) would be incorrect 20% more often (1.2 times as often) if the association between X and Y was purely random chance.
```

```ad-def
title:Alternative measures of interestingness[[edit source](https://en.wikipedia.org/w/index.php?title=Association_rule_learning&action=edit&section=7 "Edit section: Alternative measures of interestingness")]
In addition to confidence, other measures of *interestingness* for rules have been proposed. Some popular measures are:

- All-confidence[[7]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-allconfidence-7>)
- Collective strength[[8]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-collectivestrength-8>)
- Leverage[[9]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-leverage-9>)

Several more measures are presented and compared by Tan et al.[[10]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-measurescomp-10>) and by Hahsler.[[4]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-michael.hahsler.net-4>) Looking for techniques that can model what the user has known (and using these models as interestingness measures) is currently an active research trend under the name of "Subjective Interestingness."

```
