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
となる. 期待値の線形性と各 $`X_i`$ が独立であることから
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
E[X] &= \frac{1-p}{p}r \\
Var[X] &= \frac{1-p}{p^2}r
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
***Proposition***  
確率変数 $`X`$ が次の密度関数を持つ分布に従うとする: 
```math
f(x) = \frac{1}{\sqrt{2\pi\sigma^2}}\exp\{-\frac{(x-\mu)^2}{2\sigma^2}\}
```
このとき, 次が成立する.
```math
\begin{align*}
E[X] &= \mu \\
Var[X] &= \sigma^2
\end{align*}
```
*&lt;proof&gt;*  
まず, $`z`$ の関数
```math
\phi (z) = \frac{1}{\sqrt{2\pi}}\exp( -\frac{z^2}{2})
```
について, 次の2つの等式が成り立つことを示す： 
```math
\begin{align}
\int^\infty_{-\infty} z\phi(z) dz = 0 \\
\int^\infty_{-\infty} z^2\phi(z) dz = 1
\end{align}
```
(1)については被積分関数が奇関数なので明らか.  
(2)は $`\phi^\prime(z) = -z\phi(z)`$ に注意すると, 
```math
\begin{align*}
\int^\infty_{-\infty} z^2\phi(z) dz &= -\int^\infty_{-\infty}z\phi^\prime(z)dz \\
&= -\big[z\phi(z)\big]^\infty_{-\infty} + \int^\infty_{-\infty}\phi(z) dz \\
&= 1 
\end{align*}
```
となるのでOK.  

以上より, $`f(x)`$ の期待値 $`E[X]`$ および分散 $`Var[X]`$ は
```math
\begin{align*}
z &= \frac{x-\mu}{\sigma} \\
f(x) &= \frac{1}{\sigma}\phi(z)
\end{align*}
```
とおけば次のように求められる：
```math
\begin{align*}
E[X] &= \int^\infty_{-\infty}xf(x)dx = \int^\infty_{-\infty}(\sigma z + \mu)\phi(z)dz = \mu \\
Var[X] &= \int^\infty_{-\infty}(x-\mu)^2f(x)dx = \sigma^2 \int^\infty_{-\infty} z^2\phi(z)dz = \sigma^2
\end{align*}
```
## ガンマ分布

## 指数分布

## ベータ分布