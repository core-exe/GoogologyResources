#! https://zhuanlan.zhihu.com/p/664215059
# 大数数学入门（Part 3.1-OCF与反射）

在上一章中，我们通过引入非递归序数函数 $\Omega_x$ 和序数塌缩函数 $\psi$ 来折叠不动点。在最后，我们到达了第一个 $\Omega$ 不动点。我们可以像引入 Veblen 函数一样，使用 $\Phi(1,\alpha)$ 来表示 $\Omega_x$ 的第 $\alpha$ 个不动点，来将这个系统继续进行下去。但是，这样做是不必要的：我们很快就会拓展到越来越复杂的 $\Phi$ 函数。

除此之外，还有另外一个方法：我们引入一个全新的大序数 $I$。不同于 $\Omega$，$I$ 之下的序数通过任何的 **包含 $\Omega_x$** 的递归记号都无法达到它。这个序数的地位与大基数中的不可达基数相当，我们称为递归不可达序数。它便可以用来产生一套新的序数塌缩函数。

在此之前，让我们先讲一讲初步的反射。

## 反射

### $\Pi_1$ 反射

反射表达式 $X$ 表示的是一个序数的集合。想要从其中取出一个序数，就使用 $n \text{ th } X$ 来表示它的第 $n$ 个序数，特殊的，$\min X$ 表示最小的序数，在没有歧义的情况下也可以写作 $X$。此外，使用 $X \text{ aft } \alpha$ 表示 $X$ 中的大于 $\alpha$ 的子集。

在最开始，我们有全体序数构成的集合（实际上是类，但是我们不去想这个。）：$\{0,1,2,\cdots,\omega,\omega+1, \cdots, \omega2, \cdots\}$，我们用 $\Pi_0$ 表示它。我们将它其中每 $\omega$ 个序数归为一组取上界，所得到的便是 $\Pi_1$。

$\Pi_1 = \{\omega, \omega2, \omega3, \cdots\}$。

我们可以在 $\Pi_1$ 上面再进行一次这样的操作：每 $\omega$ 个序数归为一组取上界，所得到的是 $\Pi_1 \text{ onto } \Pi_1$。我们简写为 $\Pi_1 - \Pi_1$：

$\Pi_1 - \Pi_1 = \{\omega^2, \omega^2 2,\cdots\}$。

我们可以继续做 $\Pi_1 -$ 的操作：

$\Pi_1 - \Pi_1 - \Pi_1 = \{\omega^3, \omega^3 2, \cdots \}$

并且这个 $\Pi_1 -$ 操作可以进行序数次。我们使用上标表示进行的次数。上标中的反射模式实际上表示的是最小的序数。

$(\Pi_1 -)^4 = \{\omega^4, \omega^4 2, \cdots\}$
$(\Pi_1 -)^{\Pi_1} = \{\omega^\omega, \cdots\}$
$(\Pi_1 -)^{\text{2nd }\Pi_1} = \{\omega^{\omega2}, \cdots\}$
$(\Pi_1 -)^{\Pi_1 - \Pi_1} = \{\omega^{\omega^2}, \cdots\}$
$(\Pi_1 -)^{(\Pi_1 -)^{\Pi_1}} = \{\omega^{\omega^\omega}, \cdots\}$

此后，我们就会到达不动点。

### $\Pi_2$ （直到 $\Pi_2 \cap (\Pi_1 - \Pi_2)$）

单凭 $\Pi_1$ 反射的递归记号达不到的序数就是 $\Pi_2$，也就是全体非递归序数构成的集合：$\Pi_2 = \{\Omega, \Omega_2, \cdots, \Omega_{\omega+1}, \Omega_{\omega+2}, \cdots\}$。注意，$\Omega_\omega$ 不是非递归序数。

我们可以对它取 $\Pi_1 -$，得到的是 $\Pi_1 - \Pi_2 = \{\Omega_{\omega}, \Omega_{\omega 2}, \cdots\}$。

继续下去，可以得到：

$\Pi_1 - \Pi_1 - \Pi_2 = \{\Omega_{\omega^2}, \Omega_{\omega^2 2}, \cdots, \}$
$(\Pi_1 - )^{\Pi_1} \Pi_2 = \{\Omega_{\omega^\omega}, \Omega_{\omega^\omega 2}, \cdots, \}$
$(\Pi_1 - )^{\Pi_2} \Pi_2 = \{\Omega_{\Omega}, \Omega_{\Omega 2}, \cdots, \}$
$(\Pi_1 - )^{\text{2nd } \Pi_2} \Pi_2 = \{\Omega_{\Omega_1}, \Omega_{\Omega_1 2}, \cdots, \}$
$(\Pi_1 - )^{\Pi_1 - \Pi_2} \Pi_2 = \{\Omega_{\Omega_\omega}, \Omega_{\Omega_\omega 2}, \cdots, \}$
$(\Pi_1 - )^{(\Pi_1 - )^{\Pi_2} \Pi_2} \Pi_2 = \{\Omega_{\Omega_\Omega}, \Omega_{\Omega_\Omega 2}, \cdots, \}$

最后，我们发现此前达到的 $\Omega$ 不动点是 $(\Pi_1 - )^{x} \Pi_2$ 的不动点。

> 此后，如果没有歧义，我们就用数字来表示反射表达式，例如 $1-1-2$ 表示 $\Pi_1 - \Pi_1 - \Pi_2$。如果有歧义，在反射之外会加一层括号，例如 $(1-)^{(2)} 2$ 表示 $(\Pi_1 - )^{\Pi_2} \Pi_2$。

我们考虑这样一个序数：它既是 $1-2$，也是 $(2)$。我们发现，此前遇到的所有的序数都不满足这样的条件，哪怕是 $\Phi(\alpha, \beta)$ 也不满足这样的条件。这个序数是 $\Omega_x$ 的形式，并且是一个非递归序数，也就是说，它就是之前提到的递归不可达序数 $I$，通过 $\Omega_x$ 的递归记号达不到的序数：

$\Pi_2 \cap (\Pi_1 - \Pi_2) = \{I,I_2,I_3,\cdots, I_{\omega+1}, \cdots\}$

当然，$I_x$ 是 $\Omega$ 不动点。

> 我们使用空格来简写 $\cap$，也就是 $\Pi_2 \cap (\Pi_1 - \Pi_2) = 2 \; 1-2$。

## 反射与OCF

我们可以重新考虑一下我们此前的OCF的定义。此前的OCF的定义是将一个大序数去塌缩成小的序数，而我们现在可以考虑一个将大序数塌缩为小的反射表达式的OCF。

下面实际上就是使用反射的语言将之前定义的 OCF 重新表述。如果你第一次遇到反射，请对照之前几节的内容试图理解这里的每一个式子。此外，打一个很小的补丁：$\psi(0) = 1, \psi(1) = \omega, \psi(2) = \omega^2, \cdots$。从 $\psi(\omega)$ 之后的值就与之前的定义重合了。我们可以对于之前的定义进行一个很小的修改来达到这样的效果。此外，我们还修改 $\psi_{\Omega_{x+1}}(0)$ 的定义：$\psi_{\Omega_{x+1}}(0) = \Omega_x$。

$\psi(0) = 1$
$\psi(0 \text{ aft } 0) = (1)$（这里的 $\Pi_0 \text{ aft }$ 实际上就是取后继序数。）
$\psi(0 \text{ aft } 0 \text{ aft } 0) = 1-1$
$\psi((1)) = (1-)^{(1)}$
$\psi(0 \text{ aft } 1) = 1- (1-)^{(1)} = (1-)^{0 \text{ aft } 1}$
$\psi(1 \text{ aft } 1) = (1-)^{(1)} (1-)^{(1)} = (1-)^{1 \text{ aft } 1}$
$\psi(1-1) = (1-)^{1-1}$
$\psi((1-)^{(1)}) = (1-)^{(1-)^{(1)}}$
$\psi((2)) = (1-)^{(1,0)} = \psi(1,0)$（这里表示不动点。）
$\psi(0 \text{ aft } 2) =  1- \psi((2))$
$\psi(0 \text{ aft } 0 \text{ aft } 2) =  1- 1- \psi((2))$
$\psi(1 \text{ aft } 2) =  (1-)^{(1)}\psi((2))$
$\psi(0 \text{ aft } 1 \text{ aft } 2) =  (1-)^{0 \text{ aft } 1}\psi((2))$
$\psi(1 \text{ aft } 1 \text{ aft } 2) =  (1-)^{1 \text{ aft } 1}\psi((2))$
$\psi(1- 1 \text{ aft } 2) =  (1-)^{1 - 1}\psi((2))$
$\psi(\psi((2)) \text{ aft } 2) =  (1-)^{\psi((2))}\psi((2))$
$\psi(\psi(\psi((2)) \text{ aft } 2) \text{ aft } 2) =  (1-)^{(1-)^{\psi((2))}\psi((2))}\psi((2))$

我们遇到了 $\psi(\Omega2) = \psi(\Omega + \psi(\Omega + \psi(\cdots)))$。注意，$2 \text{ aft } 2$ 并不是 $\Omega 2$，而是 $\Omega_2$。$\Omega 2$ 是 $(1-)^{(2)} \text{ aft } 2 = \text{2nd }(1-)^{(2)}$。$(1-)^{(2)}$ 和 $2$ 是两个不同的集合，但是它们的最小值都是 $\Omega$。

$\psi(\text{2nd }(1-)^{(2)}) = (1-)^{(1,0)}\psi((2))$
$\psi(0 \text{ aft } \text{2nd }(1-)^{(2)}) = 1-\psi(\text{2nd }(1-)^{(2)})$
$\psi(1 \text{ aft } \text{2nd }(1-)^{(2)}) = (1-)^{(1)} \psi(\text{2nd }(1-)^{(2)})$
$\psi(\psi((2)) \text{ aft } \text{2nd }(1-)^{(2)}) = (1-)^{\psi((2)) } \psi(\text{2nd }(1-)^{(2)})$
$\psi(\psi(\text{2nd }(1-)^{(2)}) \text{ aft } \text{2nd }(1-)^{(2)}) = (1-)^{\psi(\text{2nd }(1-)^{(2)}) } \psi(\text{2nd }(1-)^{(2)})$
$\psi(\psi(\psi(\text{2nd }(1-)^{(2)}) \text{ aft } \text{2nd }(1-)^{(2)}) \text{ aft } \text{2nd }(1-)^{(2)}) = (1-)^{\psi(\psi(\text{2nd }(1-)^{(2)}) \text{ aft } \text{2nd }(1-)^{(2)}) } \psi(\text{2nd }(1-)^{(2)})$

$(1,0) \text{ aft }$ 塌缩成 $+\Omega$，也就是塌缩成 $(1-)^{(2)} \text{ aft }$。
$\psi(\text{3rd }(1-)^{(2)}) = (1-)^{(1,0)}\psi(\text{2nd }(1-)^{(2)})$
$\psi(\text{4th }(1-)^{(2)}) = (1-)^{(1,0)}\psi(\text{3rd }(1-)^{(2)})$
$\psi(\text{5th }(1-)^{(2)}) = (1-)^{(1,0)}\psi(\text{4rd }(1-)^{(2)})$
$\cdots$

每 $\omega$ 个归为一组取上界，这是 $\Pi_1-$ 的定义。同时，从这里开始，$\psi_{\Omega_2}$ 开始发挥作用：

$\psi(\psi_{\text{2nd } 2}(1)) = \psi((1-)^{0 \text{ aft } 2}) = \psi(1-(1-)^{(2)}) = \psi(1-\psi_{\text{2nd } 2}(0))$
$\psi(0 \text{ aft } \psi_{\text{2nd } 2}(1)) = 1-  \psi(\psi_{\text{2nd } 2}(1))$
$\psi((1-)^{(2)} \text{ aft } \psi_{\text{2nd } 2}(1)) = (1-)^{(1,0)} \psi(\psi_{\text{2nd } 2}(1))$
$\psi(\text{2nd } (1-)^{(2)} \text{ aft } \psi_{\text{2nd } 2}(1)) = (1-)^{(1,0)} \psi((1-)^{(2)} \text{ aft } \psi_{\text{2nd } 2}(1))$
$\psi(\text{2nd }\psi_{\text{2nd } 2}(1)) = \psi(\psi_{\text{2nd } 2}(1) \text{ aft } \psi_{\text{2nd } 2}(1)) = \psi(1-(1-)^{(2)} \text{ aft } \psi_{\text{2nd } 2}(1))$
$\psi(\text{3rd }\psi_{\text{2nd } 2}(1)) = \psi(\psi_{\text{2nd } 2}(1) \text{ aft }\text{2nd } \psi_{\text{2nd } 2}(1))$
$\psi(\psi_{\text{2nd } 2}(2)) = \psi(1- \psi_{\text{2nd } 2}(1))$

这里就是 $\psi(\psi_{\Omega_2}(2)) = \psi(\Omega \omega^2)$。即使是对于 $\psi_{\text{2nd } 2}$，也有 $\psi_{\text{2nd } 2}(0 \text{ aft } X) = 1-\psi_{\text{2nd } 2}(X)$。

$\psi(\psi_{\text{2nd } 2}(3)) = \psi(1 - \psi_{\text{2nd } 2}(2))$
$\psi(\psi_{\text{2nd } 2}((1))) = \psi((1-)^{(1)} \psi_{\text{2nd } 2}(0))$
$\psi(\psi_{\text{2nd } 2}(\psi((2)))) = \psi((1-)^{\psi((2))} \psi_{\text{2nd } 2}(0))$
$\psi(\psi_{\text{2nd } 2}(\psi(\psi_{\text{2nd } 2}(0)))) = \psi((1-)^{\psi(\psi_{\text{2nd } 2}(0))} \psi_{\text{2nd } 2}(0))$
$\psi(\psi_{\text{2nd } 2}((2))) = \psi((1-)^{(2)} \psi_{\text{2nd } 2}(0)) = \psi((1-)^{(1,0)} \psi_{\text{2nd } 2}(0))$（依然是使用 $\Omega$ 折叠不动点。）
$\psi(\psi_{\text{2nd } 2}(0 \text{ aft } 2)) = \psi(1 - \psi_{\text{2nd } 2}((2)))$
$\psi(\psi_{\text{2nd } 2}(\text{2nd } (1-)^{(2)})) = \psi((1-)^{(1,0)} \psi_{\text{2nd } 2}((2)))$
$\psi(\psi_{\text{2nd } 2}(\psi_{\text{2nd } 2}(1))) = \psi(\psi_{\text{2nd } 2}(1-(1-)^{(2)}))$
$\psi(\psi_{\text{2nd } 2}(\psi_{\text{2nd } 2}(\psi_{\text{2nd } 2}(1)))) = \psi(\psi_{\text{2nd } 2}(\psi_{\text{2nd } 2}(1-(1-)^{(2)})))$

然后是 $\Omega_2$：

$\psi(\text{2nd } 2) = \psi((1-)^{\text{2nd } 2})$
$\psi((1-)^{(2)} \text{ aft }\text{2nd } 2) = (1-)^{(1,0)} \psi(\text{2nd } 2)$
$\psi(\psi_{\text{2nd }2}(1) \text{ aft }\text{2nd } 2)$
$\psi(\psi_{\text{2nd }2}((2)) \text{ aft }\text{2nd } 2)$
$\psi(\psi_{\text{2nd }2}(\text{2nd }2) \text{ aft }\text{2nd } 2)$
$\psi(\psi_{\text{2nd }2}(\psi_{\text{2nd }2}(\text{2nd }2) \text{ aft }\text{2nd } 2) \text{ aft }\text{2nd } 2)$
$\psi(\text{2nd } (1-)^{\text{2nd }2})$，这是 $\psi(\Omega_2 2)$
$\psi((1-)^{(2)} \text{ aft }\text{2nd } (1-)^{\text{2nd }2}) = \psi((1,0) \text{ aft }\text{2nd } (1-)^{\text{2nd }2})$
$\psi(\text{3rd } (1-)^{\text{2nd }2}) = \psi((1-)^{\text{2nd }2} \text{ aft }\text{2nd } (1-)^{\text{2nd }2}) = \psi(\psi_{\text{2nd } 2}(\cdots) \text{ aft }\text{2nd } (1-)^{\text{2nd }2})$
$\psi(\psi_{\text{3rd 2}}(1))$

就不继续进行下去了。

### 计算规则

让我们重新总结现在的 OCF 的规则。目前遇到的 OCF 的计算方式实际上只需要三个规则便可以计算清楚：

1. $\psi_X(0)$ 是什么
2. $\psi_X(\alpha + 1) = \psi_X(0\text{ aft } \alpha)$ 是什么
3. $\psi_X(\# \sim X)$ 是什么

只要定义清楚这三个规则，我们就可以去刻画一个 OCF 的计算。

那么，对于这三个规则，我们上面的 OCF 是这样计算的：

1. $\psi_{2 \text{ aft }X}(0) = X$（特殊的，$\psi_{(2)}(0) = 1$）
2. $\psi_{2 \text{ aft }X}(0\text{ aft } \alpha) = 1 - \psi_{2 \text{ aft }X}(\alpha)$，如果形式标准。
3. $\psi_{2 \text{ aft }X}((1-)^{2 \text{ aft } X} \text{ aft } \alpha) = \psi_{2 \text{ aft }X}((1,0) \text{ aft } \alpha)$，如果形式标准。如果最外层的下标小于 $2 \text{ aft }X$，那么最外层的下标不变。

说到底，这里讨论的依然是以前的 OCF，只不过现在套上了反射的皮。所折叠的东西实际上也只是 $(1-)^\cdots (1-)^X$ 这样的形式，而没有试图折叠 $(1-)^\cdots 2$。这件事情留给下一节。