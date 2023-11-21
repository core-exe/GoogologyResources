#! https://zhuanlan.zhihu.com/p/667872804
# 大数数学入门（Part 3.2-递归不可达序数）

## 递归不可达序数 $I$

虽然 $(1-)^{(2)}$ 和 $(2)$ 的最小元都是 $\Omega$，但是对它们做 $1-$ 是不同的结果。对于前者，容许点是 $\Omega_2$，而后者的容许点是 $I = 2\; 1-2$。

因此，我们期望一个 OCF，它能够折叠 $(1-)^X 2$，而不是 $(1-)^X (1-)^{(2)}$。这个 OCF 以 $I$ 为下标。

我们可以尝试定义这样的OCF，来观察它的行为。

1. $\psi_I(0) = \Pi_2$
2. $\psi_I(X + 1) = 1 - \psi_I(X)$，如果形式标准。
3. $\psi_I(\# \sim I) = \psi_I(\# \sim (1,0))$

### 枚举

注意，OCF之后的第一个等号是反射模式，第二个等号是反射模式的极小元，并不表严格相等。

$\psi_I(0) = \Pi_2 = \Omega$
$\psi_I(1) = 1 - 2 = \Omega_\omega$
$\psi_I(2) = 1 - 1 - 2 = \Omega_{\omega^2}$
$\psi_I(\omega) = (1 -)^\omega 2 = \Omega_{\omega^\omega}$
$\psi_I(\psi_I(0)) = \psi_I(\Omega) = (1 -)^{(2)} 2 = \Omega_{\Omega}$
$\psi_I(\psi_I(\psi_I(0))) = \psi_I(\Omega_{\Omega}) = (1 -)^{(1 -)^{(2)} 2} 2 = \Omega_{\Omega_\Omega}$
$\psi_I(I) = \psi_I((1,0)) = (1 -)^{(1,0)} 2 = \Phi(1,0)$

> 注意，当我们用 $(1-)^{(1,0)} 2$ 的时候，我们实际表达的是 $(1-)^{\min (1-)^{(1,0)} 2} 2$。也就是，它指代的集合是 $\{\text{OFP}, \Omega_{\text{OFP} 2}, \Omega_{\text{OFP} 3}, \cdots\}$（OFP表 Omega 不动点），而不是 Omega 不动点的集合。这是因为这里的反射模式指数上的并不是反射模式，而是一个序数。

之前的 OCF 对于 Omega 不动点的塌缩实际上就是 $\psi(I)$。

从 $\psi_I(I)$ 到 $\psi_I(I+1)$ 的路很长，我们在 $\psi$ 下枚举一部分。注意，$\psi(\psi_I(I+1))$ 并不标准。

$\psi(I)$
$\psi(I+1)$
$\psi(I+\psi_I(0))$
$\psi(I+\psi_I(I))$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(1)) = \psi(I+\psi_I(I) \omega)$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(I)) = \psi(I+\psi_I(I)^2)$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(I + \psi_I(I))) = \psi(I+\psi_I(I)^3)$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(I + \psi_{\Omega_{\psi_I(I)}+1}(1))) = \psi(I+\psi_I(I)^\omega)$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(I + \psi_{\Omega_{\psi_I(I)}+1}(1) + \psi_I(I))) = \psi(I+\psi_I(I)^{\omega+1})$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(I + \psi_{\Omega_{\psi_I(I)}+1}(I))) = \psi(I+\psi_I(I)^{\psi_I(I)})$
$\psi(I+\psi_{\Omega_{\psi_I(I)}+1}(I + \psi_{\Omega_{\psi_I(I)}+1}(I + \psi_I(I)))) = \psi(I+\psi_I(I)^{\psi_I(I)^2})$
$\psi(I+\Omega_{\psi_I(I)+1})$

> $\Omega_{\psi_I(I)+1}$ 是 $\Pi_2 \text{ aft } \psi_I(I)$，它折叠了 $\psi_I(I)$ 的运算。

此后，我们稍微加快一下脚步：

$\Omega_{\psi_I(I)+2}$
$\Omega_{\psi_I(I)+\omega} = 1-2 \text{ aft }\psi_I(I)$
$\Omega_{\psi_I(I)+\Omega} = (1-)^{(2)} 2 \text{ aft }\psi_I(I)$
$\Omega_{\psi_I(I) 2} = \text{2nd } (1-)^{(1,0)} 2$
$\Omega_{\psi_I(I) 3} = \text{3rd } (1-)^{(1,0)} 2$
$\psi_I(I+1) = \Omega_{\psi_I(I) \omega} = 1-((1-)^{(1,0)} 2)$（我们此后会经常使用括号来表示不动点记号 $(1,0)$ 的作用范围）
$\psi_I(I+\Omega) = \Omega_{\psi_I(I) \Omega}$
$\psi_I(I+\psi_I(I)) = \Omega_{\psi_I(I)^2}$
$\psi_I(I+\psi_{\Omega_{\psi_I(I)}+1}(1)) = \Omega_{\psi_I(I)^\omega}$
$\psi_I(I+\psi_{\Omega_{\psi_I(I)}+1}(I)) = \Omega_{\psi_I(I)^{\psi_I(I)}}$
$\psi_I(I+\psi_{\Omega_{\psi_I(I)}+1}(I+\psi_{\Omega_{\psi_I(I)}+1}(I))) = \Omega_{\psi_I(I)^{\psi_I(I)^{\psi_I(I)}}}$

然后：

$\psi_I(I+\Omega_{\psi_I(I)+1}) = \Omega_{\Omega_{\psi_{I}(I)+1}}$

注意，它并不是 $\Omega_{\psi_I(I)^{\psi_I(I)^{\cdots}}}$，但是它会塌缩成 $\Omega_{\psi_I(I)^{\psi_I(I)^{\cdots}}}$，这个和之前见到的“卡住”的情况：

$\psi(I+\psi_I(I+\Omega_{\psi_I(I)+1})) = \psi(I+\psi_I(I+\psi_{\Omega_{\psi_I(I)+1}} ( \cdots))) = \psi(I+\Omega_{\psi_I(I)^{\psi_I(I)^{\cdots}}}) = \psi(I+\Omega_{\Omega_{\psi_I(I)+1}})$

继续下去，我们将会达到第二个 $\Omega$ 不动点：

$\psi_I(I+\psi_I(I+\Omega_{\psi_I(I)+1})) = \Omega_{\Omega_{\Omega_{\psi_{I}(I)+1}}}$
$\psi_I(I+\psi_I(I+\psi_I(I+\Omega_{\psi_I(I)+1}))) = \Omega_{\Omega_{\Omega_{\Omega_{\psi_{I}(I)+1}}}}$

然后，我们达到 $\psi_I(I2) = (1-)^{(1,1)} 2$，继续下去我们可以知道 $\psi_I(In) = (1-)^{(1,n)} 2$。

$I$ 本身也是可以进行算术运算的，例如 $I\omega$。这样，我们就可以使用比 $I$ 大的非递归序数去折叠它：$\Omega_{I+1} = 2 \text{ aft } I$，有 $\psi_{\Omega_{I+1}}(1) = I\omega$。注意，$\Omega_{I+1}$ 和 $\Omega_{\psi_I(I)+1}$ 是两个不同的数。

$\psi(\psi_{\Omega_{I+1}}(1)) = \psi(I\omega)$
$\psi(\Omega_{I+1}) = \psi(I^{I^\cdots}) = \text{JO}$ 
$\psi(\Omega_{I2})$
$\psi(\Omega_{\psi_{\Omega_{I+1}(1)}})$
$\psi(\Omega_{\Omega_{I+1}})$
$\psi(\Omega_{\Omega_{\Omega_{I+1}}})$

我们迎来了 $I$ 之后的 $\Omega$ 不动点。使用 $I$ 塌缩就不管用了，因为这个不动点本身比 $I$ 大。

## 引入多个递归不可达序数

在之前定义 $\Omega$ 的OCF达到极限时，我们引入 $\Omega_2$，来折叠 $\Omega$ 之上的运算。现在也一样，我们引入 $I_2 = \text{2nd } 2\;1-2$。$\psi_{I_2}$ 的规则与 $\psi_I$ 几乎一致，只有一个改动：

1. $\psi_{I_2}(0) = 2 \text{ aft } 2\;1-2$。

因此，我们就可以来折叠 $I$ 之上的 $\Pi_2$，$I$ 之后的 $\Omega$ 不动点就是 $\psi_{I_2}(I_2)$。$I_2$ 之后也会有新的 $\Omega$ 不动点，我们也可以同样的引入 $I_3 = \text{3rd } 2\;1-2$ 去折叠它们。

之后，我们会达到 $I_\omega = 1-2\; 1-2 = \sup\{I,I_2,I_3,\cdots\}$。和 $\Omega_\omega$ 一样，它并不是一个 $\Pi_2$ 序数，因此不能作为 OCF 的下标。再之后：

$I_{\omega+1} = 2\;1-2 \text{ aft } 1-2\;1-2$
$I_{\omega 2} = \text{2nd } 1-2\;1-2$
$I_{\omega^2} = 1-1-2\;1-2$
$I_{\omega^\omega} = (1-)^{(1)} 2\;1-2$
$I_{\Omega} = (1-)^{(2)} 2\;1-2$
$I_I = (1-)^{2\;1-2} 2\;1-2$
$I_{I_I} = (1-)^{(1-)^{2\;1-2}2\;1-2} 2\;1-2$
$I_{I_{\cdots}} = (1-)^{(1,0)} 2\; 1-2$

我们到达了 $I$ 函数本身的不动点，仿照之前的思路，我们会去找 $(1-)^{x} 2\;1-2$ 无法达到的点，也就是 $2\;1-2\;1-2$。这个序数被记为 $I(1,0)$，有的地方会写成 $\Omega(2,0)$。它以及更高的序数的性质将在下一节讨论。

此外，我们试图给出比较通用的递归不可达序数为下标的 OCF 的计算规则：

1. $\psi_{2\;1-X}(0) = X$
2. $\psi_{2\;1-X}(\alpha+1) = 1-\psi_{2\;1-X}(\alpha)$，如果形式标准。
3. $\psi_{2\;1-X}(\# \sim 2\;1-X) = \psi_{2\;1-X}(\# \sim (1,0))$

当然，$I$ 不动点并不是这个记号的极限，因为这个记号适用于 $2\;1-2\;1-2$ 这样的序数。