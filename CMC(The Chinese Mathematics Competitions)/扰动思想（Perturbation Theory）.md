这个本质上就是抓大放小，将不等式改写成有小量的并且能消去的等式
1.
**题**
$$\forall x,y\in \mathbb{R},|f(x+y)-f(x-y)-y|\le y^2,\text{find } f(x+y)$$
**解**
我们当然可以使用换元来解决这个问题，但是这样的解法不利于了解题目的本质
$$\begin{aligned}
&f(x+y)-f(x-y)=y+y^2\varepsilon (x,y),(|\varepsilon(x,y)|\le1)
\\
&\text{显然一阶会比二阶更重要}
\\
&\frac{f(x+y)-f(x-y)}{y}=1+y\varepsilon(x,y)
\\
&y\to0,2f'(x)=1
\\
&f(x+y)=\frac{x+y}{2}+C
\end{aligned}$$
2.
**题**
$$\begin{aligned}
&\forall x,y \in \mathbb{R},\text{the function }f:\mathbb{R} \to \mathbb{R}\text{ satisfies
}
\\
&|f(x+y)-f(x-y)-2f(x)-y^2|\le y^3
\\
&\text{we assume f is second-order differentiable in order to simplify}
\\
&\text{Find }f(x+y)
\end{aligned}$$
**解**
$$\begin{aligned}
&f(x+y)-f(x-y)-2f(x)=y^2+y^3\varepsilon(x,y),(|\varepsilon|\le 1)
\\
&f(x+y)=f(x)+f'(x)y+\frac{f''(\xi_1)}{2}y^2
\\
&f(x-y)=f(x)+f'(x)(-y)+\frac{f''(\xi_2)}{2}y^2
\\
&\frac{f''(\xi_1)}{2}y^2+\frac{f''(\xi_2)}{2}y^2=y^2+y^3\varepsilon(x,y)
\\
&y\to 0,f''(x)=0
\\
&
f(x+y)=C_1(x+y)+C_2
\end{aligned}
$$
3.
**题**
对于所有实数 $x, y$，函数 $f: \mathbb{R} \to \mathbb{R}$ 满足 $|f(x+y) - f(x) - f(y) - x y| \leq x^2 y^2$。求 $f(x+y)$ 的表达式。

**解**
感觉在这种地方扰动思想和$\Delta x$（我自己那个几把方法）一起使用比较好
得到
$$f(x)=f'(0)x-\frac{1}{2}x^2+C$$



需要知道的一件事情是，\Delta x方法是要求函数能够可导的，如果没有可导的条件，那就不方便了。
这里，我们想办法给出函数可导的证明办法。

我们刚才说的扰动和\Delta x在这里不好用，考虑
不对？好像不好证？
$$
\begin{aligned}
&g(x)=f(x)-\frac{1}{2}x^2
\\
&\text{so}|g(x+y)-g(x)-g(y)|\le x^2y^2
\\
&g(x+y)-g(x)-g(y)=\epsilon x^2y^2
\\
&
\end{aligned}$$

4.
**题**
于所有实数 $x,y$，函数 $f: \mathbb{R} \to \mathbb{R}$ 满足 $|f(x+y) - f(x-y) - 2 y f'(x)| \leq y^4$，假设 $f$ 可微。求$f(x+y)$ 的形式。



上面这几道题就是大概3个东西
1.扰动思想
2.\Delta x方法
3.通过绝对值内部构造函数消去多项式，使得绝对值内部只剩下函数的方法。