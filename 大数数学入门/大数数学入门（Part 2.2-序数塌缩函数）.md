#! https://zhuanlan.zhihu.com/p/662616768
# 大数数学入门（Part 2.2-序数塌缩函数）

这一节我们开始讲序数塌缩函数。序数塌缩函数的定义与此前一系列Veblen函数的逐渐强化的定义不同，而在理解之后序数塌缩函数反而是更加自然的一种序数表示方式。不仅如此，虽然序数塌缩函数的定义较为复杂，但是在理解定义之后我们会发现它的计算是简单的。

---

## 序数塌缩函数的定义和性质

让我们首先给出一个版本的序数塌缩函数的定义：

1. $C_0(x) = \{0,1,\Omega\}$
2. $C_{n+1}(x) = C_{n}(x) \cup \{\alpha+\beta, \psi(\gamma) | \alpha, \beta, \gamma \in C_{n}(x), \gamma < x\}$
3. $C(x) = \bigcup_{n<\omega} C_n(x)$
4. $\psi(x) = \sup C(x) \cap \Omega = \sup \{\alpha \in C(x) | \alpha < \Omega\}$

这个定义第一眼看上去很复杂而且不知所云。让我们对于每一条规则逐一的分析：

规则1：$C_0(x) = \{0,1,\Omega\}$。对于任意的 $x$，$C_0(x) = \{0,1,\Omega\}$ 是同一个集合。这个集合可以理解成一个“种子”，或者理解成“初始状态”。

规则2：$C_{n+1}(x) = C_{n}(x) \cup \{\alpha+\beta, \psi(\gamma) | \alpha, \beta, \gamma \in C_{n}(x), \gamma < x\}$。这个规则递归的定义的 $C_{n+1}(x)$。$C_{n+1}(x)$ 是 $C_n(x)$，再加上 $C_{n}(x)$ 中通过加法和 $\psi$ 函数产生的元素，这里额外要求 $\psi$ 函数自变量小于 $x$，因为 $\psi(x)$ 是由 $C(x)$ 定义的。

规则3：$C(x) = \bigcup_{n<\omega} C_n(x)$。所有的 $C_n(x)$ 取并集得到的集合。这个集合就是由 $C_0(x)$ 出发，进行有限的加法和 $\psi$ 函数（自变量小于 $x$）操作得到的所有的序数。

规则4：$\psi(x) = \sup C(x) \cap \Omega = \sup \{\alpha \in C(x) | \alpha < \Omega\}$。$\psi(x)$ 被定义为 $C(x)$ 之中小于 $\Omega$ 的序数的上界，也就是由 $C_0(x)$ 出发，进行有限的加法和 $\psi$ 函数（自变量小于 $x$）操作得到的小于 $\Omega$ 序数的上界。

### $\psi$ 函数的一些特殊行为

让我们先试着计算一些值：

从 $\psi(0)$ 开始。因为没有任何序数小于 $0$，我们可以忽略规则2的 $\psi$ 函数：
$C_0(0) = \{0,1,\Omega\}$
$C_1(0) = \{0,1,2,\Omega,\Omega+1,\Omega2\}$
$C_2(0) = \{0,1,2,3,4,\Omega,\cdots\}$
省略号略去的是大于 $\Omega$ 的数，最后我们得到 $C(0)$，它包含了所有自然数，以及一些大于等于 $\Omega$ 的序数。

那么，$C(0)$ 中小于 $\Omega$ 的数的上界就是 $\omega$，它刚好就是由 $0$ 和 $1$ 通过有限的加法无法达到的数，$\psi(0) = \omega$。

然后是 $\psi(1)$，现在我们就可以将 $\psi(0)$ 加入集合了：
$C_0(1) = \{0,1,\Omega\}$
$C_1(1) = \{0,1,2,\omega,\Omega,\Omega+1,\Omega2\}$
$C_2(1) = \{0,1,2,3,4,\omega,\omega+1,\omega+2,\omega2,\Omega,\Omega+1,\Omega2\}$
最后的 $C(1)$ 包含了有限个 $\psi(0) = \omega$ 相加。$\psi(1) = \omega^2$

$\psi(2)$ 的计算中，我们将 $\psi(1)$ 包含于集合之内之内，$\psi(2)$ 就是有限个 $\psi(1)$ 相加所达不到的序数，也就是 $\psi(2) = \omega^3 = \psi(1) \omega$。

同理，$\psi(n) = \omega^n$

计算 $\psi(\omega)$ 时，我们在有限步内将任何的 $\psi(n)$ 加入集合，它们通过任何的加法组合都能达到 $\omega^\omega$ 以下的数，但是达不到它本身。因此，$\psi(\omega) = \omega^\omega$。

我们可以猜想，$\psi(x) = \omega^x$：
$\psi(\omega+1) = \psi(\psi(0)+1) = \omega^{\omega+1}$
$\psi(\omega2) = \psi(\psi(0)+\psi(0)) = \omega^{\omega+2}$
$\psi(\omega^2) = \psi(\psi(1)) = \omega^{\omega^2}$
$\psi(\omega^\omega) = \psi(\psi(\psi(0))) = \omega^{\omega^\omega}$
$\psi(\psi(\psi(\cdots))) = \omega^{\omega^\cdots} = \varepsilon_0 = \psi(\varepsilon_0)$

**注意：接下来的内容尤其重要。**

按照猜想，$\psi(\varepsilon_0+1) = \omega^{\varepsilon_0+1}$。
但是，我们注意到这样一个事实：$\varepsilon_0$ 没有被 $\psi$ 和加法有限的表示，也就是说，$\varepsilon_0$ 根本不会出现在 $C(\varepsilon_0+1)$ 之中，而对于它进行加法操作就更无从谈起了。$C(\varepsilon_0+1) = C(\varepsilon_0)$，因为即使允许 $\psi(\varepsilon_0)$ 的存在，$\varepsilon_0$ 也不会存在，$C(\varepsilon_0+1)$ 并没有加入任何的新东西。

也就是说 $\psi(\varepsilon_0+1) = \varepsilon_0$。
在此之后，$\psi(\varepsilon_0+2) = \varepsilon_0$，$\psi(\varepsilon_0+\omega) = \varepsilon_0$，$\cdots$。
我们因为 $\varepsilon_0$ 无法被有限的表示，而被卡在了 $\psi(x)$ 的第一个不动点。

这种情况一直持续下去，让我们计算 $\psi(\Omega)$。由于任何的小于 $\Omega$ 的 $\alpha$ 都有 $\psi(\alpha)\le \varepsilon_0$，$\psi(\Omega) = \varepsilon_0$，看起来我们依然被卡住了。

但是，在计算 $\psi(\Omega+1)$ 时，$\varepsilon_0 = \psi(\Omega)$ **是可以被有限表示的**，而 $\varepsilon_0$ 也将出现在 $C(\Omega+1)$ 中，我们有：$\psi(\Omega+1) = \varepsilon_0 \omega$，我们在 $\Omega$ 的帮助下跳出了这个不动点，而 $\psi$ 将 $\Omega$ 塌缩成 $\varepsilon_0$。

继续：
$\psi(\Omega+2) = \varepsilon_0 \omega^2$
$\psi(\Omega+\psi(0)) = \varepsilon_0 \omega^\omega$
$\psi(\Omega+\psi(\psi(0))) = \varepsilon_0 \omega^{\omega^\omega}$
$\psi(\Omega + \psi(\Omega)) = \psi(\Omega+\psi(\psi(\psi(\cdots)))) = \varepsilon_0^2$。我们这里并没有被卡住，因为 $\psi(\Omega)$ 是允许存在的。
$\psi(\Omega + \psi(\Omega)+\psi(\Omega)) = \varepsilon_0^3$
$\psi(\Omega + \psi(\Omega + 1)) = \varepsilon_0^{\omega}$
$\psi(\Omega + \psi(\Omega + 1) + \psi(\Omega + 1)) = \varepsilon_0^{\omega2}$
$\psi(\Omega + \psi(\Omega + 2)) = \varepsilon_0^{\omega^2}$
$\psi(\Omega + \psi(\Omega + \psi(0))) = \varepsilon_0^{\omega^\omega}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega))) = \varepsilon_0^{\varepsilon_0}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega) + 1)) = \varepsilon_0^{\varepsilon_0\omega}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega) + \psi(\Omega))) = \varepsilon_0^{\varepsilon_0^2}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega + 1))) = \varepsilon_0^{\varepsilon_0^\omega}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega + \psi(0)))) = \varepsilon_0^{\varepsilon_0^{\omega^\omega}}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega + \psi(\Omega)))) = \varepsilon_0^{\varepsilon_0^{\varepsilon_0}}$

$\psi(\Omega + (1,0)) = \varepsilon_1$，这里使用了弱Veblen模式的记号作为不动点的简写，而这个序数并没有被有限的表达。也就是说 $\psi(\Omega + \varepsilon_1) = \varepsilon_1$, $\varepsilon_1 = \psi(\Omega+\varepsilon_1 + 1) = \psi(\Omega+\varepsilon_1 + 2) = \cdots$，最后，我们再一次引入 $\Omega$ 去将不动点的有限运算折叠成一个运算：$\psi(\Omega2) = \psi(\Omega + \Omega) = \varepsilon_1$。

我们可以总结一下一个不严格的 OCF 的计算方式：

1. $\psi(0) = \omega$
2. $\psi(\alpha+1) = \psi(\alpha)\omega$，如果 $\psi(\alpha)$ 是一个被有限表达的序数。
3. $\psi(\# \sim \Omega) = \psi(\# \sim (1,0))$，其中 $\#$ 是一个表达式，$\#\sim \Omega$ 表示这个表达式的末端是 $\Omega$。这个规则解释起来就是“如果表达式的末端是 $\Omega$，它所折叠的便是将 $\Omega$ 变成自变量产生的函数的首个不动点。

### $\psi$ 函数的枚举

$\psi(0) = \omega$
$\psi(1) = \omega^2$
$\psi(2) = \omega^3$
$\psi(\omega) = \omega^\omega$
$\psi(\psi(0)+1) = \omega^{\omega+1}$
$\psi(\psi(0)+\psi(0)) = \omega^{\omega+2}$
$\psi(\psi(1)) = \omega^{\omega^2}$
$\psi(\psi(\psi(0))) = \omega^{\omega^\omega}$
$\psi(\Omega) = \psi((1,0)) = \varepsilon_0$
$\psi(\Omega+1) = \varepsilon_0 \omega$
$\psi(\Omega+2) = \varepsilon_0 \omega^2$
$\psi(\Omega+\psi(0)) = \varepsilon_0 \omega^\omega$
$\psi(\Omega+\psi(\psi(0))) = \varepsilon_0 \omega^{\omega^\omega}$
$\psi(\Omega + \psi(\Omega)) = \varepsilon_0^2$
$\psi(\Omega + \psi(\Omega)+ \psi(\Omega)) = \varepsilon_0^3$
$\psi(\Omega + \psi(\Omega + 1)) = \varepsilon_0^{\omega}$
$\psi(\Omega + \psi(\Omega + 1) + \psi(\Omega + 1)) = \varepsilon_0^{\omega2}$
$\psi(\Omega + \psi(\Omega + 2)) = \varepsilon_0^{\omega^2}$
$\psi(\Omega + \psi(\Omega + \psi(0))) = \varepsilon_0^{\omega^\omega}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega))) = \varepsilon_0^{\varepsilon_0}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega) + 1)) = \varepsilon_0^{\varepsilon_0\omega}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega) + \psi(\Omega))) = \varepsilon_0^{\varepsilon_0^2}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega + 1))) = \varepsilon_0^{\varepsilon_0^\omega}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega + \psi(0)))) = \varepsilon_0^{\varepsilon_0^{\omega^\omega}}$
$\psi(\Omega + \psi(\Omega + \psi(\Omega + \psi(\Omega)))) = \varepsilon_0^{\varepsilon_0^{\varepsilon_0}}$
$\psi(\Omega2) = \psi(\Omega + (1,0)) = \varepsilon_1$
$\psi(\Omega2 + 1) = \varepsilon_1 \omega$
$\psi(\Omega2 + \psi(\Omega)) = \varepsilon_1 \varepsilon_0$
$\psi(\Omega2 + \psi(\Omega2)) = \varepsilon_1^2$
$\psi(\Omega2 + \psi(\Omega2+1)) = \varepsilon_1^\omega$
$\psi(\Omega2 + \psi(\Omega2+\psi(\Omega))) = \varepsilon_1^{\varepsilon_0}$
$\psi(\Omega2 + \psi(\Omega2+\psi(\Omega2))) = \varepsilon_1^{\varepsilon_1}$
$\psi(\Omega2 + \psi(\Omega2+\psi(\Omega2+\psi(\Omega2)))) = \varepsilon_1^{\varepsilon_1^{\varepsilon_1}}$
$\psi(\Omega3) = \psi(\Omega2 + (1,0)) = \varepsilon_2$
$\psi(\Omega4) = \psi(\Omega2 + (1,0)) = \varepsilon_3$
$\psi(\Omega \omega) = \psi(\Omega + \Omega + \cdots) = \varepsilon_\omega$

我们到此为止了，因为 $\Omega\omega = \Omega + \Omega + \cdots$ 也是不能由有限次加法得到的，因此不会出现在 $C$ 中，此后的函数值都不会变化了。

此外，$\Omega3$ 这样的写法并不是标准的写法，想要标准的表达它需要写成 $\Omega+\Omega+\Omega$，因此在构造 $C$ 的过程中并没有乘法的出现。

## 关于本章节的一些评论

到此为止，我们仅仅到达了 $\psi(\Omega \omega) = \varphi(1,\omega)$ 就停住了，但是序数塌缩函数引入了一个全新的表达大序数的方法：我们使用越来越高层级的非递归序数来塌缩成越来越复杂的递归序数。在下一节中，我们将引入 $\Omega_2$ 之后的非递归序数，从此之后我们就能看到序数塌缩函数的强大之处。

此外，序数塌缩函数可以通过修改定义产生不同的小版本。
在一些版本中，$\psi(\alpha+1) = \psi(\alpha)+1$。在另一些版本中，$\psi(\alpha+1) = \psi(\alpha)\uparrow\uparrow \omega$。我们此后会发现其实这些定义只会在函数的最开始的一些地方拉开差距，在到达某一个点之后，函数之间的差距会被抹平。在看到使用 OCF 进行符号分析的时候，请留心观察使用的 OCF 的版本和行为。