这个证明参考了 <https://thecuriousastronomer.wordpress.com/2017/09/12/derivation-of-relativistic-mass/>

使用这个证明中的设计，但是注意，我设置的是S'系关于S系以V速度向右运动。

![使用的条件](https://thecuriousastronomer.files.wordpress.com/2017/09/pagesscreensnapz002-1.jpg)

这组条件是由$V$和$u_0$所唯一确定的，其余的量皆可由之导出。

我们在$S'$系中来考察这个问题

由于对称关系，可以得到$$u_{(Red, S, y)}y=u_{(Blue, S', y)}$$ $$u_{(Red, S, x)}=u_{(Blue, S', x)}$$于是可以将二者分别记为$u_x$，$u_y$

我们将$\frac{1}{\sqrt{1-\beta^2}}$记为$\lambda$

由y方向的洛伦兹变换可知，$$u_y = \frac{1}{\lambda}u_0$$由x方向的洛伦兹变换可知，$$u_x = V$$

因此，在S'系中a的速度$u_a$为$\sqrt{V^2 + (\frac{u_0}{λ})^2}$

我们考虑y方向上的动量守恒：$$m(u_0)(-u_0) + m(u_a)\frac{u_0}\lambda = m(u_0)u_0 + m(u_a)(-\frac{u_0}\lambda)$$

整理得到 $$\frac{m(u_a)}{m(u_0)} = \lambda$$

即对任意的$u_0$有$$\frac{m(\sqrt{V^2 + (\frac{u_0}{\lambda})^2)})}{m(u_0)} = \lambda$$

我们取$u_0 = 0$ ，得到 $$\frac{m(V)}{m_0} = lambda$$

即 $m(V) = m_0\lambda$

QED.