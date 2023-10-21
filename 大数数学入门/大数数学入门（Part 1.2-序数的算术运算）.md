#! https://zhuanlan.zhihu.com/p/661658857
# 大数数学入门（Part 1.2-序数的算术运算、不动点）

在上一节中，我们提到了序数和FGH的定义。从这一节开始，我们就会开始了解越来越大的序数的表示方法。

---

## 序数的算术运算

让我们从序数的后继开始：$S(\alpha) = \alpha \cup \{\alpha\}$。

和此前我们对于自然数所做的事情一样，我们定义加法为后继的重复：

1. $\alpha + 0 = \alpha$
2. $\alpha + S(\beta) = S(\alpha+\beta)$
3. 若$\beta$是极限序数，$\alpha + \beta = \sup_{\gamma < \beta} \alpha + \gamma$。同时，定义基本列$(\alpha+\beta)[n] = \alpha + \beta[n]$。

定义乘法为加法的重复（有时乘法的符号会被省略）：

1. $\alpha \times 0 = 0$
2. $\alpha \times S(\beta) = \alpha \times \beta + \alpha$
3. 若$\beta$是极限序数，$\alpha \times \beta = \sup_{\gamma < \beta} \alpha \times \gamma$。同时，定义基本列$(\alpha\times \beta)[n] = \alpha \times \beta[n]$。

定义指数为乘法的重复：

1. $\alpha^0 = 1$
2. $\alpha ^{S(\beta)} = \alpha^\beta \times \alpha$
3. 若$\beta$是极限序数，$\alpha^\beta = \sup_{\gamma < \beta} \alpha^\gamma$。同时，定义基本列$(\alpha^\beta)[n] = \alpha^{\beta[n]}$。

定义$\omega$的基本列：$\omega[n] = n$。

注意，在自然数的算术中，加法、乘法是满足交换律，但是这里不一定满足，例如$2 + \omega = \sup_{n<\omega} 2+n = \omega$，但是$\omega+2 = S(S(\omega))$，它们并不相等。

在像自然数一样定义高阶运算和超运算之前，让我们先枚举一下目前的序数。

## 枚举

$0$
$1$
$2$
$\omega = \sup\{0,1,2\cdots\}$
$\omega + 1$
$\omega + 2$
$\omega2 = \omega+\omega = \sup\{\omega, \omega+1, \omega+2, \cdots\}$
$\omega2+1$
$\omega3 = \omega2+\omega$
$\omega^2 = \omega \times \omega = \sup\{0, \omega, \omega2, \omega3, \cdots\}$
$\omega^2+1$
$\omega^2+\omega$
$\omega^22$
$\omega^3$
$\omega^4$
$\omega^\omega = \sup\{1, \omega, \omega^2, \omega^3, \cdots\}$
$\omega^{\omega+1} = \omega^\omega \times \omega$
$\omega^{\omega+2}$
$\omega^{\omega2}$
$\omega^{\omega^2}$
$\omega^{\omega^\omega}$
$\omega^{\omega^{\omega^\omega}}$
$\cdots$
最后，我们到达极限 $\varepsilon_0 = \sup\{0, 1, \omega, \omega^\omega, \omega^{\omega^\omega}, \cdots\}$ ，在它之前的序数都是可以用此前的序数运算得到的，而它本身不行。

## 指数不动点

我们发现，指数运算对于 $\varepsilon_0$ 不管用了：

$$
\omega^{\varepsilon_0} = \sup\{1, \omega, \omega^\omega, \omega^{\omega^\omega}, \cdots\} = \varepsilon_0
$$

也就是说，$\varepsilon_0$ 是 $\alpha \mapsto \omega^\alpha$ 的第 $0$ 个不动点。这样的不动点性质在自然数的算术运算中是见不到的： $x\mapsto 2^x$ 并没有一个有限的不动点。

但是 $\varepsilon_0$ 并不是终点，对于任何一个序数，它的后继一定比它大，$\varepsilon_0+1$ 也不例外。在此后：
$\omega^{\varepsilon_0+1} = \omega^\varepsilon_0 \times \omega = \varepsilon_0\omega$
$\omega^{\omega^{\varepsilon_0+1}} = \omega^{\varepsilon_0 \omega} = \varepsilon_0^\omega$
$\omega^{\omega^{\omega^{\varepsilon_0+1}}} = \omega^{\varepsilon_0^\omega} = \omega^{\varepsilon_0 \times \varepsilon_0^\omega} = \varepsilon_0^{\varepsilon_0^\omega}$
我们确实跳出了这个$\varepsilon_0$指数不动点，最后达到了另一个指数不动点：
$$
\varepsilon_1 = \sup\{\varepsilon_0+1, \omega^{\varepsilon_0+1}, \omega^{\omega^{\varepsilon_0+1}}, \cdots\} = \sup\{\varepsilon_0+1, \varepsilon_0\omega, \varepsilon_0^\omega, \varepsilon_0^{\varepsilon_0^\omega}, \cdots\}
$$

> 对于$\varepsilon_1$的基本列有另一个定义：$\sup\{\varepsilon_0, \varepsilon_0^{\varepsilon_0}, \varepsilon_0^{\varepsilon_0^{\varepsilon_0}}, \cdots\}$。从上文中我们可以看见两种定义等价。在对于各种符号的分析中，后一种标准列也是相当常用的，而本系列文章中也会使用这样的定义。

同样的，我们定义了 $\varepsilon_1$ 之后，它的指数不动点就是 $\varepsilon_2 = \sup \{\varepsilon_1, \varepsilon_1^{\varepsilon_1}, \varepsilon_1^{\varepsilon_1^{\varepsilon_1}}, \cdots\}$ 。

我们可以继续枚举了：

$\varepsilon_0$
$\varepsilon_0+1$
$\varepsilon_0\times 2$
$\varepsilon_0^\omega$
$\varepsilon_0^{\varepsilon_0}$
$\varepsilon_0^{\varepsilon_0^{\varepsilon_0}}$
$\varepsilon_1$
$\varepsilon_1^{\varepsilon_0}$
$\varepsilon_1^{\varepsilon_1}$
$\varepsilon_1^{\varepsilon_1^{\varepsilon_1}}$
$\varepsilon_2$
$\varepsilon_2^{\varepsilon_2}$
$\varepsilon_2^{\varepsilon_2^{\varepsilon_2}}$
$\varepsilon_3$
$\varepsilon_4$
$\cdots$
$\varepsilon_\omega = \sup\{\varepsilon_0, \varepsilon_1, \varepsilon_2, \cdots\}$

这样，我们就达到了 $\varepsilon_\omega$ ，它是之前的指数不动点的上确界。

我们可以沿用之前的超限递归定义的思路，去定义一个 $\varepsilon$ 函数：

1. $\varepsilon_0 = \sup\{1, \omega, \omega^\omega, \cdots\}$ 
2. $\varepsilon_{\alpha+1} = \sup\{1, \varepsilon_\alpha, \varepsilon_\alpha^{\varepsilon_\alpha}, \cdots\}$
3. 若 $\beta$ 是极限序数，那么 $\varepsilon_\beta = \sup_{\gamma < \beta} \varepsilon_\gamma$

在定义了这三种情况之后，我们便能在任何情况下表示出 $\varepsilon_\alpha$ 的值。继续枚举：

$\varepsilon_{\omega+1}$
$\varepsilon_{\omega2}$
$\varepsilon_{\omega^\omega}$
$\varepsilon_{\varepsilon_0}$
$\varepsilon_{\varepsilon_{\varepsilon_0}}$

我们到达了一个新的不动点：

$\text{Cantor's Ordinal} = \zeta_0 = \sup\{0, \varepsilon_0, \varepsilon_{\varepsilon_0}, \varepsilon_{\varepsilon_{\varepsilon_0}}, \cdots\}$

和 $\varepsilon_0$ 不能被它之下的数通过后继、加法、乘法和指数有限的表示一样， $\zeta_0$ 不能被它之下的数通过后继、加法、乘法、指数、和 $\varepsilon$ 函数有限的表示。

## 高阶不动点

注意到 $\zeta_0 = \varepsilon_{\zeta_0}$，我们可以得到 $\varepsilon_{\zeta_0+1}$ ，它是 $\zeta_0$ 的指数塔。在我们有了 $\zeta_0$ 之后，我们自然可以得到它之后的下一个 $\varepsilon$ 不动点：

$\zeta_1 = \sup\{\zeta_0+1, \varepsilon_{\zeta_0+1}, \varepsilon_{\varepsilon_{\zeta_0+1}}, \varepsilon_{\varepsilon_{\varepsilon_{\zeta_0 + 1}}}, \cdots\}$

然后，像定义 $\varepsilon$ 函数一样，我们可以定义一个 $\zeta$ 函数，表示第 $\alpha$ 个 $\varepsilon$ 不动点，它的不动点定义了一个新的值 $\eta_0$ 。

同样的，像定义 $\zeta$ 函数一样，我们可以定义一个 $\eta$ 函数，表示第 $\alpha$ 个 $\zeta$ 不动点，它的不动点定义了一个新的值 $\xi_0$ 。

......

希腊字母是有限的，我们用 $\varphi(1, x)$ 表示 $\varepsilon_x$，用 $\varphi(2, x)$ 表示 $\zeta_x$，用 $\varphi(3, x)$ 表示 $\eta_x$，我们可以同样的、重复的定义任意一个 $\varphi(n, x) (n<\omega)$，它是之前的 $\varphi(m, \cdot) (m<n)$ 的第 $x$ 个不动点。

继续枚举：

$\varphi(2,0) = \zeta_0$
$\varphi(1, \varphi(2,0)+1) = \varepsilon_{\zeta_0+1}$
$\varphi(1, \varphi(1, \varphi(2,0)+1)) = \varepsilon_{\varepsilon_{\zeta_0+1}}$
$\varphi(2,1) = \zeta_1$
$\varphi(1, \varphi(2,1)+1) = \varepsilon_{\zeta_1+1}$
$\varphi(2,2) = \zeta_2$
$\varphi(2,3) = \zeta_3$
$\varphi(2,\omega) = \zeta_\omega$
$\varphi(2,\varphi(1,0)) = \zeta_{\varepsilon_0}$
$\varphi(2, \varphi(2,0)) = \zeta_{\zeta_0}$
$\varphi(2, \varphi(2,\varphi(2, 0))) = \zeta_{\zeta_{\zeta_0}}$
$\varphi(3, 0) = \eta_0$
$\varphi(1, \varphi(3, 0)+1)$
$\varphi(2, \varphi(3, 0)+1)$
$\varphi(3, 1)$
$\varphi(3, \varphi(1, 0))$
$\varphi(3, \varphi(2, 0))$
$\varphi(3, \varphi(3, 0))$
$\varphi(3, \varphi(3, \varphi(3, 0)))$
$\varphi(4, 0)$
$\varphi(5, 0)$
......

最后我们达到的序数 $\alpha$，是$\varphi(n, x) (n<\omega)$的不动点。

这实际上是二元Veblen函数的定义的一部分。对于第一个变量在极限序数的情况的定义，就是下一节的事情了。