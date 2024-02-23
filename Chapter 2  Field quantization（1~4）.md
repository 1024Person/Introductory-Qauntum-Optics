# Chapter 2  Field quantization

## 2.1 Quantization of a single-mode field  

谐振腔，z轴，$z\in [0,L]$，自由空间中的MaxWell方程组
$$
\begin{cases}
\begin{aligned}
	\nabla \cdot E &= 0\\
	\nabla \cdot B &= 0\\
	\nabla \times E&=-\frac{\partial B}{\partial t}\\
	\nabla \times B&=\mu_0\frac{\partial D}{\partial t}
\end{aligned}
\end{cases}
$$
电场的表达式(电场的偏振在$x$方向偏振)
$$
\bold E(\bold r,t)=\bold e_x E_x(z,t)\\
E_x(z,t) = (\frac{2\omega^2}{V\epsilon_0})^{1/2}q(t)\sin(kz)
$$
![](https://s2.loli.net/2024/02/17/9FGMBTcH4JaK5rL.png)

驻波条件：$m =\frac{L}{\lambda/2}=\frac{2L}{2\pi/k}=k\frac{L}{\pi}=\frac{\omega L}{c\pi}$，所以$\omega_m=\frac{c\pi m}{L}$，我们假设$E_x$中的$\omega$是满足条件的众多频率中的一个。同时$V$是腔中的有效频率，同时$q(t)$是时间依赖因子，具有长度量纲，我们可以将其看成正则坐标。

腔中的磁场坐标
$$
\bold B(\bold r,t) =\bold e_y B_y(z,t) \\
B_y(z,t)=(\frac{\mu_0\epsilon_0}{k})(\frac{2\omega^2}{V\epsilon_0})^{1/2}\dot{q}(t)\cos(kz)
$$
其中$\dot{q}(t)$将会充当正则动量的作用，也就是$p(t)=\dot q(t)$。

经典电场磁场的能量
$$
H = \frac12\int dV\left[\epsilon_0\bold E^2(\bold r,t)+\frac{1}{\mu_0}\bold B^2(\bold r,t)\right]\\
=\frac{1}{2}\int dV\left[\epsilon_0 E^2_x(z,t)+\frac{1}{\mu_0}B_y^2(z,t)\right]\\
=\frac{1}{2}\left(q\omega^2+p^2\right)
$$

>展开
>$$
>\begin{aligned}
>E^2_x(z,t)&=(\frac{2\omega^2}{V\epsilon_0})q^2(t)\sin^2(kz)\\
>B^2_y(z,t)&=(\frac{\mu_0\epsilon_0}{k})^2(\frac{2\omega^2}{V\epsilon_0})\dot{q}^2(t)\cos^2(kz)\\
>&=\frac{\mu_0^2\epsilon_0}{k^2}\frac{2\omega^2}{V}\dot q^2(t)\cos^2(kz)\\
>&=\frac{\mu_0^2\epsilon_0}{\omega^2/c^2}\frac{2\omega^2}{V}\dot q^2(t)\cos^2(kz)\\
>&=2\frac{\mu_0^2 c^2\epsilon_0}{V}\dot q^2(t)\cos^2(kz)\\
>&=2\frac{\mu_0}{V}\dot q^2(t)\cos^2(kz)\\
>&=2\frac{\mu_0}{V}p^2(t)\cos^2(kz)\\
>\end{aligned}
>$$
>下面计算能量（哈密顿量）
>$$
>\begin{aligned}
>H &=\frac12 \int dV\left[\epsilon_0 (\frac{2\omega^2}{V\epsilon_0})q^2(t)\sin^2(kz)+2\frac1\mu_0\frac{\mu_0}{V}p^2(t)\cos^2(kz)\right]\\
>&=\frac{1}{2}\int \int \int_0^L dz dy dx\left[\epsilon_0 (\frac{2\omega^2}{V\epsilon_0})q^2(t)\sin^2(kz)+2\frac1\mu_0\frac{\mu_0}{V}p^2(t)\cos^2(kz)\right]\\
>&=\sigma_{xy}\frac{1}{2}\int_0^L dz\left[\frac{2q^2(t)\omega^2}{V}\frac{1}{2}\left(1-\cos(2kz)\right)\right]+\sigma_{xy}\frac{1}{2}\int_0^L dz\left[2\frac{\dot q^2(t)}{V}\frac12\left(1+\cos(2kz)\right)\right]\\
>&=\frac{1}{2}\left(q^2\omega^2+p^2\right)
>\end{aligned}
>$$

从上面的形式说明了一件事情，电磁场在形式上等价于单位质量的谐振子。电场发挥着正则坐标，磁场发挥正则动量的作用。

下面用相应的算符进行替换$p:\to\hat p,q:\to \hat q$，其中满足对易关系
$$
[\hat q,\hat p]=i\hbar \hat I
$$
那么电场和磁场的量子化形式为：
$$
\begin{aligned}
\hat E_x(z,t) &= \left(\frac{2\omega^2}{V\epsilon_0}\right)^{1/2}\hat q(t)\sin\left(kz\right)\\
\hat B_y(z,t) &= \left(\frac{\mu_0\epsilon_0}{k}\right)\left(\frac{2\omega_0^2}{V\epsilon_0}\right)^{1/2}\hat p(t)\cos(kz)
\end{aligned}
$$
进而电磁场的哈密顿量：
$$
\hat H=\frac12(\omega^2\hat q^2+\hat p^2)
$$
为了量子化，我们引入产生湮灭算符
$$
\begin{aligned}
\hat a&=(2\hbar \omega)^{-1/2}(\omega \hat q+i\hat p)\\
\hat a^\dagger&=(2\hbar \omega)^{-1/2}(\omega \hat q-i\hat p)
\end{aligned}
$$
进而，电场和磁场的量子表达式
$$
\begin{aligned}
\hat E_x(z,t)&=\mathcal{E}_0\left(\hat a+\hat a^\dagger\right)\sin(kz)\\
\hat B_y(z,t)&=\mathcal{B}_0\left(\hat a-\hat a^\dagger\right)\cos(kz)
\end{aligned}
$$
其中，$\mathcal{E}_0=(\hbar\omega/\epsilon_0 V)^\frac{1}{2}$，并且$\mathcal{B}_0=(\mu_0/k)(\epsilon_0\hbar\omega^3/V)^{1/2}$。同时，$\hat a,\hat a^\dagger$满足下列关系
$$
\left[\hat a,\hat a^\dagger\right]=1
$$
再对哈密顿量进行量子化
$$
\hat H = \hbar \omega\left(a^\dagger a+1\right)
$$

> 下面，有关产生湮灭算符的事情就不再继续展开了，都学过了，主要还是看看怎么将电磁场实现量子化的过程的。
>
> 但是有一点就是$\hat a(t)=\hat ae^{-i\omega t},\hat a^\dagger(t) = \hat a^\dagger e^{i\omega t}$，这个重新带回到电场算符的表达式中有了新的表达式
> $$
> \hat E_x(z,t)=\mathcal{E}_0(\hat a e^{-i\bold k\cdot \bold r-i\omega t}+\hat a^\dagger e^{i\bold k\cdot \bold r +i\omega t})
> $$
>

## 2.2 Quantum fluctuations of a single-mode field  

电场，磁场的期望值：
$$
\begin{aligned}
\langle n| E_x(z,t)|n\rangle&= \mathcal{E}_0\sin\left(kz\right)\left[\langle n|a|n\rangle+\langle n|a^\dagger|n\rangle \right]=0\\
\langle n|E^2_x(z,t)|n\rangle&=\mathcal{E}^2_0\sin^2\left(kz\right)\langle n| a^2+(a^\dagger)^2+a a^\dagger+a^\dagger a|n\rangle\\
&=\mathcal{E}^2_0\sin^2(kz)\langle n|a^2+(a^\dagger)^2+2a^\dagger a+1|n\rangle\\
&=2\mathcal{E}^2_0\sin^2(kz)\left(n+\frac12\right)\\
\langle \left(\Delta E_x(z,t)\right)^2\rangle&=\langle E_x^2(z,t)\rangle-\langle E_x(z,t)\rangle^2=\langle E_x^2(z,t)\rangle\\
&=2\mathcal{E}_0\sin^2(kz)\left(n+\frac12\right)\\
\Delta E_x(z,t)&=\left\langle \Delta E_x(z,t))^2\right\rangle^{1/2}=\sqrt{2\mathcal{E}_0}\sin(kz)\left(n+\frac12\right)^{1/2}
\end{aligned}\\
$$
可以看到，量子涨落当$n=0$的时候，量子涨落是最小的。
$$
\left[\hat n,\hat E_x\right]=\mathcal{E}_0\sin(kz)\left(\hat a^\dagger-\hat a\right)
$$
那么不确定关系
$$
\Delta n\Delta E_x\leq \frac{1}{2}\mathcal{E}_0\left|\sin(kz)\right|\left|\left\langle a^\dagger-a\right\rangle\right|
$$
对于态$|n\rangle$，我们可以得到$\Delta n=0$，同时上式右侧等于0。换而言之，如果我们完全的确定了场$\Delta E_x=0$，那么量子数是完全不确定的。

---

下面对于相位的引入，我感觉自己说不清楚，还是直接看原文吧

![](https://s2.loli.net/2024/02/17/Chpw51bNIWJgFEz.png)

> 将粒子数$n$看作振幅，相位$\phi$看作相位，两者不能同时确定。
>
> 相位的全空间就是$[0,2\pi]$，相位完全不确定就是在$[0,2\pi]$上均匀分布。

---

## 2.3 Quadrature operators for a single-mode field  

正交算符
$$
\hat X_1= \frac{1}{2}\left(\hat a+\hat a^\dagger\right)\\
\hat X_2 = \frac{1}{2i}\left(\hat a-\hat a^\dagger\right)
$$
那么场算符就可以重新写成
$$
\hat E_x(z,t)=2\mathcal{E}_0\sin(kz)\left[\hat X_1\cos(\omega t)+\hat X_2\sin(\omega t)\right]
$$
这个$\hat X_1$和$\hat X_2$之间为什么是正交的，我也没看出来，感觉像是由于$\cos(\omega t)$和$\sin(\omega t)$调制的原因，导致，$\hat X_1$和$\hat X_2$是正交的。下面直接看原图

![](https://s2.loli.net/2024/02/17/C5aXwmbIZk6g1Wv.png)

其实这里的$\hat X_1$和$\hat X_2$就是正则坐标和正则动量。其中，$\hat X_1$和$\hat X_2$满足下面的对易关系
$$
\left[\hat X_1,\hat X_2\right]=\frac12
$$
所以，$\hat X_1$和$\hat X_2$的不确定关系
$$
\left\langle \left(\Delta\hat X_1\right)^2\right\rangle\left\langle \left(\Delta\hat X_2\right)^2\right\rangle\geq\frac{1}{16}
$$


下面对$\hat X_1,\hat X_2$之间量子涨落进行讨论
$$
\begin{aligned}
\langle n|\hat X_1|n \rangle&=\langle n|\hat X_2|n\rangle = 0\\
\langle n|\hat X_1^2|n\rangle&=\frac{1}{4}\langle n|\hat a^2+(\hat a^\dagger)^2+\hat a\hat a^\dagger+a^\dagger a|n\rangle\\
&=\frac14\langle n|\hat a^2+(\hat a^\dagger)^2+2\hat a^\dagger a+1|n\rangle\\
&=\frac12\left(n+\frac12\right)\\

\langle n|\hat X_2^2|n\rangle&=-\frac{1}{4}\langle n|\hat a^2+(\hat a^\dagger)^2-\hat a\hat a^\dagger-a^\dagger a|n\rangle\\
&=-\frac14\langle n|\hat a^2+(\hat a^\dagger)^2-2\hat a^\dagger a-1|n\rangle\\
&=\frac12\left(n+\frac12\right)\\
\left \langle \left(\Delta\hat X_1\right)^2\right \rangle&=\left \langle \left(\Delta\hat X_2\right)^2\right \rangle=\frac12\left(n+\frac12\right)
\end{aligned}
$$

## 2.4 Multimode fields  

引入一个矢量势$\bold A(\bold r,t)$，满足的偏微分方程
$$
\nabla^2 \bold A-\frac{1}{c^2}\frac{\partial^2 \bold A}{\partial t^2}=0
$$
库伦规范势（下面的就先不详细追究了）
$$
\nabla \cdot \bold A(\bold r,t)=0\\
\bold E(\bold r,t)=-\frac{\partial \bold A}{\partial t}\\
\bold B(\bold r,t)=\nabla\times \bold A(\bold r,t)
$$
下面我们讨论自由空间。我们假设立方体模型，边长为$L$，等到得到相应的结果之后，再令$L\to\infty$，就能得到自由空间中的结果了。之所以这样做是因为我们要强制用周期性条件。
$$
\begin{cases}
\begin{aligned}
	k_x &= \left(\frac{2\pi}{L}\right)m_x,\quad m_x =0,\pm 1,\pm2,\pm3,\cdots\\
	k_y &= \left(\frac{2\pi}{L}\right)m_y,\quad m_y =0,\pm 1,\pm2,\pm3,\cdots\\
	k_z &= \left(\frac{2\pi}{L}\right)m_z,\quad m_z =0,\pm 1,\pm2,\pm3,\cdots\\
\end{aligned}
\end{cases}
$$
在间隔$\Delta m_x,\Delta m_y,\Delta m_z$之间的模式数
$$
\Delta m = \Delta m_x\Delta m_y\Delta m_z = 2\left(\frac{L}{2\pi}\right)^3\Delta k_x\Delta k_y\Delta k_z
$$
考虑到自由空间中的连续变量。
$$
dm=2\left(\frac{V}{8\pi^3}\right)dk_xdk_ydk_z
$$
对于k空间的球坐标
$$
\bold k=k\left(\sin\theta \cos\phi,\sin\theta\sin\phi,\cos\theta\right)
$$
带入可得
$$
dm=2\left(\frac{V}{8\pi^3}\right)k^2dkd\Omega
$$
其中，$d\Omega = \sin\theta d\theta d\phi$，利用$k=\omega_k/c$
$$
dm =2\left(\frac{V}{8\pi^3}\right)\frac{\omega^2k}{c^3}d\omega_kd\Omega
$$
对上式进行积分，分别积掉$d\Omega$，可得到
$$
V\frac{k^2}{\pi^2}dk = V\rho_kdk\\
V\frac{\omega_k^2}{\pi^2c^3}d\omega_k=V\rho(\omega_k)dk
$$
其中，$\rho_k=k^2/\pi^2,\rho(\omega_k)=\omega_k^2/\pi^2c^3$。教材里面讨论这个就是为了讨论多模场的特殊点。

矢量势可以写成平面波的叠加态的形式
$$
\bold A(\bold r,t)=\sum_{\bold k,s}\bold e_{\bold k,s}\left[A_{\bold k,s}(t)e^{i\bold k\cdot \bold r}+A^*_{\bold k,s}(t)e^{-i\bold k\cdot \bold r}\right]
$$
这里求和的部分，对于$\bold k$求和其实就是对$m_x,m_y,m_z$求和，对$s$求和就是对极化方向求和，一共就两个取值。
$$
e_{\bold k,s}\cdot e_{\bold k,s'}=\delta_{s,s'}\\
\bold k\cdot\bold e_{\bold k,s}=0\\
e_{\bold k 1}\times e_{\bold k2}=\frac{\bold k}{|\bold k|}=\bold \kappa
$$
在自由空间中，矢量势的叠加态可以写成积分的形式，但是我一直没看懂（这个积分的形式到底是怎么出来的）
$$
\sum_k\to\frac{V}{\pi^2}\int k^2dk
$$
将$\bold A$的表达式带入到表达式$\nabla^2 \bold A-\frac{1}{c^2}\frac{\partial^2 \bold A}{\partial t^2}=0,\nabla\cdot \bold A=0$，可得

> 球坐标下
> $$
> \nabla^2 = \frac{\partial^2 }{\partial r^2}+\frac{1}{r^2\sin\theta}\frac{\partial }{\partial \theta}\left(\sin\theta\frac{\partial }{\partial \theta}\right)+\frac{1}{r^2\sin^2\theta }\frac{\partial^2}{\partial \phi^2}
> $$
> 

下面进行推导
$$
\nabla^2 \bold A-\frac{1}{c^2}\frac{\partial^2 \bold A}{\partial t^2}=0\\
\frac{\partial^2}{\partial r^2}\left[ A_{\bold ks}(t)e^{i\bold k\cdot \bold r}+ A_{\bold ks}^*(t)e^{-i\bold k\cdot\bold r}\right]-\frac{1}{c^2}\frac{\partial^2}{\partial t^2}\left[ A_{\bold ks}(t)e^{i\bold k\cdot \bold r}+ A_{\bold ks}^*(t)e^{-i\bold k\cdot\bold r}\right]=0\\
-k^2[ A_{\bold ks}(t)e^{i\bold k\cdot\bold r}+A_{\bold ks}^{*}e^{-i\bold k\cdot\bold r}]-\frac{1}{c^2}\left[\frac{\partial^2}{\partial t^2} A_{\bold ks}(t)e^{i\bold k\cdot \bold r}+\frac{\partial ^2}{\partial t^2} A_{\bold ks}^*(t)e^{-i\bold k\cdot\bold r}\right]=0\\
\begin{cases}
k^2 A_{\bold ks}(t)+\frac{1}{c^2}\frac{\partial^2}{\partial t^2} A_{\bold ks}(t)=0\\
k^2 A^*_{\bold ks}(t)+\frac{1}{c^2}\frac{\partial^2}{\partial t^2} A^*_{\bold ks}(t)=0\\

\end{cases}\\
\frac{\partial ^2}{\partial t^2}A_{\bold ks}(t)+\omega_k^2A_{ks}(t)=0
$$
从而可以解的
$$
A_{ks}(t)=A_{ks}e^{-i\omega_k t}
$$
其中，$A_{ks}(0)=A_{ks}$。

由$\bold E=-\frac{\partial}{\partial t}\bold A,\bold B=\nabla \times\bold A$，可得

![image-20240217154009129](https://s2.loli.net/2024/02/17/m1BLK3PVcdjrw6f.png)

电磁场哈密顿量
$$
H=\frac12\int_V\left(\epsilon_0\bold E\cdot \bold E+\frac{1}{\mu_0}\bold B\cdot\bold B\right)dV
$$
这其中又是经过一系列的推导，就不再继续写了，就是纯体力活，下面直接展示最终结果

![image-20240217154659828](https://s2.loli.net/2024/02/17/e78LFOvV1C6XtNQ.png)

其实，再次看场算符的表达式，并且对比单模场的算符表达式，这其中的$A_{\bold ks}$，可以看成产生湮灭算符(但是两者并不是完全相等)

也就是
$$
A_{\bold ks}=\frac{1}{2\omega_k(\epsilon_0V)^{1/2}}[\omega_k q_{\bold ks}+ip_{\bold ks}]\\
A^*_{\bold ks}=\frac{1}{2\omega_k(\epsilon_0V)^{1/2}}[\omega_k q_{\bold ks}-ip_{\bold ks}]
$$
带入到哈密顿量表达式中，可得
$$
H=\frac12\sum_{\bold ks}\left(p^2_{\bold ks}+\omega_kq^2_{\bold ks}\right)
$$
这个就是跟单位质量的谐振子哈密顿量非常的像，所以也就是能够对应于多模场的哈密顿量。量子化的过程就是将上面的正则变量变成算符，这些算符满足下面的对易关系

![image-20240217155818015](https://s2.loli.net/2024/02/17/nwclVZvi7qmXY1M.png)

对于产生湮灭算符做如下定义

![image-20240217155850698](https://s2.loli.net/2024/02/17/SX39OayYpNJEAb5.png)

电磁场的哈密顿量也就变成了量子化的形式。
$$
\hat H=\sum_{\bold ks}\hbar \omega_k\left(\hat a^\dagger_{\bold ks}\hat a_{\bold ks}+\frac12\right)\\
=\sum_{\bold ks}\hbar \omega_k\left(\hat n_{\bold ks}+\frac12\right)
$$
已经量子化了电磁场哈密顿量了，下面我们就继续考虑场算符的量子化，$\hat A_{\bold ks}$与$\hat a_{\bold ks}$的关系如下。

![](https://s2.loli.net/2024/02/17/B915tzyIOLNvMm4.png)

将其带入到场算符中，可得

![](https://s2.loli.net/2024/02/17/GbIHm6Tre9vc15F.png)

考虑海森堡运动方程，与单模光场相似$\hat a_{\bold ks}(t)=\hat a_{\bold ks}e^{-i\omega_k t}$，再回代到场算符表达式中，

![image-20240217161752862](https://s2.loli.net/2024/02/17/EhgVBMInNolOKRk.png)

同样的场算符，可以写成
$$
\hat E=\hat E^{(+)}+\hat E^{(-)}\\
\hat E^{(+)}=i\sum_{\bold ks}\left(\frac{\hbar\omega_k}{2\epsilon_0 V}\right)^{1/2}\bold e_{\bold ks}\hat a_{\bold ks}(t)e^{i\bold k\cdot\bold r}
$$
这个称作正频率部分