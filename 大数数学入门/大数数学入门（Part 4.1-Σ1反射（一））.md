#! https://zhuanlan.zhihu.com/p/674902112
# 大数数学入门（Part 4.1-Σ1反射（pfec）初步）

从这一节开始，我们将不去再具体的写出OCF的定义，有兴趣的可以自己去写出定义。此外，由于本人能力不足，本人将同样不去讲解它的数理逻辑方面的意义，而只将稳定表达式作为非递归序数的符号。

由于adm稳定的分析进展缓慢，我们将使用目前最为常用的p.f.e.c（parameter free effective cardinal）稳定。

## $\Sigma_1$ 稳定的性质

当我们说 $\alpha$ 是 $\beta$-稳定，或者 $\alpha$ 稳定到 $\beta$ 时，我们的意思是 $\alpha < \beta$，并且 $L_\alpha \prec_{\Sigma_1} L_\beta$。对于 $\Sigma_1$ 稳定和 $\Pi_n$ 反射的具体意义，请参考这篇文章：[https://googology.fandom.com/wiki/User:Hyp_cos/TON_vs._stability_(remastered)]

我们可以刻画 $\prec_{\Sigma_1}$ 的一些性质：

1. 如果 $\alpha < \beta < \gamma$，且有 $L_{\alpha} \prec_{\Sigma_n} L_\beta$ 和 $L_{\beta} \prec_{\Sigma_n} L_\gamma$，那么有 $L_\alpha \prec_{\Sigma_n} L_\gamma$。
2. 如果 $\alpha < \beta < \gamma$，且有 $L_{\alpha} \prec_{\Sigma_n} L_\gamma$ 和 $L_{\beta} \prec_{\Sigma_n} L_\gamma$，那么有 $L_\alpha \prec_{\Sigma_n} L_\beta$。
3. 如果 $\alpha < \beta < \gamma$，且有 $L_{\alpha} \prec_{\Sigma_1} L_\gamma$ 那么有 $L_\alpha \prec_{\Sigma_1} L_\beta$。
4. 对于一个序数集合 $A$，若对于任意的 $x\in A$ 有 $L_{x} \prec_{\Sigma_1} L_\beta$，那么有 $L_{\sup A} \prec_{\Sigma_1} L_\beta$
5. 对于一个序数集合 $B$，若对于任意的 $x\in B$ 有 $L_{\alpha} \prec_{\Sigma_1} L_x$，那么有 $L_{\alpha} \prec_{\Sigma_1} L_{\sup B}$

当我们说一个序数类 $X$ 是 $f$-稳定时，我们的意思是对于每一个 $x \in X$，$x$ 是 $f(x)$ 稳定的。

我们可以进一步细分 $\alpha$ 是 $\beta$-稳定的结构：$\alpha$ 是 $\beta$-$\Pi_n$-稳定。以及函数式的稳定中，我们会出现 $\Pi_n$-$f$-稳定，我们写作 $\lambda \alpha.f(\alpha) - \Pi_n$。

## $\Sigma_1$ 稳定和 $\Pi_n$ 反射的关联

> 这里用一个稍有歧义的符号：$\Pi_\omega$ 将表示此前的 $\text{psd}.\Pi_\omega$，而真正 $\Pi_{\omega}$ 将写成 $\Pi_{\omega+1}$。

让我们将 $\Sigma_1$ 稳定与 $\Pi_n$ 反射建立关联。最小的非平凡的表达式是 $\lambda \alpha.(\alpha+1) - \Pi_0 = \Pi_\omega$，恰好是我们此前达到的极限。$\lambda \alpha.(\alpha + 1) - \Pi_0$ 中的序数 $x$ 稳定到 $x+1$

$\lambda \alpha.(\alpha+1) - \Pi_0 = \Pi_\omega$
$1- \lambda \alpha.(\alpha+1) - \Pi_0 = \Pi_1 - \Pi_\omega$
$2- \lambda \alpha.(\alpha+1) - \Pi_0 = \Pi_2 - \Pi_\omega$
$\lambda \alpha.(\alpha+1) - \Pi_0 - \lambda \alpha.(\alpha+1) - \Pi_0 = \Pi_\omega - \Pi_\omega$
$\lambda \alpha.(\alpha+1) - \Pi_1 = \Pi_{\omega + 1}$
$\lambda \alpha.(\alpha+1) - \Pi_2 = \Pi_{\omega + 2}$
$\lambda \alpha.(\alpha+1) - \Pi_3 = \Pi_{\omega + 3}$
$\lambda \alpha.(\alpha+2) - \Pi_0 = \Pi_{\omega 2}$
$\lambda \alpha.(\alpha+2) - \Pi_1 = \Pi_{\omega 2 + 1}$
$\lambda \alpha.(\alpha+3) - \Pi_0 = \Pi_{\omega 3}$

> 前面的函数在后面的 $\Pi_n$ 到达 $\Pi_0$ 时 $+1$，并将后面重新变成 $\Pi_0$，起到一个“计数器”的作用。

$\lambda \alpha.(\alpha+\omega) - \Pi_0 = \Pi_{\omega^2}$
$\lambda \alpha.(\alpha+\omega+1) - \Pi_0 = \Pi_{\omega^2+\omega}$
$\lambda \alpha.(\alpha+\omega 2) - \Pi_0 = \Pi_{\omega^2 2}$
$\lambda \alpha.(\alpha+\omega^2) - \Pi_0 = \Pi_{\omega^3}$
$\lambda \alpha.(\alpha+\omega^3) - \Pi_0 = \Pi_{\omega^4}$
$\lambda \alpha.(\alpha+\omega^\omega) - \Pi_0 = \Pi_{\omega^\omega}$
$\lambda \alpha.(\alpha+\omega^\omega) - \Pi_0 = \Pi_{\omega^\omega}$
$\lambda \alpha.(\alpha+\omega^{\omega+1}) - \Pi_0 = \Pi_{\omega^{\omega+1}}$
$\lambda \alpha.(\alpha+\omega^{\omega^\omega}) - \Pi_0 = \Pi_{\omega^{\omega^\omega}}$

此后：$\lambda \alpha.(\alpha+x) - \Pi_0$ 的容许点就是：
$\lambda \alpha.(\alpha+\Omega) - \Pi_0 = \Pi_{\Omega}$

继续：
$\lambda \alpha.(\alpha + \Omega+1) - \Pi_0 = \Pi_{\Omega + \omega}$
$\lambda \alpha.(\alpha + \Omega_2) - \Pi_0 = \Pi_{\Omega_2}$
$\lambda \alpha.(\alpha + \Omega_\omega) - \Pi_0 = \Pi_{\Omega_\omega}$
$\lambda \alpha.(\alpha + I) - \Pi_0 = \Pi_{I}$
$\lambda \alpha.(\alpha + M) - \Pi_0 = \Pi_{M}$
$\lambda \alpha.(\alpha + K) - \Pi_0 = \Pi_{K}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+1) - \Pi_0) - \Pi_0 = \Pi_{\Pi_\omega}$

此后，可以继续强化内部的 $\Pi_\omega$：

$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+1) - \Pi_1) - \Pi_0 = \Pi_{\Pi_{\omega+1}}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+2) - \Pi_0) - \Pi_0 = \Pi_{\Pi_{\omega 2}}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+\omega) - \Pi_0) - \Pi_0 = \Pi_{\Pi_{\omega^2}}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+\Omega) - \Pi_0) - \Pi_0 = \Pi_{\Pi_{\Omega}}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+\lambda \alpha.(\alpha+1) - \Pi_0) - \Pi_0) - \Pi_0 = \Pi_{\Pi_{\Pi_\omega}}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+\lambda \alpha.(\alpha+2) - \Pi_0) - \Pi_0) - \Pi_0 = \Pi_{\Pi_{\Pi_{\omega 2}}}$
$\lambda \alpha.(\alpha + \lambda \alpha.(\alpha+\lambda \alpha.(\alpha+\lambda \alpha.(\alpha+1) - \Pi_0) - \Pi_0) - \Pi_0) - \Pi_0 = \Pi_{\Pi_{\Pi_{\Pi_\omega}}}$

然后我们就到达了不动点。回想起 OCF 的 $\psi(\Omega + \Omega)$ 是如何展开的：

$\psi(\Omega 2) = \psi(\Omega + \psi(\Omega + \psi(\Omega + \cdots)))$

因此，我们这样表示之前的不动点：

$\lambda \alpha.(\alpha + \alpha) - \Pi_0$

$x \rightarrow \lambda \alpha.(\alpha + x) - \Pi_0$ 有容许点、$M$ 点等，我们依然没有失去表达它们的方法：

$\Pi_2 \; \Pi_1 - \lambda \alpha.(\alpha 2) - \Pi_0$
$\Pi_2-\Pi_2 \; \Pi_1 - \lambda \alpha.(\alpha 2) - \Pi_0$
$\Pi_3 \; \Pi_1 - \lambda \alpha.(\alpha 2) - \Pi_0$
$\cdots$

$\lambda \alpha.(\alpha 2 + 1) - \Pi_0$
$\lambda \alpha.(\alpha 2 + \Omega) - \Pi_0$
$\lambda \alpha.(\alpha 2 + \lambda \alpha.(\alpha+1) - \Pi_0) - \Pi_0$
$\lambda \alpha.(\alpha 2 + \lambda \alpha.(\alpha 2) - \Pi_0) - \Pi_0$
$\lambda \alpha.(\alpha 2 + \lambda \alpha.(\alpha 2 + \lambda \alpha.(\alpha 2) - \Pi_0) - \Pi_0) - \Pi_0$
$\lambda \alpha.(\alpha 3) - \Pi_0$，它是 $\lambda \alpha.(\alpha 2 + x) - \Pi_0$ 的不动点。
$\lambda \alpha.(\alpha^2) - \Pi_0$
$\lambda \alpha.(\alpha^\alpha) - \Pi_0$
$\lambda \alpha.(\alpha^{\alpha^\alpha}) - \Pi_0$
$\lambda \alpha.(\epsilon_\alpha) - \Pi_0$
$\cdots$

现在我们达到了一个比较关键的地方：我们需要枚举所有的递归函数 $f$，才能进展到 $\lambda \alpha.\Omega_{\alpha+1} - \Pi_1$，而枚举递归函数这一步当然不是递归的。好在我们最后都会使用 OCF 去塌缩这个序数，因此我们给出它的塌缩后的展开。

$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(\Omega_{\alpha+1})) - \Pi_0$
$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(I_{\alpha+1})) - \Pi_0$
$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(K_{\alpha+1})) - \Pi_0$
$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(\lambda \beta.(\beta + 1) - \Pi_0 \text{ aft } \alpha)) - \Pi_0$
$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(\lambda \beta.(\beta 2) - \Pi_0 \text{ aft } \alpha)) - \Pi_0$
$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(\lambda \beta.(\psi_{\Omega_{\beta+1}}(\Omega_{\beta+1})) - \Pi_0 \text{ aft } \alpha)) - \Pi_0$
$\lambda \alpha.(\psi_{\Omega_{\alpha+1}}(\lambda \beta.(\psi_{\Omega_{\beta+1}}(\lambda \gamma.(\psi_{\Omega_{\gamma+1}}(\Omega_{\gamma+1})) - \Pi_0 \text{ aft } \beta)) - \Pi_0 \text{ aft } \alpha)) - \Pi_0$
$\cdots$

当我们展开 $\psi(\lambda \alpha.\Omega_{\alpha+1} - \Pi_1)$ 时，我们是按照以上的规律展开的，但是这并不表明 $\lambda \alpha.\Omega_{\alpha+1} - \Pi_1$ 是它们的上界，就像 $\Omega$ 永远是递归序数的上界，无论 $\psi(\cdots)$ 里面是多么复杂的东西。

> 这里有两个注意事项。
> 第一个是 $\lambda \alpha.f(\alpha) - \Pi_n$ “表现出” $\Pi_{n+1}$ 的性质
> 第二个是考虑 $\lambda \alpha.f(\alpha) - \Pi_i$，在 $f(\alpha)$ 表现出 $\Pi_{n+1}$ 的性质时，$i$ 必须大于等于 $n$。由于 $\Omega_{\alpha+1}$ 是 $\Pi_2$ 的，因此 $\lambda \alpha.\Omega_{\alpha+1} - \Pi_0$ 不存在。

继续：
$\lambda \alpha.(\Omega_{\alpha+1}) - \Pi_1$
$\lambda \alpha.(\Omega_{\alpha+2}) - \Pi_1$
$\lambda \alpha.(I_{\alpha+1}) - \Pi_1$
$\lambda \alpha.(K_{\alpha+1}) - \Pi_2$
$\lambda \alpha.(\Pi_4 \text{ aft } \alpha) - \Pi_3$
$\lambda \alpha.(\Pi_5 \text{ aft } \alpha) - \Pi_4$

再进行下去，我们似乎会达到 $\Pi_\omega$，但是 $\Pi_\omega$ 不能表现出任何的性质 $\Pi_{n+1}$，我们似乎卡在了这个地方。

## 两段稳定链

我们当然不会止步于此。回忆起稳定序数最开始的地方，$\lambda \alpha.(\alpha+1) - \Pi_0$ 实际上就是 $\Pi_\omega$，并且表现出 $\Pi_1$ 的性质。因此，我们可以这样表达上面的那些序数的极限：

$\lambda \alpha.(\lambda \beta.(\beta + 1) - \Pi_0 \text{ aft }\alpha) - \Pi_0$

我们先简记为 $X$。$X$ 中的序数 $x$ 具有这样的性质：首先，$\alpha(0) = x$ 会被稳定到 $\alpha(1) = \lambda \beta.(\beta + 1) - \Pi_0 \text{ aft }x$。然后，由于 $\lambda \beta.(\beta + 1) - \Pi_0$ 中的序数是 $+1$ 稳定的，$\alpha(1)$ 被稳定到 $\alpha(2) = \alpha(1) + 1$。

> 这里就已经引入了 $\alpha$ 函数。$\alpha(x)$ 是稳定链的第 $1+x$ 项：$\alpha(0)$ 属于满足整个稳定表达式的序数类，而 $\alpha(0)$ 稳定到 $\alpha(1)$，$\alpha(1)$ 稳定到 $\alpha(2)$ 等。
> 有的时候会看到 $\alpha'$ 等记号。由于每一个稳定表达式都对应着一个 $\alpha$ 函数，$\alpha'$ 会区别于 $\alpha$ 表示另一个稳定表达式的稳定链。

让我们用 $\alpha$ 函数将前面的一些重要的稳定表达式再描述一遍。

$\alpha(1) = \alpha(0) + 1$：
$\lambda \alpha.(\alpha+1) - \Pi_0$

$\alpha(1) = \alpha(0) + 1$，且 $\Pi_1$ 反射：
$\lambda \alpha.(\alpha+1) - \Pi_1$

$\alpha(1) = \alpha(0) + 2$：
$\lambda \alpha.(\alpha+2) - \Pi_0$

$\alpha(1) = \alpha(0) * 2$：
$\lambda \alpha.(\alpha * 2) - \Pi_0$

$\alpha(1) = \Pi_2 \text{ aft } \alpha(0)$：
$\lambda \alpha.(\Omega_{\alpha+1}) - \Pi_1$

$\alpha(1) = \Pi_3 \text{ aft } \alpha(0)$：
$\lambda \alpha.(K_{\alpha+1}) - \Pi_2$

$\alpha(1)$ 是 $\alpha(0)$ 的后一个（$\alpha(1)$ 稳定到 $\alpha(1) + 1$ 序数）：
$\lambda \alpha.(\lambda \beta.(\beta + 1) - \Pi_0 \text{ aft }\alpha) - \Pi_0$
到了这里，后面的 $\alpha(1)+1$ 就是 $\alpha(2)$。

使用常规的方法继续前进：

$\alpha(1)$ 是 $\alpha(0)$ 的后一个（$\alpha'(1) = \alpha'(0)+1$ 稳定）加 $1$：
$\lambda \alpha.(\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\alpha + 1) - \Pi_0$
注意，这里 $\alpha(1)$ 并不是像之前一样稳定到 $\alpha(1)+1$。事实上它不稳定到任何东西，因此这个稳定表达式其实只有一段稳定。

$\lambda \alpha.(\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\alpha + \alpha) - \Pi_0$
$\lambda \alpha.((\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\alpha) \times 2) - \Pi_0$
$\lambda \alpha.(\Pi_2 \text{ aft }\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\alpha) - \Pi_1$
$\lambda \alpha.(\Pi_3 \text{ aft }\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\alpha) - \Pi_1$

> 有的时候这个 $\text{ aft }$ 会略去不写，因为一个序数的稳定目标大于它本身。
> 此外，有的地方也会使用 $\alpha +1 \text{ th } X$，即 $X[\alpha+1]$ 表示。但是考虑到后面计划讲到方括号稳定，应该不会使用方括号来表示这个表达式。

$\lambda \alpha.(\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\lambda \beta.(\beta+1)-\Pi_0) - \Pi_1$
也就是 $\lambda \alpha.(\text{2nd }\lambda \beta.(\beta+1)-\Pi_0 \text{ aft }\alpha) - \Pi_1$
这里也是有两段稳定的。$\alpha(2)$ 是 $\alpha(1) + 1$，$\alpha(1)$ 是 $\alpha(0)$ 的后两个 $\alpha(2)$-稳定。

$\lambda \alpha.(\Pi_1 - \lambda \beta.(\beta+1)-\Pi_0) - \Pi_1$
$\lambda \alpha.(\Pi_2 - \lambda \beta.(\beta+1)-\Pi_0) - \Pi_1$
$\lambda \alpha.(\lambda \beta.(\beta+1) - \Pi_0 - \lambda \beta.(\beta+1)-\Pi_0 ) - \Pi_1$

$\alpha(1)$ 是 $\alpha(0)$ 的后一个（$\alpha(1)-\Pi_1$ 稳定到 $\alpha(1) + 1$ 序数）：
$\lambda \alpha.(\lambda \beta.(\beta+1) - \Pi_1) - \Pi_1$
$\lambda \alpha.(\lambda \beta.(\beta+1) - \Pi_2) - \Pi_2$
$\lambda \alpha.(\lambda \beta.(\beta+2) - \Pi_0) - \Pi_0$


$\lambda \alpha.(\lambda \beta.(\beta+\alpha) - \Pi_0) - \Pi_0$，这里的 $\alpha$ 找到最外层的 $\lambda \alpha . f(\cdots)$ 做不动点，类似于 $\psi(\Omega_2 + \Omega)$。
$\lambda \alpha.(\lambda \beta.(\beta+\beta) - \Pi_0) - \Pi_0$，这里的 $\beta$ 找到里面的的 $\lambda \beta . f(\cdots)$ 做不动点，类似于 $\psi(\Omega_2 + \Omega_2)$。

$\lambda \alpha.(\lambda \beta.(\Pi_2) - \Pi_1) - \Pi_1$
$\lambda \alpha.(\lambda \beta.(\Pi_3) - \Pi_2) - \Pi_2$

最后，达到 $\Pi_\omega$ 时，我们引入第三段稳定链：
$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0) - \Pi_0$
这里，$\alpha(0)$ 稳定到 $\alpha(1)$，$\alpha(1)$ 稳定到 $\alpha(2)$，$\alpha(2)$ 稳定到 $\alpha(3) = \alpha(2) + 1$。稳定链顶端的性质（即 $+1$-稳定）被底端两段的稳定链放大。

在下一节，我们将触碰到极限长度稳定链的极限，并且将会第一次见到非平凡的方括号稳定：$\Pi_0[2]$ 反射，即 Nonprojectible 序数。