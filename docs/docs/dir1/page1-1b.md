# いろんな分布

LaTexを思い出すために試しに書いてみる

## ベルヌーイ分布

確率変数$`X`$が実数$`0\leq p \leq 1`$に対して確率関数

```math
\begin{align*}
P(X=1) &= p \\
P(X=0) &= 1-p
\end{align*}
```

で与えられるとき, $`X`$はベルヌーイ分布$`B(1, p)`$に従うという.
$`X`$の期待値および分散は次の通り：

```math
\begin{align*}
E[X] &= p \\
Var[X] &= p(1-p)
\end{align*}
```

## 二項分布

$`n`$個の確率変数$`X_1, \ldots, X_n `$がベルヌーイ分布に従うとき, $`X=X_1 + \ldots + X_n`$は二項分布$`B(n, p)`$に従うという.
このとき, $`X`$の確率関数および期待値、分散は次の通り：

```math
\begin{align*}
P(X=k) &= \binom{n}{k}p^k(1-p)^{n-k} \\
E[X] &= np \\
Var[X] &= np(1-p)
\end{align*}
```

