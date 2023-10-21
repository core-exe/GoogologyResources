#! https://zhuanlan.zhihu.com/p/662657981
# 大数数学入门（Part 2.3-第二个非递归序数）

## 定义

如果没有 $\psi$ 和 $\Omega$，从 $\{0,1\}$ 出发进行有限次加法无法达到 $\omega$。类似的，在上一章的结尾，我们达到了 $\Omega \omega$，从 $\{0,1,\Omega\}$ 开始进行有限次加法无法达到它。
因此，我们也可以像上一章所做的事情一样，引入另一个非递归序数 $\Omega_2$ 和另一个序数塌缩函数 $\psi_1$ 来表示 $\Omega$ 之后的更为复杂的结构：

1. $C_0^0(x) = \{0,1,\Omega,\Omega_2\}, C_0^1(x) = \Omega \cup \{\Omega_2\}$
2. $C_{n+1}^i(x) = \{\alpha+\beta, \psi(\gamma), \psi_1(\gamma) | \alpha,\beta,\gamma \in C_n^i(x), \gamma < x\}$
3. $C^i(x) = \bigcup_{n<\omega} C_n^i(x)$
4. $\psi(x) = \sup C^0(x) \cap \Omega$
5. $\psi_1(x) = \sup C^1(x) \cap \Omega_2$

我们引入了非递归序数 $\Omega_2$，和塌缩函数 $\psi_1$。与 $\psi$ 不同，$\psi_1$ 输出的是 $C^1(x)$ 在 $\Omega_2$ 之下的部分的上界。

## 函数行为

让我们注意一下新定义下的 $\psi$ 函数和 $\psi_1$ 函数的行为。

$C^0(0) = \{0,1,2,\cdots, \Omega,\Omega2,\Omega3, \cdots, \Omega_2,\Omega_2 2 \cdots\}$ （这里并没有完全列举集合中的值），因此 $\psi(0) = \omega$。
$C^1(0) = \{\cdots, \Omega,\Omega2,\Omega3, \cdots, \Omega_2,\Omega_2 2 \cdots\}$ （这里并没有完全列举集合中的值），因此 $\psi_1(0) = \Omega \omega$。

$C^0(1)$ 将 $\omega, \Omega\omega$ 加入其中，有 $\psi(1) = \omega^2$
$C^1(1)$ 将 $\Omega\omega$ 加入其中，有 $\psi_1(1) = \Omega\omega^2$

$\psi(\omega) = \omega^\omega, \psi_1(\omega) = \Omega \omega^\omega$

$\psi(\psi(\cdots)) = \varepsilon_0, \psi_1(\psi(\psi(\cdots))) = \psi_1(\varepsilon_0) = \Omega \varepsilon_0$。前者卡住了，但是后者没有，因为按照定义，$C_1$ 含有小于 $\Omega$ 的所有数。

$\psi(\Omega) = \varepsilon_0, \psi_1(\Omega) = \Omega^2$

$\psi(\Omega2) = \varepsilon_1, \psi_1(\Omega 2) = \Omega^3$
$\psi(\Omega3) = \varepsilon_2, \psi_1(\Omega 3) = \Omega^4$

现在的行为也还和此前一致。这种情况下一直持续到 $\Omega \omega$。$\psi_1(0) = \Omega \omega$ 从 $x=1$ 开始就被放入集合 $C(x)$ 中了，但是此前由于 $x < \Omega \omega$，它没有办法成为 $\psi(\gamma)$ 的自变量，但是从现在开始情况就不一样了：

$\psi(\psi_1(0)) = \psi(\Omega \omega)$
$\psi(\psi_1(0) + 1) = \psi(\Omega \omega) \omega$
$\psi(\psi_1(0) + \omega) = \psi(\Omega \omega) \omega^\omega$
$\psi(\psi_1(0) + \psi(0)) = \psi(\Omega \omega) \psi(0)$
$\psi(\psi_1(0) + \psi(\Omega)) = \psi(\Omega \omega) \psi(\Omega)$
$\psi(\psi_1(0) + \psi(\psi_1(0))) = \psi(\Omega \omega + \psi(\Omega \omega)) = \psi(\Omega \omega)^2$
$\psi(\psi_1(0) + \psi(\psi_1(0) + 1)) = \psi(\Omega \omega + \psi(\Omega \omega + 1)) = \psi(\Omega \omega)^\omega$
$\psi(\psi_1(0) + \psi(\psi_1(0) + 2)) = \psi(\Omega \omega + \psi(\Omega \omega + 2)) = \psi(\Omega \omega)^{\omega^2}$
$\psi(\psi_1(0) + \psi(\psi_1(0) + \psi(0))) = \psi(\Omega \omega + \psi(\Omega \omega + \psi(0))) = \psi(\Omega \omega)^{\omega^\omega}$
$\psi(\psi_1(0) + \psi(\psi_1(0) + \psi(\Omega))) = \psi(\Omega \omega + \psi(\Omega \omega + \psi(\Omega))) = \psi(\Omega \omega)^{\psi(0)}$
$\psi(\psi_1(0) + \psi(\psi_1(0) + \psi(\psi_1(0)))) = \psi(\Omega \omega + \psi(\Omega \omega + \psi(\Omega \omega))) = \psi(\Omega \omega)^{\psi(\Omega \omega)}$
$\psi(\psi_1(0) + \psi(\psi_1(0) + \psi(\psi_1(0)+1))) = \psi(\Omega \omega + \psi(\Omega \omega + \psi(\Omega \omega+1))) = \psi(\Omega \omega)^{\psi(\Omega \omega)^\omega}$
$\psi(\psi_1(0)+(1,0)) = \psi(\psi_1(0) + \Omega) = \psi(\Omega \omega + \Omega)$
这是 $\Omega \omega$ 之后的第一次用 $\Omega$ 折叠不动点。$\Omega$ 的折叠作用依然存在。

到现在为止，依然只有 $\psi_1(0) = \Omega \omega$ 能够被放进自变量中。
$\psi(\psi_1(0) + \Omega 2) = \psi(\Omega \omega + \Omega 2) = \psi(\psi_1(0)+\Omega + (1,0))$
$\psi(\psi_1(0) + \Omega 3) = \psi(\Omega \omega + \Omega 3) = \psi(\psi_1(0)+\Omega2 + (1,0))$
$\psi(\psi_1(0) 2) = \psi(\Omega \omega 2)$
$\psi(\psi_1(0) 3) = \psi(\Omega \omega 3)$
$\psi(\psi_1(1)) = \psi(\Omega \omega^2)$

从此之后，$\psi_1(1) = \Omega \omega^2$ 也可以成为 $\psi$ 的自变量，它可以被有限表示了。

$\psi(\psi_1(1) + \Omega) = \psi(\Omega \omega^2 + \Omega)$
$\psi(\psi_1(1) + \psi_1(0)) = \psi(\Omega \omega^2 + \Omega \omega)$
$\psi(\psi_1(1) 2) = \psi(\Omega \omega^2 2)$
$\psi(\psi_1(2)) = \psi(\Omega \omega^3)$
$\psi(\psi_1(\psi(0))) = \psi(\Omega \omega^\omega)$
$\psi(\psi_1(\psi(\Omega))) = \psi(\Omega \psi(\Omega))$
$\psi(\psi_1(\psi(\psi_1(0)))) = \psi(\Omega \psi(\Omega \omega))$
$\psi(\psi_1(\psi(\psi_1(1)))) = \psi(\Omega \psi(\Omega \omega^2))$
$\psi(\psi_1(\psi(\psi_1(\psi(\Omega))))) = \psi(\Omega \psi(\Omega \psi(\Omega)))$
$\psi(\psi_1(\psi(\psi_1(\psi(\psi_1(0)))))) = \psi(\Omega \psi(\Omega \psi(\Omega \omega)))$

$\psi(\psi_1((1,0)))$ 无法被有限表示，它会被折叠成 $\psi(\psi_1(\Omega)) = \psi(\Omega^2)$。

$\psi(\psi_1(\Omega + 1)) = \psi(\Omega^2 \omega)$
$\psi(\psi_1(\Omega 2)) = \psi(\Omega^3)$
$\psi(\psi_1(\psi_1(0))) = \psi(\Omega^\omega)$
$\psi(\psi_1(\psi_1(0) + 1)) = \psi(\Omega^\omega \omega)$
$\psi(\psi_1(\psi_1(0) + \Omega)) = \psi(\Omega^{\omega+1})$
$\psi(\psi_1(\psi_1(0)2)) = \psi(\Omega^{\omega2})$
$\psi(\psi_1(\psi_1(1))) = \psi(\Omega^{\omega^2})$
$\psi(\psi_1(\psi_1(\psi(0)))) = \psi(\Omega^{\omega^\omega})$
$\psi(\psi_1(\psi_1(\psi(\Omega)))) = \psi(\Omega^{\psi(\Omega)})$
$\psi(\psi_1(\psi_1(\psi(\psi_1(0))))) = \psi(\Omega^{\psi(\Omega \omega)})$
$\psi(\psi_1(\psi_1(\psi(\psi_1(\psi_1(0)))))) = \psi(\Omega^{\psi(\Omega^\omega)})$
$\psi(\psi_1(\psi_1(\Omega))) = \psi(\Omega^\Omega)$

同样的，折叠不动点。

我们继续下去，就会达到这个地方：

$\psi(\psi_1(\psi_1(\psi_1(\cdots))))$。它无法被有限的表示，我们把 $\psi_1((1,0))$ 叫做 $x$，那么 $\psi_1(x) = x$，此后 $\psi_1(x+1) = \psi_1(x+2) = \cdots = \psi_1(\Omega_2) = x$，它在 $\Omega_2$ 之前不可以被有限表示，而 $\Omega_2$ 折叠的是 $\psi_1$ 的不动点。

那么 $\psi(\psi_1(\Omega_2)+1)$ 是否就是 $\psi(\psi_1(\Omega_2)) \omega$ 了？并不是。在计算 $\psi(\psi_1(\Omega_2)+1)$ 时，$\Omega_2$ 依然无法被放入 $\psi$ 和 $\psi_1$ 中，而 $\psi_1(\Omega_2)$ 的值也是不会出现在 $C(x)$ 中的，$\psi(\psi_1(\Omega_2)+1) = \psi(\psi_1(\Omega_2))$。这种情况将一直保持，直到 $\psi(\Omega_2) = \psi(\psi_1(\Omega_2))$，在它之后的 $\psi(\Omega_2 + 1) = \psi(\Omega_2)\omega$。

$\psi(\Omega_2) = \psi(\psi_1(\Omega_2))$
$\psi(\Omega_2+1)$
$\psi(\Omega_2+\psi(0))$
$\psi(\Omega_2+\psi(\Omega_2))$
$\psi(\Omega_2+\psi(\Omega_2 + \psi(\Omega_2)))$
$\psi(\Omega_2+\Omega)$
$\psi(\Omega_2+\Omega2)$
$\psi(\Omega_2+\psi_1(0))$
$\psi(\Omega_2+\psi_1(1))$
$\psi(\Omega_2+\psi_1(\psi(0)))$
$\psi(\Omega_2+\psi_1(\Omega))$
$\psi(\Omega_2+\psi_1(\psi_1(0)))$
$\psi(\Omega_2+\psi_1(\psi_1(\psi_1(0))))$
$\psi(\Omega_2+\psi_1(\Omega_2))$
$\psi(\Omega_2+\psi_1(\Omega_2 + 1))$
$\psi(\Omega_2+\psi_1(\Omega_2 + \Omega))$
$\psi(\Omega_2+\psi_1(\Omega_2 + \psi_1(\Omega_2)))$
$\psi(\Omega_2+\psi_1(\Omega_2 + \psi_1(\Omega_2 + \psi_1(\Omega_2))))$
$\psi(\Omega_2 2)$

注意它的展开与 $\psi(\Omega_2 + \Omega)$ 展开的区别。$\Omega$ 展开的是 $\psi$ 的不动点，而 $\Omega_2$ 展开的是 $\psi_1$ 的不动点。此后，由于 $\psi(\Omega_2 + \psi_1(\Omega_2 2) + 1)$ 中，$\psi_1(\Omega_2 2)$ 并不能被有限表示，整个函数被卡到了 $\psi(\Omega_2 2)$。

继续下去，最后我们达到了 $\psi(\Omega_2 \omega)$，再向前就无法增加了，原因与上一节末尾讲到的相同。

同样，我们来归纳一下一个不严谨的计算规则：

1. $\psi(0) = \omega$
2. $\psi(\alpha+1) = \psi(\alpha)\omega$，如果 $\psi(\alpha)$ 的形式标准，也就是可以被有限表达。
3. $\psi(\# \sim \Omega) = \psi(\# \sim \psi(\# \sim \psi(\# \sim \cdots)))$，其中 $\#$ 是一个表达式，$\#\sim \Omega$ 表示这个表达式的末端是 $\Omega$。这个规则解释起来就是“如果表达式的末端是 $\Omega$，它所折叠的便是将 $\Omega$ 变成自变量产生的函数的首个不动点。
4. $\psi(\# \sim \Omega_2) = \psi(\# \sim \psi_1(\# \sim \psi_1(\# \sim \cdots)))$。如果表达式的末端是 $\Omega_1$，它将展开一个 $\psi_1$ 形成的不动点。

## 枚举

我们将 OCF 与 Veblen 函数对照分析，注意留心 Veblen 函数与 OCF 的对应关系。
左边的式子是最为标准的形式，中间的式子是对 $\psi_1$ 求值之后的结果，右边的式子是 Veblen 函数。

$\psi(\psi_1(0)) = \psi(\Omega \omega) = \varepsilon_\omega$
$\psi(\psi_1(0) + \Omega) = \psi(\Omega \omega + \Omega) = \varepsilon_{\omega+1}$
$\psi(\psi_1(0) 2) = \psi(\Omega \omega 2) = \varepsilon_{\omega 2}$
$\psi(\psi_1(1)) = \psi(\Omega \omega^2) = \varepsilon_{\omega^2}$
$\psi(\psi_1(\psi(0))) = \psi(\Omega \omega^\omega) = \varepsilon_{\omega^\omega}$
$\psi(\psi_1(\psi(\Omega))) = \psi(\Omega \psi(\Omega)) = \varepsilon_{\varepsilon_0}$
$\psi(\psi_1(\psi(\psi_1(0)))) = \psi(\Omega \psi(\Omega \omega)) = \varepsilon_{\varepsilon_\omega}$
$\psi(\psi_1(\Omega)) = \psi(\Omega^2) = \varphi(2,0)$
$\psi(\psi_1(\Omega) + \Omega) = \psi(\Omega^2 + \Omega) = \varphi(1,\varphi(2,0)+1)$
$\psi(\psi_1(\Omega) + \psi_1(0)) = \psi(\Omega^2 + \Omega \omega) = \varphi(1,\varphi(2,0)+\omega)$
$\psi(\psi_1(\Omega) + \psi_1(1)) = \psi(\Omega^2 + \Omega \omega^2) = \varphi(1,\varphi(2,0)+\omega^2)$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\Omega))) = \psi(\Omega^2 + \Omega \psi(\Omega)) = \varphi(1,\varphi(2,0)+\varphi(1,0))$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(0)))) = \psi(\Omega^2 + \Omega \psi(\Omega \omega)) = \varphi(1,\varphi(2,0)+\varphi(1,\omega))$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega)))) = \psi(\Omega^2 + \Omega \psi(\Omega^2)) = \varphi(1,\varphi(2,0) 2)$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega)) + 1)) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + 1)) = \varphi(1,\varphi(2,0) \omega)$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega)) + \psi(\Omega))) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + \psi(\Omega))) = \varphi(1,\varphi(2,0)\varphi(1,0))$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega)) + \psi(\psi_1(\Omega)))) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + \psi(\Omega^2))) = \varphi(1,\varphi(2,0)^2)$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega) + 1))) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + \psi(\Omega^2 + 1))) = \varphi(1,\varphi(2,0)^\omega)$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega) + \psi(\psi_1(\Omega))))) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + \psi(\Omega^2 + \psi(\Omega^2)))) = \varphi(1,\varphi(2,0)^{\varphi(2,0)})$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega) + \Omega))) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + \Omega)) = \varphi(1,\varphi(1,\varphi(2,0)+1))$
$\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega) + \psi_1(\psi(\psi_1(\Omega) + \Omega))))) = \psi(\Omega^2 + \Omega \psi(\Omega^2 + \Omega \psi(\Omega^2 + \Omega))) = \varphi(1,\varphi(1,\varphi(1,\varphi(2,0)+1)))$
$\psi(\psi_1(\Omega)2) = \psi(\Omega^2 2) = \varphi(2,1)$
$\psi(\psi_1(\Omega+1)) = \psi(\Omega^2 \omega) = \varphi(2,\omega)$
$\psi(\psi_1(\Omega+\psi(0))) = \psi(\Omega^2 \omega^\omega) = \varphi(2,\omega^\omega)$
$\psi(\psi_1(\Omega+\psi(\Omega))) = \psi(\Omega^2 \psi(\Omega)) = \varphi(2,\varphi(1,0))$
$\psi(\psi_1(\Omega+\psi(\psi_1(\Omega)))) = \psi(\Omega^2 \psi(\Omega^2)) = \varphi(2,\varphi(2,0))$
$\psi(\psi_1(\Omega+\psi(\psi_1(\Omega + \psi(\psi_1(\Omega)))))) = \psi(\Omega^2 \psi(\Omega^2\psi(\Omega^2))) = \varphi(2,\varphi(2,\varphi(2,0)))$
$\psi(\psi_1(\Omega2)) = \psi(\Omega^3) = \varphi(3,0)$
$\psi(\psi_1(\Omega2) + \Omega) = \psi(\Omega^3) = \varphi(1,\varphi(3,0)+1)$
$\psi(\psi_1(\Omega2) + \psi_1(\Omega)) = \psi(\Omega^3 + \Omega^2) = \varphi(2,\varphi(3,0)+1)$
$\psi(\psi_1(\Omega2)2) = \psi(\Omega^3 2) = \varphi(3,1)$
$\psi(\psi_1(\Omega2+1)) = \psi(\Omega^3 \omega) = \varphi(3,\omega)$
$\psi(\psi_1(\Omega3)) = \psi(\Omega^4) = \varphi(4,0)$
$\psi(\psi_1(\psi_1(0))) = \psi(\Omega^\omega) = \varphi(\omega,0)$
$\psi(\psi_1(\psi_1(0)) + \psi_1(\psi_1(0))) = \psi(\Omega^\omega 2) = \varphi(\omega,1)$
$\psi(\psi_1(\psi_1(0)+1)) = \psi(\Omega^{\omega} \omega) = \varphi(\omega,\omega)$
$\psi(\psi_1(\psi_1(0)+\Omega)) = \psi(\Omega^{\omega+1}) = \varphi(\omega+1,0)$
$\psi(\psi_1(\psi_1(0)2)) = \psi(\Omega^{\omega 2}) = \varphi(\omega 2,0)$
$\psi(\psi_1(\psi_1(1))) = \psi(\Omega^{\omega^2}) = \varphi(\omega^2,0)$
$\psi(\psi_1(\psi_1(\psi(\Omega)))) = \psi(\Omega^{\psi(\Omega)}) = \varphi(\varphi(1,0),0)$
$\psi(\psi_1(\psi_1(\psi(\psi_1(\psi_1(0)))))) = \psi(\Omega^{\psi(\Omega^\omega)}) = \varphi(\varphi(\varphi(1,0),0),0)$
$\psi(\psi_1(\psi_1(\Omega))) = \psi(\Omega^\Omega) = \varphi(1,0,0)$
$\psi(\psi_1(\psi_1(\Omega)) + \Omega) = \psi(\Omega^\Omega + \Omega) = \varphi(1,\varphi(1,0,0)+1)$
$\psi(\psi_1(\psi_1(\Omega)) + \psi_1(\psi_1(0))) = \psi(\Omega^\Omega + \Omega^\omega) = \varphi(\omega,\varphi(1,0,0)+1)$
$\psi(\psi_1(\psi_1(\Omega)) + \psi_1(\psi_1(\psi(\Omega)))) = \psi(\Omega^\Omega + \Omega^{\psi(\Omega)}) = \varphi(\varphi(1,0),\varphi(1,0,0)+1)$
$\psi(\psi_1(\psi_1(\Omega)) + \psi_1(\psi_1(\psi(\psi_1(\psi_1(\Omega)))))) = \psi(\Omega^\Omega + \Omega^{\psi(\Omega^\Omega)}) = \varphi(\varphi(1,0,0),1)$
$\psi(\psi_1(\psi_1(\Omega)) + \psi_1(\psi_1(\psi(\psi_1(\psi_1(\Omega))) + 1))) = \psi(\Omega^\Omega + \Omega^{\psi(\Omega^\Omega) + 1}) = \varphi(\varphi(1,0,0)+1,0)$
$\psi(\psi_1(\psi_1(\Omega)) 2) = \psi(\Omega^\Omega 2) = \varphi(1,0,1)$
$\psi(\psi_1(\psi_1(\Omega) + 1)) = \psi(\Omega^\Omega \omega) = \varphi(1,0,\omega)$
$\psi(\psi_1(\psi_1(\Omega) + \Omega)) = \psi(\Omega^{\Omega+1}) = \varphi(1,1,0)$
$\psi(\psi_1(\psi_1(\Omega) + \Omega) 2) = \psi(\Omega^{\Omega+1} 2) = \varphi(1,1,1)$
$\psi(\psi_1(\psi_1(\Omega) + \Omega 2)) = \psi(\Omega^{\Omega+2}) = \varphi(1,2,0)$
$\psi(\psi_1(\psi_1(\Omega) + \psi_1(0))) = \psi(\Omega^{\Omega+\omega}) = \varphi(1,\omega,0)$
$\psi(\psi_1(\psi_1(\Omega)2)) = \psi(\Omega^{\Omega 2}) = \varphi(2,0,0)$
$\psi(\psi_1(\psi_1(\Omega + 1))) = \psi(\Omega^{\Omega \omega}) = \varphi(\omega,0,0)$
$\psi(\psi_1(\psi_1(\Omega 2))) = \psi(\Omega^{\Omega^2}) = \varphi(1,0,0,0)$
$\psi(\psi_1(\psi_1(\Omega 3))) = \psi(\Omega^{\Omega^3}) = \varphi(2,0,0,0)$
$\psi(\psi_1(\psi_1(\psi_1(0)))) = \psi(\Omega^{\Omega^\omega}) = \varphi(1@\omega)$
$\psi(\psi_1(\psi_1(\psi_1(0)2))) = \psi(\Omega^{\Omega^{\omega2}}) = \varphi(1@\omega2)$
$\psi(\psi_1(\psi_1(\psi_1(\psi(\Omega))))) = \psi(\Omega^{\Omega^{\psi(\Omega)}}) = \varphi(1@\varphi(1,0))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega)))) = \psi(\Omega^{\Omega^{\Omega}}) = \varphi(1@(1,0)) = \text{LVO}$

> 欢迎加入国内的大数数学交流群！
> 群号：930971194

$\psi(\psi_1(\psi_1(\psi_1(\Omega)))2) = \psi(\Omega^{\Omega^{\Omega}}2) = \varphi(1@\varphi(1@(1,0)), 1)$
$\psi(\psi_1(\psi_1(\psi_1(\Omega))+\Omega)) = \psi(\Omega^{\Omega^{\Omega}+1}) = \varphi(1@\varphi(1@(1,0)), 1@1)$
$\psi(\psi_1(\psi_1(\psi_1(\Omega))+\psi_1(\Omega))) = \psi(\Omega^{\Omega^{\Omega}+\Omega}) = \varphi(1@\varphi(1@(1,0)), 1@2)$
$\psi(\psi_1(\psi_1(\psi_1(\Omega))+\psi_1(\psi_1(0)))) = \psi(\Omega^{\Omega^{\Omega}+\Omega^\omega}) = \varphi(1@\varphi(1@(1,0)), 1@\omega)$
$\psi(\psi_1(\psi_1(\psi_1(\Omega))2)) = \psi(\Omega^{\Omega^{\Omega} 2}) = \varphi(2@\varphi(1@(1,0)))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega) + \Omega))) = \psi(\Omega^{\Omega^{\Omega+1}}) = \varphi(1@\varphi(1@(1,0))+1)$
$\psi(\psi_1(\psi_1(\psi_1(\Omega)2))) = \psi(\Omega^{\Omega^{\Omega2}}) = \varphi(1@(1,1))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega+1)))) = \psi(\Omega^{\Omega^{\Omega\omega}}) = \varphi(1@(1,\omega))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega 2)))) = \psi(\Omega^{\Omega^{\Omega^2}}) = \varphi(1@(2,0))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega 2) + \Omega))) = \psi(\Omega^{\Omega^{\Omega^2+1}}) = \varphi(1@\varphi(1@(2,0))+1)$
$\psi(\psi_1(\psi_1(\psi_1(\Omega 2) + \psi_1(\Omega)))) = \psi(\Omega^{\Omega^{\Omega^2+\Omega}}) = \varphi(1@(1,\varphi(1@(2,0))+1))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega 2)2))) = \psi(\Omega^{\Omega^{\Omega^2 2}}) = \varphi(1@(2,1))$
$\psi(\psi_1(\psi_1(\psi_1(\Omega 3)))) = \psi(\Omega^{\Omega^{\Omega^3}}) = \varphi(1@(3,0))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(0))))) = \psi(\Omega^{\Omega^{\Omega^\omega}}) = \varphi(1@(\omega,0))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\Omega))))) = \psi(\Omega^{\Omega^{\Omega^\Omega}}) = \varphi(1@(1,0,0))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(0)))))) = \psi(\Omega^{\Omega^{\Omega^{\Omega^\omega}}}) = \varphi(1@(1@\omega))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\Omega)))))) = \psi(\Omega^{\Omega^{\Omega^{\Omega^\Omega}}}) = \varphi(1@(1@(1,0)))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(0))))))) = \psi(\Omega^{\Omega^{\Omega^{\Omega^{\Omega^\omega}}}}) = \varphi(1@(1@(\omega,0)))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\Omega))))))) = \psi(\Omega^{\Omega^{\Omega^{\Omega^{\Omega^\Omega}}}}) = \varphi(1@(1@(1,0,0)))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(0)))))))) = \psi(\Omega^{\Omega^{\Omega^{\Omega^{\Omega^{\Omega^\omega}}}}}) = \varphi(1@(1@(1@\omega)))$
$\psi(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\psi_1(\Omega)))))))) = \psi(\Omega^{\Omega^{\Omega^{\Omega^{\Omega^{\Omega^\Omega}}}}}) = \varphi(1@(1@(1@(1,0))))$
$\psi(\Omega_2) = \psi(\psi_1(\Omega_2)) = \text{BHO}$

这个形式的 BHO 应该是大部分人刚开始学习大数数学时见到的形式。此前讲到的 Veblen 函数和它的拓展就确实到此为止了。

$\psi(\Omega_2+1)$
$\psi(\Omega_2+\psi(0))$
$\psi(\Omega_2+\psi(\Omega_2))$
$\psi(\Omega_2+\psi(\Omega_2 + \psi(\Omega_2)))$
$\psi(\Omega_2+\Omega)$
$\psi(\Omega_2+\Omega2)$
$\psi(\Omega_2+\psi_1(0))$
$\psi(\Omega_2+\psi_1(1))$
$\psi(\Omega_2+\psi_1(\psi(0)))$
$\psi(\Omega_2+\psi_1(\Omega))$
$\psi(\Omega_2+\psi_1(\psi_1(0)))$
$\psi(\Omega_2+\psi_1(\psi_1(\psi_1(0))))$
$\psi(\Omega_2+\psi_1(\Omega_2))$
$\psi(\Omega_2+\psi_1(\Omega_2 + 1))$
$\psi(\Omega_2+\psi_1(\Omega_2 + \Omega))$
$\psi(\Omega_2+\psi_1(\Omega_2 + \psi_1(\Omega_2)))$
$\psi(\Omega_2+\psi_1(\Omega_2 + \psi_1(\Omega_2 + \psi_1(\Omega_2))))$
$\psi(\Omega_2 2)$
$\psi(\Omega_2 2 + \Omega)$
$\psi(\Omega_2 2 + \psi_1(\Omega_2))$
$\psi(\Omega_2 2 + \psi_1(\Omega_2 2 + \psi_1(\Omega_2 2)))$
$\psi(\Omega_2 2 + \psi_1(\Omega_2 2 + \psi_1(\Omega_2 2)))$
$\psi(\Omega_2 3)$
$\psi(\Omega_2 4)$
$\psi(\Omega_2 \omega)$

## 一些说明

这一节所定义的 OCF 并不是 BOCF，而是开头弱化版本的 MOCF。
此外，可能有人会问关于函数下标的问题。这里的自然数下标只是一个简写，在讲到 $\Omega_\omega$ 之后时会修正为标准的下标。

一般情况下，我们不经常用最左边的最标准的形式，而是用右边的形式。这个形式理解和表达起来更加简便一些，在 $\Omega^{\Omega^\cdots}$ 之后将它改变为 $\psi_1(\Omega_2)$ 即可。