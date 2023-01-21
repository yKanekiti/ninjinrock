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
ポアソン分布の確率母関数を求めると, 
```math
\begin{align*}
G(s) = E[s^X] &= \displaystyle\sum^\infty_{x=0} s^x\frac{\lambda^x}{x!} e^{-\lambda}\\
&= e^{s\lambda -\lambda} \displaystyle\sum^\infty_{x=0} \frac{(s\lambda)^x}{x!}e^{-s\lambda} \\
&= e^{s\lambda -\lambda}
\end{align*}
```
となるので, $`G(s)`$ を2階まで微分して
```math
\begin{align*}
G^\prime(s) &= \lambda e^{s\lambda-\lambda} \\
G^{\prime\prime}(s) &= \lambda^2 e^{s\lambda-\lambda}
\end{align*}
```
となる. よって, 確率母関数と期待値および分散の関係から, 
```math
\begin{align*}
E[X] &= G^\prime(1) = \lambda \\
Var[X] &= G^{\prime\prime}(1) + G^\prime(1) - G^\prime(1)^2 = \lambda
\end{align*}
```
が得られる.

## 負の二項分布

***Proposition***  
$`X \sim NB(r, p)`$とすると, 次が成立する.
```math
\begin{align*}
E[X] &= 
Var[X] &= 
\end{align*}
```
*&lt;proof&gt;*  
まず $`q:=1-p`$ として $`(1-q)^{-r}`$ をTaylor展開してみると, 
```math
\begin{align*}
(1-q)^{-r} &= 1 + rq + \frac{r(r+1)}{2!}q^2 + \dots \\
           &= \displaystyle\sum^\infty_{k=0} \binom{r+k-1}{k} q^k
\end{align*}
```
が得られるので, これを用いるとポアソン分布の確率母関数 $`G(s)`$ は

```math
\begin{align*}
G(s) &= \displaystyle\sum^\infty_{x=0} s^x \binom{r+x-1}{x}(1-p)^xp^r \\
     &= \displaystyle\sum^\infty_{x=0} \binom{r+x-1}{x} (qs)^xp^r \\
     &= (1-q)^{-r} p^r \\
     &= (1-\frac{s-1}{p}q)^{-r}
\end{align*}
```
となる. $` G(s)`$ を2階まで微分は
```math
\begin{align*}
G^\prime(s) &= \frac{q}{p}r (1-\frac{s-1}{p}q)^{-r-1}\\
G^{\prime\prime}(s) &= \frac{q^2}{p^2}r(r+1) (1-\frac{s-1}{p}q)^{-r-2}\\
\end{align*}
```
であるから, 期待値と分散は
```math
\begin{align*}
E[X] &= G^\prime(1) = \frac{q}{p}r = \frac{1-p}{p}r \\
Var[X] &= G^{\prime\prime}(1) + G^\prime(1) - G^\prime(1)^2 
        = \frac{q^2}{p^2}r + \frac{q}{p}r = \frac{1-p}{p^2}r
\end{align*}
```
となる. ちなみに, $`r=1`$ とすれば幾何分布の期待値と分散が得られる. 

## 超幾何分布

省略（有限修正のはなし）

## 一様分布

## 正規分布
正規分布と言えば大抵は期待値と分散がそもそも与えられてるものだが, ここでは確率密度関数から直接求めてみる


## ガンマ分布

## 指数分布

## ベータ分布