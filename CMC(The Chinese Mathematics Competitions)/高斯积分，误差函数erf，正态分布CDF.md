高斯积分：
$$
\int_{-\infty}^{+\infty}e^{-x^2}\,dx=\sqrt{\pi}
$$
$$
\int_{-\infty}^{+\infty}e^{-ax^2}\,dx=\int_{-\infty}^{+\infty}e^{-t^2} \frac{1}{\sqrt{a}}dt=\frac{\sqrt{\pi}}{\sqrt{a}}$$
$$\int_{-\infty}^{+\infty}e^{-ax^2+bx}\,dx$$这种的顶上配个方就可以了


$$\int_{-\infty}^{+\infty}x^{2n}e^{-ax^3}\,dx$$
这个东西从原来式子对a求导可以解得(注意，这个求导本质就是之前那个连带着积分上下限也出来的二元函数的求导),以此类推来解决问题
$$F(a)=\int_{-\infty}^{+\infty}e^{-ax^2}\,dx=\sqrt{\frac{\pi}{a}},F'(a)=\int_{-\infty}^{+\infty}(-x^2)e^{-ax^2}\,dx=-\frac{1}{2}\sqrt{\frac{\pi}{a^3}}$$


$$erf(x)=\frac{2}{\sqrt{\pi}}\int_{0}^{x}e^{-t^2}\,dt$$
$$\Phi(x)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{x}e^{-t^2}\,dt$$