### Amdahl’s law

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
