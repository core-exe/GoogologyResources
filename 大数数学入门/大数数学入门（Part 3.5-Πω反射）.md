#! https://zhuanlan.zhihu.com/p/673933193
# 大数数学入门（Part 3.5-Πω反射）

在上一章的最后，我们到达了递归弱紧致序数$K = \min \Pi_3$，并且给出了达到 $K$ 的OCF。在这一节中，我们将会完成整个 $\Pi_\omega$ 之下的反射的OCF的构建。

## $\Pi_3$ 反射

首先，在 $K$ 之后，我们可以按照之前的方式，达到一些比 $K$ 稍微大一点的序数：

$\Omega_{K+1} = 2\text{ aft }3$
$I_{K+1} = 2\;1-2\text{ aft }3$
$I(1, K+1) = 2\;1-2\;1-2\text{ aft }3$
$M_{K+1} = 2-2\text{ aft }3$
$N_{K+1} = 2-2-2\text{ aft }3$
$2-2-2-2\text{ aft }3$
$(2-)^\omega \text{ aft }3$
$2\;1-\{(2-)^{x}\} \text{ aft }3$
$2-\{(2-)^{x}\} \text{ aft }3$
$2-\{(2-)^{y}\{(2-)^{x}\}\} \text{ aft }3$
以上的递归极限就是下一个 $\Pi_3$ 序数，即 $K_2 = 3\text{ aft } 3$

$K_2$ 的OCF的规则也是比较简单的：

1. $\psi_{K_2}(0) = \Pi_2 \text{ aft } K$
2. $\psi_{K_2}(\alpha+1) = 2-\psi_{K_2}(\alpha)$
3. $\psi_{K_2}(\#\sim K_2) = (2-)^{2-\psi_{K_2}(\#\sim x) | x < K_2}$

本质上，就只是将起始的位置变成了 $2 \text{ aft }K$，这样的事情我们已经做过几次了。按照同样的方式，我们可以继续：

$\text{3rd } \Pi_3$
$1-3$
$1-1-3$
$2\;1-3$
$2-2\;1-3$
$2-2-2\;1-3$
$2-\{(2-)^x\}\;1-3$
$2-\{(2-)^y\{(2-)^x\}\}\;1-3$

折叠上面的就是 $3\;1-3$，$K$ 函数的 $K$ 点。OCF的规则仅需改变第一条：$\psi_{3\;1-3}(0) = 2\;1-3$。

继续：
$1-3\;1-3$
$3\;1-3\;1-3$
$(3\;1-)^\omega$
$3\;1-\{(3\;1-)^x\}$
$3\;1-\{(3\;1-)^y\{(3\;1-)^x\}\}$

回忆一下我们是如何达到 $2-\{(2-)^x\}$ 的，我们发现折叠以上的都是 $2-3$：

1. $\psi_{2-3}(0) = (3\;1-) = \Pi_3$
2. $\psi_{2-3}(\alpha+1) = 3\;1-\psi_{2-3}(\alpha)$
3. $\psi_{2-3}(\#\sim 2-3) = (3\;1-)^{3\;1-\{\psi_{2-3}(\#\sim x) | x < 2-3\}}$

它的折叠依然与 $2-X$ 的折叠一致。

从 $2-3$ 出发：

$1-2-3$
$2\;1-2-3$
$2-2\;1-2-3$
$3\;1-2-3$
$2-3\;1-2-3$
$2-3\;1-2-3\;1-2-3$
$2-2-3$，同样遵循 $2-3$ 的规则。
$2-2-2-3$
$2-\{(2-)^x3\}$
$\cdots$

折叠 $(2-)^\cdots 3$ 的自然是 $3\;2-3$，仿照 $2\;1-2$ 的定义：

1. $\psi_{3\;2-3}(0) = 3$
2. $\psi_{3\;2-3}(\alpha+1) = 2-\psi_{3\;2-3}(\alpha)$
3. $\psi_{3\;2-3}(\#\sim 3\;2-3) = (2-)^{2-\psi_{3\;2-3}(\#\sim x) | x < 3\;2-3}$

从 $3\;2-3$ 出发：

$1-3\;2-3$
$2-3\;2-3$
$3\;2-3\;2-3$
$(3\;2-)^3 3$

我们的情况与当初的 $2-2$ 的情况很相似：

1. $\psi_{3-3}(0) = 3$
2. $\psi_{3-3}(\alpha+1) = 3\;2-\psi_{3-3}(\alpha)$
3. $\psi_{3-3}(\# \sim 3-3) = (3\;2-)^{3\;2-\{\psi_{3-3}(x) | x < 3-3\}}$

从 $3-3$ 之后：

$1-3-3$
$3\;1-3-3$
$3-3\;1-3-3$
$3-3\;1-3-3\;1-3-3$
$2-3-3$
$2-2-3-3$
$3\;2-3-3$
$3\;2-3\;2-3-3$
$3-3\;2-3-3$
$3-3\;2-3-3\;2-3-3$
$3-3-3$
$3-3-3-3$
$1-\{(3-)^x\}$
$2-\{(3-)^x\}$
$3-\{(3-)^x\}$
$3-\{(3-)^y\{(3-)^x\}\}$

此后，我们到达 $\Pi_3$ 反射的极限。同时，我们给出任意的 $3-X$ 的塌缩：

1. $\psi_{3-X}(0) = X$
2. $\psi_{3-X}(\alpha+1) = X\;2-\psi_{3-X}(\alpha)$
3. $\psi_{3-X}(\#\sim 3-X) = (X\;2-)^{X\;2-\{\psi_{3-X}(\# \sim x) | x < 3-X\}}$

## $\Pi_n$ 反射

相信大家已经找到规律了：$\Pi_{n+1} - X$ 折叠 $X \Pi_{n}-$，因此我们直接给出 OCF：

1. $\psi_{\Pi_{n+1}-X}(0) = X$
2. $\psi_{\Pi_{n+1}-X}(\alpha+1) = X\;\Pi_n-\psi_{\Pi_{n+1}-X}(\alpha)$
3. $\psi_{\Pi_{n+1}-X}(\#\sim \Pi_{n+1}-X) = (X\;\Pi_n-)^{X\;\Pi_n-\{\psi_{\Pi_{n+1}-X}(\# \sim x) | x < \Pi_{n+1}-X\}}$

从此，我们从 $\Pi_4$ 开始向上枚举，它们的 OCF 展开留作练习：

$\Pi_4$
$1-4$
$2\;1-4$
$2-2\;1-4$
$3\;1-4$
$4\;1-4$
$4\;1-4\;1-4$
$2-4$
$3\;2-4$
$3-3\;2-4$
$4\;2-4$
$3-4$
$3-3-4$
$4\;3-4$
$4-4$
$4-4-4$
$\Pi_5$
$1-5$
$2-5$
$3-5$
$4-5$
$5-5$
$\Pi_6$
$\Pi_7$
$\cdots$

最后，我们到达它们共同的上界：$\text{pseudo}.\Pi_\omega = \sup\{\Pi_1, \Pi_2, \Pi_3, \cdots\}$，这里我们简记为 $p.\omega$。我们还没到达真正的 $\Pi_\omega$。类比来讲，我们现在在 $\psi(\Omega_\omega)$，而 $\Pi_\omega$ 类比于 $\psi(\Omega_{\omega+1})$。

## $\Pi_\omega$ 反射

让我们完成这最后一步。

$p.\omega$
$1-p.\omega$
$2-p.\omega$
$p.\omega-p.\omega$
$p.\omega-p.\omega-p.\omega$
$1-\{(p.\omega-)^x\}$
$2-\{(p.\omega-)^x\}$
$p.\omega-\{(p.\omega-)^x\}$
$1-\{(p.\omega-)^y\{(p.\omega-)^x\}\}$

折叠这一切的就是真正的 $\Pi_\omega$ 反射。

在此后，我们能做什么？我们可以继续拓展，得到 $\Pi_{\omega+1}$，$\Pi_{\omega+2}$ 等，以及进一步拓展成veblen形式的 $\Pi_{(1,0)}$，$\Pi_{(1,0,0)}$，为整个记号继续续命。但是，这样依然是走不远的，就像多元 $I$ 函数走不远一样。

从下一节开始，我们将进入 $\Sigma_1$ 稳定序数的阶段，即便是 $\Pi_{(1,0)}$ 这样的序数，在 $\Sigma_1$ 稳定序数中也算是相当小的。