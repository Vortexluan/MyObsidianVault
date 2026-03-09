1.
**题**
$$
\begin{aligned}
&\text{Let f:}[0,1]\to \mathbb{R}\text{ is continuous on}[0,1],\forall x \in [0,1],|f(x)|\le1.
\\
&\text{Prove that }\exists x_0\in(0,1).s.t.|f'(x)|\le2
\end{aligned}
$$
**解**
用拉中放缩一下很快就有结果
bernstein g(x)=f(x)+2x^2只能证明很弱的结果|f'(x)|<=4
原因显然是因为这个构造直观的y=2x-1没有用上而是选择了神秘的加上二次项，这个构造是失败的。

我们考虑构造g(x)=f(x)-2x+1和g(x)=f(x)+2x-1
假设恒有|f'(x)|>2,则有f'(x)>2或者f'(x)<-2分别对应两个构造，
g(0),g(1)说明有零点,g’(x)说明单调，因此矛盾。

发现推广到下一题本质上是g(0)对应(0,0),g(1)对应边界,g'(x)说明极值情况

2.
**题**
$$
\begin{aligned}
&\text{Let }f: B \to \mathbb{R}\text{is partial differentiable on}B = \{ (x,y,z) \in \mathbb{R}^3 : x^2 + y^2 + z^2 \leq 1 \} \,,\text{and} |f(x,y,z)| \leq M
\\
&\text{Prove that }\exists  (x_0,y_0,z_0) \in B\,s.t.|\nabla f(x_0,y_0,z_0)| \leq 4M
\end{aligned}$$
**解**
我们考虑构造g(x,y,z)=f(x,y,z)+2M(x^2+y^2+z^2)-M.就像上面那一题一样满足题目条件的函数，然后用f(x,y,z)减去。通过g(0,0,0),和边界上的g说明存在最小值，但是若结论不成立则不会有偏导都为0的地方出现，导出矛盾。



3.
**题**
$$\begin{aligned}
&\text{Let} f(x,y) \text{be twice differentiable on }x^2 + y^2 \leq 1,\text{and } |f(x,y)| \leq 1
\\
&\text{Prove that } \exists(x_0,y_0) s.t.|f_{xx}(x_0,y_0)| + |f_{xy}(x_0,y_0)| + |f_{yy}(x_0,y_0)| \leq 12
\end{aligned}$$（焦点在二阶导界，使用类似辅助。）
**解**

这个题目给出的结论似乎太松了,用上一题一模一样的方法可以得到8的结果。

4.
**题**
$$\begin{aligned}
&\text{Let} f(x,y) \text{is partial differentiable on} [0,1] \times [0,1] \text{ and } |f(x,y)| \leq 1
\\
&
\text{Prove that }\exists (x_0,y_0) s.ts|\frac{\partial f}{\partial x}(x_0,y_0)|\le4\text{ and }|\frac{\partial f}{\partial y}(x_0,y_0)|\le4
\end{aligned}
$$
这个题目似乎也是太松的