### Amdahl’s law

> Upper limit to the speed-up: $S_A(\infty) = \frac{1}{(1-p)}$.
>
> If $p$ is small, there is not much to gain from parallelization. Even for large $p$, there’s such a thing as too many units:

| p   | 2    | 4    | 100  | 200  | 400  | \infty |
| --- | ---- | ---- | ---- | ---- | ---- | ------ |
| 10% | 1.05 | 1.08 | 1.11 | 1.11 | 1.11 | 1.11   |
| 25% | 1.14 | 1.23 | 1.33 | 1.33 | 1.33 | 1.33   |
| 50% | 1.33 | 1.60 | 1.98 | 1.99 | 1.99 | 2.00   |
| 75% | 1.60 | 2.29 | 3.88 | 3.94 | 3.97 | 4.00   |
| 99% | 1.98 | 3.88 | 50.2 | 66.9 | 80.2 | 100.   |
> (Diminishing returns: doubling the number of units brings progressively less additional speed-up.)
>
> Assume total work can be decomposed into multiple parts p_1, p_2, ... p_r and each can be sped-up by s_1, s_2, ..., s_r. Total speed-up:

$$S = \frac{1}{\frac{p_1}{s_1} + \frac{p_2}{s_2} + ... + \frac{p_r}{s_r}}$$

> Should you focus where s_i is larger or where p_i is larger?
>
> Example: p_1 = 0.25, p_2 = 0.75, but s_1 = 20, s_2 = 5.

| From 1 | From 2 | From both |
| ------ | ------ | --------- |
| 1.31   | 2.5    | 6.15      |
> Focus on the larger part: better speed-up with less investment.

> Amdhal’s law focuses on maximum speed-up assuming constant work (strong scaling). How about more work in the same time (weak scaling)?
>
> Gustafson’s law: if a fraction p of the work can be sped up by a factor of s, then the total amount of work that can be done in the same time will be:

$$S_G = \frac{W(s)}{W_0} = 1 - p + sp$$

> Example: if 80% of the work can be sped up by a factor of 20, then in the same time you can do 0.2 + 20*0.8 = 16.2 times more work.
