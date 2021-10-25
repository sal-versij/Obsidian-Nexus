# Association rule learning
Following the original definition by [[Agrawal]], [[Imieliński]], [[Swami]] the problem of association rule mining is defined as:

Let $I=\{i_{1},i_{2},\ldots ,i_{n}\}$ be a set of $n$ binary attributes called *items*.

Let $D={t_{1},t_{2},\ldots ,t_{m}}$ be a set of transactions called the *database*.

Each *transaction* in $D$ has a unique transaction ID and contains a subset of the items in {\displaystyle I}![I](https://wikimedia.org/api/rest_v1/media/math/render/svg/535ea7fc4134a31cbe2251d9d3511374bc41be9f).

A *rule* is defined as an implication of the form:

{\displaystyle X\Rightarrow Y}![X\Rightarrow Y](https://wikimedia.org/api/rest_v1/media/math/render/svg/59d16d722c8c8fe129384ebc3687884c0b348eef), where {\displaystyle X,Y\subseteq I}![X,Y\subseteq I](https://wikimedia.org/api/rest_v1/media/math/render/svg/0f5aabe40ab2b554c2f23eda221556db5868959f).

In Agrawal, Imieliński, Swami[[2]](<https://en.wikipedia.org/wiki/Association_rule_learning#cite_note-mining-2>) a *rule* is defined only between a set and a single item, {\displaystyle X\Rightarrow i_{j}}![{\displaystyle X\Rightarrow i_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/10f03f06761df5fb43a17b2dac73ceb9c1ef1039) for {\displaystyle i_{j}\in I}![{\displaystyle i_{j}\in I}](https://wikimedia.org/api/rest_v1/media/math/render/svg/313bb7442e84075026469b21609039a11449d35f).

Every rule is composed by two different sets of items, also known as *itemsets*, {\displaystyle X}![X](https://wikimedia.org/api/rest_v1/media/math/render/svg/68baa052181f707c662844a465bfeeb135e82bab) and {\displaystyle Y}![Y](https://wikimedia.org/api/rest_v1/media/math/render/svg/961d67d6b454b4df2301ac571808a3538b3a6d3f), where {\displaystyle X}![X](https://wikimedia.org/api/rest_v1/media/math/render/svg/68baa052181f707c662844a465bfeeb135e82bab) is called *antecedent* or left-hand-side (LHS) and {\displaystyle Y}![Y](https://wikimedia.org/api/rest_v1/media/math/render/svg/961d67d6b454b4df2301ac571808a3538b3a6d3f) *consequent* or right-hand-side (RHS).

To illustrate the concepts, we use a small example from the supermarket domain. The set of items is {\displaystyle I={\mathrm {milk,bread,butter,beer,diapers} }}![I={{\mathrm  {milk,bread,butter,beer,diapers}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/debe2b7bb5feb6413f25afaf2816e4dad7763c96) and in the table is shown a small database containing the items, where, in each entry, the value 1 means the presence of the item in the corresponding transaction, and the value 0 represents the absence of an item in that transaction.

An example rule for the supermarket could be {\displaystyle {\mathrm {butter,bread} }\Rightarrow {\mathrm {milk} }}![{{\mathrm  {butter,bread}}}\Rightarrow {{\mathrm  {milk}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3141048979b977982202dbf7a80596f8a6b1177e) meaning that if butter and bread are bought, customers also buy milk.

Note: this example is extremely small. In practical applications, a rule needs a support of several hundred transactions before it can be considered statistically significant,[*[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed "Wikipedia:Citation needed")*] and datasets often contain thousands or millions of transactions.
