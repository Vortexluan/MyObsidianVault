说白了就是什么时候能够把极限塞进积分符号里面。




控制收敛定理（Dominated Convergence Theorem）
先给出一个完全看不懂的严格声明（这个应该是数学分析里面有的东西？）

1.$f_n$是测度空间$(X,\mu)$上的一列可测函数
2.$f_n(x)\to f(x)$ a.e.于$X$
3.存在非负可积函数$g \in L^1(X)$,s.t.
$$|f_n(x)|\le g(x),\text{对所有n以及a.e.}x\in X$$
则
$$\lim_{n\to \infty}\int_Xf_n \, d\mu=\int_Xf\, d\mu$$





我们把这个推论放到实数上去就是（对于具体积分我们只要确保在对应域上满足就可以了）

1.$f_n$是实数域上的一列实函数

2.逐点收敛
$$\forall x\in \mathbb{R},\exists \lim_{n\to \infty} f_n(x)=f(x)$$
（说人话就是对任何x，n趋向于极限时候原函数趋于某个数（收敛），这个数可以是x的函数）

3.存在控制函数
找到一条和n无关的可积函数$g:I\to[0,+\infty)$使得
$$|f_n(x)|\le g(x),\forall n,\forall x\in \mathbb{R}$$
(这里可积函数就是指的是面积有限的函数，在对应定义域上绝对值积分不会发散到无穷，就是说原来的f_n中都是可积的)
则
$$\lim_{n\to \infty}\int_{\mathbb{R}}f_n(x)\,dx=\int_{\mathbb{R}}f(x)\,dx$$




（注意，DCT允许我们先将区间涨到无穷再pass极限，比如
$$
A = \int_0^{n\delta}\frac{dt}{1+\left(1+\frac{t}{n}\right)^n}.
$$
$$
\lim_{n\to\infty}A = \int_0^\infty \frac{dt}{1+e^t} = \ln 2.

$$
这里$\delta$是一个我们挑的一个小量
这个东西的本质其实是
$$
A = \int_\mathbb{R}\frac{1}{1+\left(1+\frac{t}{n}\right)^n} 1_{0\le t\le n\delta}(t)\,dt
$$
然后DCT取极限，就可以达到对应的结果。
）


我们可以拿反例来说明
1.
$$
f_n(x)=\sin^2(n\pi x),\quad x\in[0,1].
$$
这个是不符合逐点收敛的。
注意这里的n就是趋向极限的那个n。
2.
$$
f_n(x)=e^{-(x-n)^2},\quad x\in\mathbb{R}.
$$