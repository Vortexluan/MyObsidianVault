
首先要说明有的时候我们会用到收敛控制定理
[[收敛控制定理（Dominated Convergence Theorem, DCT）]]

下面是一些最简单换元的例子
1. 线性发散
$$\lim_{n\to\infty}\int_0^n e^{-x/n}\,dx
\xrightarrow{t=x/n}
n\int_0^1 e^{-t}\,dt = n(1-e^{-1})\to\infty$$

2. Riemann 和还原
$$\lim_{n\to\infty}\frac{1}{n}\int_0^n f\!\Bigl(\frac{x}{n}\Bigr)\,dx
    \xrightarrow{t=x/n}
    \int_0^1 f(t)\,dt$$
3. 窄峰面积
$$\lim_{\varepsilon\to 0^+}\frac{1}{\varepsilon}\int_0^\varepsilon e^{-x^2/\varepsilon^2}\,dx
    \xrightarrow{t=x/\varepsilon}
    \int_0^1 e^{-t^2}\,dt = \frac{\sqrt\pi}{2}\operatorname{erf}(1)$$


这道题AI给的解法是不是有问题？

$$
L = \lim_{n\to\infty}n\int_0^n\frac{\sin^2(x/n)}{1+x^2}\,dx$$


1. 尺度换元 `t=x/n`
$$
    L = n^2\int_0^1\frac{\sin^2 t}{1+n^2t^2}\,dt$$

1. 点态估计 `|\sin^2 t|\le t^2`
$$
    0\le \frac{n^2 t^2}{1+n^2t^2}\le 1,\quad
    \text{且}\quad \frac{n^2 t^2}{1+n^2t^2}\to 0\;(n\to\infty)$$

2. 控制收敛
$$
    \frac{\sin^2 t}{1+n^2t^2}\le \frac{1}{1+t^2}\in L^1[0,1]
    \quad\Longrightarrow\quad
    L = \int_0^1 \frac{sin^2t}{t^2}\,dt = \frac{\pi}{4}-\frac{1}{2}$$

> 看到“区间长度 ∝ n”，**先缩成 1**——这就是**尺度还原**；  
> 缩完后极限常能**一眼 0** 或**一眼常数**，再不济也可上 **DCT / Laplace**。

一句话判断准则

- **区间长度 ∝ 大参数** → “压扁” (`t = x/n`)
    
- **区间长度固定，但**被积函数**在某点出现 `~1/n` 窄峰** → “拉宽” (`t = n(x-x₀)` 或 `t = (x-x₀)/ε`)
    

1. 指数窄峰

$$
\lim_{n\to\infty}n\int_1^2\frac{dx}{1+x^n}
\xrightarrow{t=n(x-1)}
\int_0^\infty\frac{dt}{1+e^t}
=\ln 2
$$
这里的换元其实思想比较简单，希望能够保持积分的某一界能稳定，不然的话容易整出奇怪的东西。

2. Gaussian 窄峰


$$
\lim_{\varepsilon\to 0^+}\frac{1}{\varepsilon}\int_0^1
e^{-(x-1/2)^2/\varepsilon^2}dx
\xrightarrow{t=(x-1/2)/\varepsilon}
\int_{-1/(2\varepsilon)}^{1/(2\varepsilon)}e^{-t^2}dt
\to\sqrt\pi
$$
---

3. Laplace 型


$$
\int_0^1 e^{n(x-\ln x)}dx
\xrightarrow{t=n(x-1)}
\frac{e^n}{\sqrt n}\int_{-\infty}^0 e^{t^2/2}dt
\sim e^n\sqrt{\frac\pi{2n}}
$$



4. Stirling 秒算
$$
n! = \int_0^\infty x^n e^{-x}dx
\xrightarrow{t=(x-n)/\sqrt n}
\sqrt n\,(n/e)^n\int_{-\infty}^\infty e^{-t^2/2}dt
= \sqrt{2\pi n}\,(n/e)^n
$$








以上是试图使用分段估计的方法来处理这种含参数积分的极限问题，但是事实上，我们有五种方法来解决这一类问题，没有某种特定的方法能够保证奏效，但是这五种方法能够涵盖大部分问题。
至于所谓的换元和泰勒展开等等是非常普遍的技巧了，事实上在下面这五种方法里面都可以用，这是一种很通用的东西。



1.转化为和的估计来处理
Fubini-Tonelli 这个是用来交换积分符号和求和符号的

2.基于分部积分法的积分估计
这个的要点是每次分部积分以后得到的新的积分函数就会衰减的更快

3.分段估计
当一个积分中重要的积分都只分布在某处而其它地方足够小可以忽略不计的时候我们考虑这种估计方法。
根据经验我们知道这个方法的技巧性是比较强的，个人觉得比较好的方式是在将其它几个方法都尝试以后再考虑这个方法。

4.控制收敛定理（DCT）
[[收敛控制定理（Dominated Convergence Theorem, DCT）]]
被积分的函数必须要有一个不含参数的上界，有时候为了得到这样一个上界，我们需要换元，在换元后的函数就不一定是在某一处聚集然后爆炸的情况了，这个时候所谓的“尺度换元”就派上用场了。

不过必须要知道的是，尺度换元绝对不是唯一一种换元的方案，之前见过有t=x^n的这种就完全不在尺度换元的类别里面

5.Laplace方法
[[Laplace方法]]



事实上我们是还有一种方法可以使用，但是需要提前猜到答案是多少 （这个有点像那个什么b拟合法）
浙江大学考研数学分析
 $f$是$[0,1]$上黎曼可积的函数,并且在$x=0$处连续，证明$$\lim_{h\to 0^{+}}\int_{0}^{1}\frac{h}{h^2+x^2}f(x)\,dx=\frac{\pi}{2}f(0)$$
此处我们把问题理解为一个积分估计的问题，我们无非就是要估计含参数的积分，并得到渐进结果$$\int_{0}^{1}\frac{h}{h^2+x^2}f(x)\,dx=\frac{\pi}{2}f(0)+o(1)$$因此我们要证明，$$I(h):=\left|\int_{0}^{1}\frac{h}{h^2+x^2}f(x)\,dx-\frac{\pi}{2}f(0)\right|=o(1)$$
但问题在于并不是所有的题目都是给出答案让你证明，如果遇到要求的时候这个方法就不是很管用了。







我们通过一两个题目来说明下面五种方法的使用情况

$$\lim_{n\to+\infty}n\int_{0}^{1}\frac{x^n}{1+x}\,dx$$



1.
**题**
$$
\lim_{n\to+\infty}n\int_{0}^{1}\frac{e^x}{1+n^2x^2+n^3x^4}\,dx
$$
**解**
尺度换元+分段估计+拟合法
显然在x趋近于1的时候几乎为0，x趋近于0的时候才是主要贡献的部分，故考虑尺度换元，具体的形式都是次要的，拉长峰才是最重要的部分。


2.
$$\lim_{x\to +\infty}\sqrt{x}\int_{0}^{\frac{\pi}{4}}e^{x(\cos t-1)}\,dt$$
这里也要做好归到高斯积分的准备（原因是e），同样拆成两部分，我们对于(cost-1)是通过泰勒展开给出积分两边的估计


这个东西其实可以提取为找下面这个式子的阶$$\lim_{s\to +\infty}\int f(x)e^{sg(x)}\,dx$$
这就是laplace定理，使用的也是泰勒来给出证明


3.
$$\begin{aligned}
f(x)\text{ is continuous on }[0,1],\text{calculate }\lim_{s \to +\infty}\frac{1}{s}\int_{0}^{1}f(x)\frac{\sin^2nx}{\sin^2x}\,dx
\end{aligned}$$

如果题目是要我们证明等于\frac{pi}{2}f(0),可以很适当的揣测这里的\pi是通过高斯积分或者迪利克雷积分得到的，这是要有的心理准备。

还有一点就是$\frac{\sin^2nx}{\sin^2x}$是比较难以处理的，我们一般会考虑中间插一个x进去来对付它，尤其是在这种泰勒无法直接使用的情况下，通过这种方式把一边归到f(x)再用积分中值提出可以大大简化(f(x)的这种情况通常会在峰出提出处理)

4.
$$\lim_{n\to \infty}\int_{0}^{1}\frac{dx}{1+nx^5}$$

5.
$$\lim_{n\to \infty}\int_{0}^{1}\frac{x^n(1-x)^n}{n!}\,dx$$



