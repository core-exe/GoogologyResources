# 大数数学入门（Part 4.2-极限长度稳定链）

在上一节中，我们初步介绍了 $\Sigma_1$ 稳定，并且进展到了两段稳定链的极限，现在让我们继续推进：

最小的三段稳定链：
$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0) - \Pi_0$

对于更长的表达式，这样的简写：$n-\pi-(\cdots)-\Pi_m$。$n$ 表示稳定链的长度，省略号中表示稳定链顶端的函数，最后的 $\Pi_m$ 表现的是稳定链顶端的稳定性质。例如上述的稳定表达式写为 $3-\pi-(+1)-\Pi_0$。此后的部分也会给出这两类表达式的对应关系。

> 尽管没有文章提到，但是我依然希望括号中的函数能够有一个统一的表达，因此我比较复杂的情况下会在其中使用lambda函数。例如 $3-\pi-(+1)-\Pi_0$ 会写成 $3-\pi-\lambda \alpha.(\alpha + 1) - \Pi_0$

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0) - \Pi_1$
是 $1-\pi-\lambda \alpha.(2-\pi-(+1)-\Pi_0 \text{ aft } \alpha)-\Pi_1$

$\lambda \alpha.((\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 \text{ aft } \alpha) + 1) - \Pi_0$
是 $1-\pi-\lambda \alpha.(2-\pi-(+1)-\Pi_0 \text{ aft } \alpha + 1)-\Pi_0$

$\lambda \alpha.(\Pi_2 \text{ aft }\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 \text{ aft } \alpha) - \Pi_1$
是 $1-\pi-\lambda \alpha.(\Pi_2 \text{ aft } 2-\pi-(+1)-\Pi_0 \text{ aft } \alpha)-\Pi_1$

$\lambda \alpha.(\lambda \beta.(\beta + 1) - \Pi_0 \text{ aft }\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 \text{ aft } \alpha) - \Pi_0$
是 $1-\pi-\lambda \alpha.(\lambda \beta.(\beta + 1) - \Pi_0 \text{ aft } 2-\pi-(+1)-\Pi_0 \text{ aft } \alpha)-\Pi_0$

$\lambda \alpha.(\text{2nd }\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 \text{ aft } \alpha) - \Pi_0$
是 $1-\pi-\lambda \alpha.(\text{2nd } 2-\pi-(+1)-\Pi_0 \text{ aft } \alpha)-\Pi_0$

$\lambda \alpha.(\text{2nd }\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 \text{ aft } \alpha) - \Pi_0$
是 $1-\pi-\lambda \alpha.(\text{2nd } 2-\pi-(+1)-\Pi_0 \text{ aft } \alpha)-\Pi_0$

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 - \lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_0 \text{ aft } \alpha) - \Pi_0$
是 $1-\pi-\lambda \alpha.(2-\pi-(+1)-\Pi_0-2-\pi-(+1)-\Pi_0 \text{ aft } \alpha)-\Pi_0$

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_1) - \Pi_1$
是 $2-\pi-\lambda\alpha.(1-\pi-(+1)-\Pi_0\text{ aft } \alpha)-\Pi_1$，我们现在开始强化 $\alpha(1)$。

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0) - \Pi_2) - \Pi_2$
是 $2-\pi-\lambda\alpha.(1-\pi-(+1)-\Pi_0\text{ aft } \alpha)-\Pi_2$。

$\lambda \alpha.(\lambda \beta.((\lambda \gamma.(\gamma + 1) - \Pi_0 \text{ aft } \beta) + 1) - \Pi_0) - \Pi_0$
是 $2-\pi-\lambda\alpha.((1-\pi-(+1)-\Pi_0\text{ aft } \alpha) + 1)-\Pi_0$。

$\lambda \alpha.(\lambda \beta.(\text{2nd }\lambda \gamma.(\gamma + 1) - \Pi_0 \text{ aft } \beta) - \Pi_0) - \Pi_0$
是 $2-\pi-\lambda\alpha.(\text{2nd } 1-\pi-(+1)-\Pi_0\text{ aft } \alpha)-\Pi_0$。

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_0 - \lambda \gamma.(\gamma + 1) - \Pi_0 \text{ aft } \beta) - \Pi_0) - \Pi_0$
是 $2-\pi-\lambda\alpha.(1-\pi-(+1)-\Pi_0 - 1-\pi-(+1)-\Pi_0\text{ aft } \alpha)-\Pi_0$。

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 1) - \Pi_1) - \Pi_1) - \Pi_1$
是 $3-\pi-(+1)-\Pi_1$，我们现在开始强化 $\alpha(2)$。

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\gamma + 2) - \Pi_0) - \Pi_0) - \Pi_0$
是 $3-\pi-(+2)-\Pi_0$。

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\Pi_2 \text{ aft } \gamma) - \Pi_1) - \Pi_1) - \Pi_1$
是 $3-\pi-\lambda\alpha.(\Pi_2 \text{ aft }\alpha)-\Pi_1$。

$\lambda \alpha.(\lambda \beta.(\lambda \gamma.(\lambda \delta.(\delta + 1)) - \Pi_1) - \Pi_1) - \Pi_1$
是 $3-\pi-\lambda\alpha.(1-\pi-(+1)-\Pi_0 \text{ aft }\alpha)-\Pi_0$。

它，也就是 $4-\pi-(+1)-\Pi_0$。我们可以看到，将稳定链进一位是这样的过程：我们先提升 $\alpha(0)$，直到 $\alpha(0)$ 被提升到“$\alpha(0)$ 被稳定到下一个 $\beta$，这个 $\beta$ 被稳定到 $f(\beta)$”，这个 $\beta$ 就是 $\alpha(1)$，我们也就完成了一次对 $\alpha(1)$ 的提升。此后，我们将 $\alpha(1)$ 提升到同样的程度，就完成了一次对 $\alpha(2)$ 的提升。直到提升到稳定链顶端，才完成稳定链顶端的进一。可以看见随着稳定链的增长，提升稳定链长度确实是越来越复杂的事情。

继续推进：

$1-\pi-\lambda \alpha.(3-\pi-(+1)-\Pi_0 \text{ aft }\alpha)-\Pi_0$
$2-\pi-\lambda \alpha.(2-\pi-(+1)-\Pi_0 \text{ aft }\alpha)-\Pi_0$
$3-\pi-\lambda \alpha.(1-\pi-(+1)-\Pi_0 \text{ aft }\alpha)-\Pi_0$
$4-\pi-(+1)-\Pi_1$
$4-\pi-(+2)-\Pi_0$
$5-\pi-(+1)-\Pi_0 = 4-\pi-\lambda\alpha.(1-\pi-(+1)-\Pi_0 \text{ aft }\alpha)-\Pi_0$
$6-\pi-(+1)-\Pi_0$

继续向上，我们就达到了极限长度的稳定链：$\omega-\pi-\Pi_0$。稳定链顶端是极限序数时，就不存在“稳定链顶端的前一项”一说，因此稳定链顶端的函数是不重要的。$\omega-\pi-\Pi_0$ 中的序数有这样的性质：$x\in \omega-\pi-\Pi_0$，那么 $x$ 就被稳定到下一个 $\omega-\pi-\Pi_0$，这个序数自然也会被稳定的到再下一个 $\omega-\pi-\Pi_0$，如此不断的延续。

根据 $\Sigma_1$ 稳定的性质（传递性，以及对于集合上确界的封闭性），这稳定链中每一个序数都被稳定到这个稳定链的上确界。以最小的 $\omega-\pi-\Pi_0$ 为例子：$\alpha(0) = \omega-\pi-\Pi_0$，$\alpha(1) =\text{2nd } \omega-\pi-\Pi_0$，$\alpha(2) =\text{3rd } \omega-\pi-\Pi_0$。所有的 $\alpha(n)$ 都稳定到 $\sup\{\alpha(n)\} = \Pi_1 - \omega-\pi-\Pi_0$，后面这个数就是 $\alpha(\omega)$。

同时，我们也要给出方括号稳定的部分定义：[0]反射和[0]稳定是所有序数共有的性质，[1]反射和[1]稳定是通常的反射和稳定。而最小的[2]稳定是 $\Pi_0[2]$，它的定义是：$\alpha\in \Pi_0[2]$ 等价于 $\alpha$ 是 $\Pi_0 - \{\beta < \alpha| \beta能[1]稳定到 \alpha\}$。

用人话讲就是，$\alpha\in \Pi_0[2]$ 等价于有极限序数个数稳定到 $\alpha$，或者 $\alpha$ 处于极限长度稳定链的顶端。

也就是说，$\Pi_0[2] = \Pi_1 - \omega-\pi-\Pi_0$。

> 普通的反射中，$\Pi_0 = \Pi_1$。在高阶的方括号反射中，$\Pi_0 =\Pi_1=\Pi_2$，具体原因牵涉到比较深的数理逻辑。

让我们继续前进，去看一下如何从 $\omega-\pi$ 进步到 $(\omega+1)-\pi$。

首先，极限长度的稳定链在底部可以任意的附加稳定链，因为 $1+\omega = \omega$。因此 $\lambda\alpha.(\omega-\pi-\Pi_0) - \Pi_0 = \omega-\pi-\Pi_0$。

有：

$1-\omega-\pi-\Pi_0 = 1-\Pi_0[2] = 1-\lambda\alpha.(\omega-\pi-\Pi_0) - \Pi_0$