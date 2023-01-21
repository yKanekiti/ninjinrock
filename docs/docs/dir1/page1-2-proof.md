# 期待値・分散の証明

## 二項分布

***Proposition***  
$`X\sim B(n,p)`$ とすると, 次が成立する. 
```math
\begin{align*}
E[X] &= np \\
Var[X] &= np(1-p)
\end{align*}
```
*&lt;proof&gt;*  
成功確率 $`p`$ の $`n`$ 個の独立なベルヌーイ試行 $`X_1, \ldots, X_n`$ によって $`X`$ を
```math
X = X_1 + \dots + X_n
```
と表すと, 各 $`i`$ に対して
```math
\begin{align*}
E[X_i] &= p \\
Var[X_i] &= E[X_i^2] - E[X_i]^2 = p - p^2 = p(1-p)
\end{align*}
```
となる. 期待値の線形性と, および各 $`X_i`$ は独立であることから
```math
\begin{align*}
E[X] &= E[X_1] + \ldots + E[X_n] = np\\
Var[X] &= Var[X_1] + \dots + Var[X_n] = np(1-p)
\end{align*}
```
が得られる.

## ポアソン分布

***Proposition*** 
$` X \sim Po(\lambda) `$ とすると, 次が成立する. 
```math
\begin{align*}
E[X] &= \lambda \\
Var[X] &=  \lambda
\end{align*}
```
*&lt;proof&gt;*  