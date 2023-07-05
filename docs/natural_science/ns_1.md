> 这个也发在了b站上 <https://www.bilibili.com/read/cv23441835>

在看[http://matematicas.uam.es/~mavi.melian/CURSO_15_16/web_Discreta/recurrence.pdf]的证明的时候，发现作者在Proof of Theorem 2中并未给出
$$\sum_{k=0}^{d+1} \binom{d+1}{k}(-1)^kq(n-k)=0$$
的证明（其中d为多项式$q(x)$的阶数，n为任意数）

我并不清楚这个式子是否是什么已有的定理，也并不知道如何直接搜数学表达式，所以简单证明了一下。（可能不够严谨，仅供参考）

首先，可以将q(x)写成
$$q(x)=\alpha (x^d+a_1x^{d-1} …+a_d)$$

考虑所求证式的左侧，可以将α提出求和之外，由于α不为0，仅需考虑求和号内部。而
$$\frac{1}{\alpha}q(n-k) = (n-k)^d+a_1(n-k)^d-1…+a_d$$

展开后得到（以d维多项式空间的常用基表示）
$$\frac{1}{\alpha}q(n-k) = [n^d,n^{d-1},…,1] * \begin{bmatrix}\binom{d}{0}(-k)^d\\\\ \binom{d}{1}(-k)^{b-1}+a_1\binom{d-1}{0}(-k)^{b-1}\\\\……\\\\\binom{d}{d}(-k)^0+a_1\binom{d-1}{d-1}(-k)^0+…+a_d\binom{0}{0}(-k)^0\end{bmatrix}$$

我们可以发现
$$\binom{d}{0},\binom{d}{1}+a_1\binom{d-1}{0},…,\binom{d}{d}+a_1\binom{d-1}{d-1}+…+a_d\binom{0}{0}$$

都是常数。

要证所求证，就需要证
$$\sum_{k=0}^{d+1} \binom{d+1}{k}(-1)^kq(n-k)= [n^d,n^{d-1},…,1] * \mathbf O$$

因此只需要证
$$\forall m\leq d, \sum_{k=0}^{d+1}\binom{d+1}{k}(-1)^k(-k)^m=0$$

即可，使用数学归纳法 
$$m=0,\sum_{k=0}^{d+1}\binom{d+1}{k}(-1)^k1^{d+1-k}=(-1+1)^d+1=0$$ 
$$d=0,\sum_{k=0}^1\binom{1}{k}(-1)^k\times 1=0$$
先考虑对于d的第一数学归纳法，如果在0-(d-1)上原命题都成立，那么考察d处：

在此处，考虑m的第一数学归纳法，如果在m上原命题成立，那么考察m+1处：

记$F(d,m)=\sum_{k=0}^{d+1}\binom{d+1}{k}(-1)^k(-k)^m$，则$\forall d_0\leq d,m_0\leq m,F(d_0,m_0)=0$

那么m+1处：
$$F(d,m+1)=\binom{d+1}{0}(-1)^00^{m+1}+\sum_{k=1}^{d+1} \frac{(d+1)!}{k!(d+1-k)!}(-1)^k(-k)^m(-k)$$ 
$$F(d,m+1)=\sum_{k=1}^{d+1} \frac{d!}{(k-1)!(d+1-k)!}(-1)^k(-k)^m\times -(d+1)$$ 
$$F(d,m+1)=\sum_{k=0}^{(d-1)+1} \binom{(d-1)+1}{k}(-1)^k(-k-1)^m(d+1)$$ 

将$(-k-1)^m$展开
$$\frac{F(d,m+1)}{d+1}=\binom{m}{0}F(d-1,m)(-1)^0+\binom{m}{1}F(d-1,m-1)(-1)^1+…+\binom{m}{m}F(d-1,0)(-1)^m$$

由假设可以得到，$F(d, m+1)=0$

因此，m+1处假设成立，故对所有的$m\leq d$假设F(d,m)成立即在d处，原命题也成立。

综上$\forall d\forall m\leq d,F(d,m)=0$

QED.