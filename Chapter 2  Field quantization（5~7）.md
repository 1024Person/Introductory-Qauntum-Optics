# Chapter 2  Field quantization

## 2.5 Thermal fields

关于热场的定义，感觉就是在黑体中和腔壁到达热平衡的单模场。

热场中，处于$n$能级的概率$P_n$满足
$$
P_n = \frac{\exp\left(-E_n/k_BT\right)}{\sum_n\exp\left(-E_n/k_BT\right)}
$$
下面呢，引入密度算符
$$
\hat\rho_{Th} = \frac{\exp\left(-\hat H/k_BT\right)}{\Tr\left[\exp\left(-\hat H/k_BT\right)\right]}
$$

> 通过将基矢分别作用在这个密度算符上并且结合上面出现的概率分布，就能明白为什么密度算符会这么定义了。

配分函数
$$
\begin{aligned}
Z &= \Tr\left[\exp\left(-\hat H/k_BT\right)\right]\\
&=\sum_{n=0}^\infty\langle n|\exp\left(-\hat H/k_BT\right)|n\rangle\\
&=\sum_{n=0}^\infty\exp\left(-E_n/k_BT\right)\\

\end{aligned}
$$
将$E_n=\hbar \omega(n+\frac12)$带入上式可得
$$
Z=\exp\left(-\frac{\hbar\omega}{2k_BT}\right)\sum_{n=0}^\infty \exp\left(-n\hbar\omega/k_BT\right)
$$
其中的求和$\sum_{n=0}^\infty \exp\left(-n\hbar\omega/k_BT\right)$是几何级数，所以
$$
\begin{aligned}
Z&=\exp\left(-\frac{\hbar\omega}{2k_BT}\right)\frac{1}{1-\exp\left(-\hbar\omega/k_BT\right)}\\
&=\frac{\exp\left(-\hbar\omega/2k_BT\right)}{1-\exp\left(-\hbar\omega/k_BT\right)}
\end{aligned}
$$
显而易见
$$
P_n &= \langle n|\hat\rho_{Th}|n\rangle=\frac1Z\langle n|\exp\left(-\hat H/k_BT\right)|n\rangle=\frac{\exp\left(-E_n/k_BT\right)}{Z}\\
$$
因此密度算符也可以写成
$$
\begin{aligned}
\hat \rho_{Th} &=\sum_{n'=0}^{\infty}\sum_{n=0}^\infty|n'\rangle\langle n'|\hat\rho_{Th}|n\rangle\langle n|\\
&=\frac1Z\sum_{n'=0}^\infty\sum_{n=0}^\infty\exp\left(-E_n/k_BT\right)\delta_{n'n}|n'\rangle\langle n|\\
&=\frac1Z\sum_{n=0}^\infty\exp\left(-E_n/k_BT\right)|n\rangle\langle n|\\
&=\sum_{n=0}^\infty P_n|n\rangle\langle n|
\end{aligned}
$$
光场的平均光子数
$$
\begin{aligned}
\bar n &= \Tr\left[\hat n\hat \rho\right]\\
&=\sum_{n=0}^\infty\langle n|\hat n\hat \rho|n\rangle\\
&=\sum_{n=0}^\infty\langle n|\hat n\sum_{n'=0}^\infty P_{n'}|n'\rangle\underbrace{\langle n'|n\rangle}_{\delta_{n'n}}\\
&=\sum_{n=0}^\infty P_n\langle n|\hat n |n\rangle\\
&=\frac{1}{Z}\sum_{n=0}^\infty n \exp\left(-E_n/k_BT\right)\\
&=\frac{\exp\left(-\hbar\omega/2k_BT\right)}{Z}\sum_{n=0}^\infty n\exp\left(-n\hbar\omega/k_BT\right)
\end{aligned}
$$
其中，$\sum_{n=0}^\infty n\exp\left(-n\hbar\omega/k_BT\right)$这个求和也是一个比较特殊的求和，我们也可以向几何级数上靠，我们取$x=\hbar\omega/k_BT$，那么
$$
\begin{aligned}
\sum_{n=0}^\infty n\exp\left(-n\hbar\omega/k_BT\right)&=\sum_{n=0}^\infty n\exp\left(-nx\right)\\
&=-\frac{d}{dx}\sum_{n=0}^\infty\exp\left(-nx\right)\\
&=-\frac{d}{dx}\frac{1}{1-\exp\left(-x\right)}\\
&=-\frac{1}{\left[1-\exp\left(-x\right)\right]^2}\left[-\exp\left(-x\right)\right]\\
&=\frac{\exp\left(-x\right)}{\left[1-\exp\left(-x\right)\right]^2}
\end{aligned}
$$
因此，平均粒子数
$$
\begin{aligned}
\bar n &= \frac{\exp\left(-x/2\right)}{Z}\frac{\exp\left(-x\right)}{\left[1-\exp\left(-x\right)\right]^2}\\
&=\frac{\exp\left(-3x/2\right)}{Z\left[1-\exp\left(-x\right)\right]^2}\\
&=\frac{1-\exp\left(-\hbar\omega/k_BT\right)}{\exp\left(-\hbar\omega/2k_BT\right)}\frac{\exp\left(-3\hbar \omega/2k_BT\right)}{\left[1-\exp\left(-\hbar\omega/k_BT\right)\right]^2}\\
&=\frac{\exp\left(-\hbar\omega/k_BT\right)}{1-\exp\left(-\hbar\omega/k_BT\right)}\\
&=\frac{1}{\exp\left(\hbar\omega/k_BT\right)-1}
\end{aligned}
$$

> 下面的公式是论文中给的说实话，我没看出来这个式子是怎么来的，这个约等于又有是什么，
> $$
> \bar n\approx
> \begin{cases}
> k_BT/\hbar\omega ,\quad k_BT\gg\hbar\omega\\
> \hbar\omega/k_BT,\quad k_BT\ll \hbar\omega
> \end{cases}
> $$
> 上面的约等于”$\approx$“应该是使用泰勒级数，只展开到了一阶，从而取了近似，所以是约等于，但是就算是这样也不应该是上面的形式
> $$
> \bar n \approx k_BT/\hbar\omega 
> $$
> 无论$k_BT$和$\hbar\omega$的大小关系如何。

通过$\bar n$的表达式，我们可以得到
$$
\exp\left(-\hbar \omega/k_BT\right)=\frac{\bar n }{1+\bar n}
$$
代回到$P_n$的表达式中
$$
\begin{aligned}
P_n&=\frac{\exp\left(-E_n/k_BT\right)}{Z}\\
&=\exp\left(-\hbar\omega/2k_BT\right)\exp\left(-n\hbar\omega/k_BT\right)\frac{1-\exp\left(-\hbar\omega/k_BT\right)}{\exp\left(-\hbar\omega/2k_BT\right)}\\
&=\exp\left(-n\hbar\omega/k_BT\right)-\exp\left[-(n+1)\hbar\omega/k_BT\right]\\
&=\left[\exp\left(-\hbar\omega/k_BT\right)\right]^n-\left[\exp\left(-\hbar\omega/k_BT\right)\right]^{(n+1)}\\
&=\left[\frac{\bar n}{1+\bar n}\right]^n-\left[\frac{\bar n}{1+\bar n}\right]^{(n+1)}\\
&=\left[\frac{\bar n}{1+\bar n}\right]^n\left(1-\frac{\bar n}{1+\bar n}\right)\\
&=\left[\frac{\bar n}{1+\bar n}\right]^n\frac{1}{1-\bar n}\\
&=\frac{\bar n^n}{\left(1-\bar n\right)^{n+1}}
\end{aligned}
$$
也就是说，**每个能级上占据的光子数既和当前能级的数有关，又和平均光子数有关。**下面展示取不同的平均光子数时，布局数的分布。

通过观察上图，可以发现，$P_n$随着$n$的增大而不断减小。



下面计算数算符$\hat n$的涨落
$$
\langle \left(\Delta n\right)^2\rangle=\langle \hat n^2\rangle - \langle \hat n\rangle^2
$$
显然$\langle \hat n\rangle = \bar n$，而
$$
\begin{aligned}
\langle \hat n^2\rangle &= \Tr\left[\hat n^2\hat \rho\right]\\
&=\sum_{n=0}^\infty\langle n|\hat n^2\sum_{m=0}^\infty P_{m}|m\rangle\underbrace{\langle m|n\rangle}_{\delta_{nm}}\\
&=\sum_{n=0}^\infty P_n\langle n|\hat n^2|n\rangle\\
&=\frac{\exp\left(-\hbar \omega/2k_BT\right)}{Z}\sum_{n=0}^\infty  n ^2\exp\left(-n\hbar\omega/k_BT\right)
\end{aligned}
$$
这个求和照样可以换成几何级数
$$
\frac{d^2}{dx^2}\sum_{n=0}^\infty\exp(-nx)=\frac{d^2}{dx^2}\frac{1}{1-\exp\left(-x\right)}=\frac{\left[\exp\left(x\right)+1\right]\exp\left(x\right)}{\left[\exp\left(x\right)-1\right]^3}
$$
然后，我们将$\exp\left(-x\right) = \frac{\bar n}{1+\bar n}$带入可得
$$
\langle \hat n^2\rangle =2\bar n^2+\bar n
$$

> 中间的具体推导过程太过复杂，用机器算的，参考[c2s5.md](./推导过程/c2s5.md)第一节

那么平均光子数的涨落为
$$
\left\langle \left(\Delta n\right)^2\right\rangle=\bar n^2+\bar n
$$
所以，
$$
\Delta n=\left\langle \left(\Delta n\right)^2\right\rangle^{1/2}=\left(\bar n^2+\bar n\right)^{1/2}
$$
然后，整理之后我们用泰勒级数进行展开（这其中用到了一个条件$\bar n \gg 1$，但是不知道具体是怎么用的，感觉不用也可以呀，但是用也只能用在约等于哪里）
$$
\Delta n = \bar n\left(1+\frac{1}{\bar n}\right)^{1/2}\approx\bar n(1+\frac{1}{2\bar n})=\bar n + \frac{1}{2}
$$
当$n\ll 1$时，上式又变成了
$$
\Delta n = \sqrt{\bar n}\left(1+\bar n\right)^{1/2}\approx\sqrt{\bar n}\left(1+\frac{\bar n}{2}\right)
$$

> 这一部分的约等于看参考1，2

## 2.6 Vacuum fluctuations and the zero-point energy  

场算符$\hat E$在真空态上的涨落
$$
\Delta E_x = \mathcal{E}_0\sin\left(kz\right)
$$
真空态涨落和零点能拥有相同的起源，**那就是产生算符和湮灭算符不对易**。

同时，由于零点能的存在又导致了量子场论中的一系列的问题，比如：宇宙中包含这无穷无尽种模式的电磁场，如果所有模式的电磁场都具有零点能的话，那么就会出现
$$
E=\sum_{\omega}\frac12\hbar\omega=\frac12\hbar\sum_{\omega}\omega\to\infty
$$
也就是说宇宙中，仅仅只需要处于真空态就已经具备了无穷大的能量了！如果这一条成立的话，那么我们的一切工作就没有了能量的基点，也就是，我们计算的能量都相当于在无穷大上增加一点有限的能量，这在数学上显然是不合理的。无穷大加上任何有限的数都是无穷大。

那么想要解决这个问题，除非一些高频模式被排除掉，也就是高频模式不具备零点能，也就是基态能量为零。

事实上，零点能和真空涨落真的可以产生可观察的效应。

1. 自发辐射和真空涨落有关（这个在第四章进行讲解）
2. 零点能和Lamb shift（兰姆位移）和 Casimir effect  （卡西米尔效应）

### 2.6.1 Lamb shift

兰姆位移就是在氢原子上，实验和狄拉克相对论之间的差异

### 2.6.2  Casimir effect

这一部分不建议继续看了，看不懂了，难度骤然上升，没必要在看了。直接看下一节

## 2.7 The quantum phase  

经典情况下的单模电场表达式
$$
\begin{aligned}
\bold E\left(\bold r,t\right)&=\bold e_x E_0\cos\left(\bold k\cdot\bold r-\omega t+\phi\right)\\
&=\bold e_x\frac12E_0\left\{\exp\left[i\left(\bold k\cdot\bold r-\omega t+\phi\right)\right]+\exp\left[-i\left(\bold k\cdot\bold r-\omega t+\phi\right)\right]\right\}
\end{aligned}
$$
上式中$E_0$是振幅，$\phi$是相位（感觉就是初相位）。

将经典的电场表达式和我们之前得到的单模量子场算符表达式（如下所示）进行比较可得
$$
\hat{ \bold E}\left(\bold r,t\right)=i\left(\frac{\hbar \omega}{2\epsilon_0V}\right)\bold e_x\left[\hat a\exp\left(i\bold k\cdot\bold r-i\omega t\right)-\hat a^\dagger\exp\left(-i\bold k\cdot\bold r+i\omega t\right)\right]
$$
将算符$\hat a$和$\hat a^\dagger$替换成极坐标的形式，那么就跟经典的差不多了。

### 2.7.1 Dirac 的最早尝试

$$
\begin{aligned}
\hat a&=\exp\left(i\hat \phi\right)\sqrt{\hat n}\\
\hat a^\dagger&=\sqrt{\hat n}\exp\left(-i\hat \phi\right)
\end{aligned}
$$

其中，$\hat \phi$**被解释为**厄密相位算符

> 注意我说的是被解释为，但是这个相位算符并不是我们想要的那种厄密相位算符

由$\left[\hat a,\hat a^\dagger\right]=1$，我们可以得到
$$
\begin{aligned}
\left[\hat a,\hat a^\dagger\right]&=\hat a\hat a^\dagger-\hat a^\dagger\hat a\\
&=\exp\left(i\hat \phi\right)\sqrt{\hat n}\sqrt{\hat n}\exp\left(-i\hat \phi\right)-\sqrt{n}\exp\left(-i\hat\phi\right)\exp\left(i\hat\phi\right)\sqrt{\hat n}\\
&=\exp\left(i\hat \phi\right)\hat n\exp\left(-i\hat \phi\right)-\hat n\\
&=1
\end{aligned}
$$
利用BCH公式
$$
\hat n+1 = \hat n+i\left[\hat \phi,\hat n\right]+\frac{i^2}{2!}\left[\hat \phi,\left[\hat \phi,\hat n\right]\right]+\frac{i^3}{3!}\left[\hat\phi,\left[\hat \phi,\left[\hat \phi,\hat n\right]\right]\right]+\cdots
$$
通过对比等号左右两边我们就能得到
$$
\left[\hat n,\hat\phi\right]=i
$$
因此，数算符$\hat n$和相位算符$\hat \phi$两者之间并不对易，也就是无法被同时确定，从而满足不确定性关系。
$$
\Delta n\Delta \phi\geq \frac12
$$
然而，上式的不等式是不正确的，因为对于相位来说，相位的全空间就是$\left[0,2\pi\right]$，所以当$\Delta n$非常非常小的时候，$\Delta \phi$最大也就是$2\pi$，所以无法满足上面的不等式。

用另一种方法也可以证明这种相位算符$\hat \phi$是不合适的。在粒子数表象下我们有
$$
\langle m|\left[\hat n,\hat \phi\right]|n\rangle=(m-n)\langle m|\hat\phi|n\rangle=i\delta_{m,n}
$$
如果$m=n$，看第一个等号后面就是零，但是在第二个等号后面却是$i$，这显然是矛盾得。

同时还有一个方法证明我们的假设是错误的。**如果$\hat \phi$作为厄米算符，那么$\exp\left(i\hat\phi\right)$应该是一个幺正算符。**但是下面我们将会证明$\exp\left(i\hat\phi\right)$并不是一个幺正算符。
$$
\begin{aligned}
\begin{cases}
e^{i\hat\phi}&=\hat a\left(\hat n\right)^{-\frac12}\\
e^{-i\hat\phi}&=\left(\hat n\right)^{-\frac12}\hat a^\dagger=\left(e^{i\hat\phi}\right)^\dagger\\
\end{cases}
\Longrightarrow
\begin{cases}
\left(e^{i\hat \phi}\right)^\dagger\left(e^{i\hat\phi}\right)&=\frac{1}{\sqrt{\hat n}}\hat n\frac{1}{\sqrt{\hat n}}=1\\
\left(e^{i\hat\phi}\right)\left(e^{i\hat \phi}\right)^\dagger&=\hat a\frac{1}{\hat n}\hat a^\dagger\neq1
\end{cases}
\end{aligned}
$$
所以，$\exp\left(i\hat \phi\right)$并不是幺正算符，从而$\hat \phi$不是厄米算符。$\exp\left(i\hat \phi\right)$不是幺正算符的原因在于，算符$\hat n$是有下界的，也就是说，$\hat n$的本征值没有负整数

> 关于这个原因只看上面的公式，并没有看出来。下面进行详细的计算。
> $$
> \begin{aligned}
> \exp\left(i\hat\phi\right)|n\rangle&=\hat a\left(\hat n\right)^{-1/2}|n\rangle=n^{1/2}n^{-1/2}|n-1\rangle=|n-1\rangle,\quad n\neq0\\
> \exp(-i\hat\phi)|n\rangle&=\left(\hat n\right)^{-1/2}\hat a^\dagger|n\rangle =\left(\hat n\right)^{-1/2}\left(n+1\right)^{1/2}|n+1\rangle
> \\&=\left(n+1\right)^{1/2}\left(n+1\right)^{-1/2}|n+1\rangle=|n+1\rangle
> \end{aligned}
> $$
> 那么，我们可以将相位指数算符展开成下面的形式
> $$
> \begin{aligned}
> \exp\left(i\hat\phi\right)&=\sum_{n=0}^\infty |n\rangle\langle n+1|\\
> \exp\left(-i\hat \phi\right)&=\sum_{n=0}^\infty|n+1\rangle\langle n|
> \end{aligned}
> $$
> 我们再看看幺正算符满足的条件
> $$
> \begin{aligned}
> \exp\left(i\hat \phi\right)\exp\left(-i\hat\phi\right)&=\sum_{n=0}^\infty\sum_{n'=0}^\infty|n\rangle\langle n'+1|n+1\rangle\langle n|\\
> &=\sum_{n=0}^\infty\sum_{n'=0}^\infty|n'\rangle\langle n|\delta_{n',n}\\
> &=\sum_{n=0}^\infty|n\rangle\langle n|\\
> &=1
> \\
> \exp\left(-i\hat\phi\right)\exp\left(i\hat\phi\right)&=\sum_{n=0}^\infty\sum_{n'=0}^\infty |n'+1\rangle\langle n'|n\rangle\langle n+1|\\
> &=\sum_{n=0}^\infty\sum_{n'=0}^\infty |n'+1\rangle\langle n+1|\delta_{n,n'}\\
> &=\sum_{n=0}^\infty|n+1\rangle\langle n+1|\\
> &=\sum_{n=0}^\infty |n\rangle\langle n|-|0\rangle\langle 0|\\
> &=1-|0\rangle\langle 0|
> \end{aligned}
> $$
> 从上面的推导可以看出来，第二个式子之所以不等于1，原因从倒数第三行能够看出来，就是$n$从零开始，要是$n$从$-\infty$开始的话就不会出现这么多的问题了。





## 参考

1. [根号下（1+x）泰勒公式怎么展开_百度知道 (baidu.com)](https://zhidao.baidu.com/question/1736646256602881707.html)
2. [当x的绝对值很小时,求根号下1加x的近似值_百度知道 (baidu.com)](https://zhidao.baidu.com/question/1884195679738031748.html)
3. 





