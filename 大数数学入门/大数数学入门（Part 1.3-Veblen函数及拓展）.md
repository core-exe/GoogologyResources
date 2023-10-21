#! https://zhuanlan.zhihu.com/p/661866022
# 大数数学入门（Part 1.3-Veblen函数及拓展）

在上一节中，我们讲到了指数不动点以及更加高阶的不动点，而这是二元Veblen函数的一部分。这一节中我们将讲解Veblen函数和它的拓展。

---

## 二元Veblen函数

在上一节中，我们定义了$\varphi(\alpha, \beta)$的一部分：

1. $\varphi(\alpha+1, 0) = \sup\{0, \varphi(\alpha,0), \varphi(\alpha,\varphi(\alpha,0)), \cdots\}$
2. $\varphi(\alpha+1, \beta+1) = \sup\{\varphi(\alpha+1,\beta), \varphi(\alpha,\varphi(\alpha+1,\beta)), \varphi(\alpha,\varphi(\alpha,\varphi(\alpha+1,\beta))), \cdots\}$
3. $\beta$ 是极限序数： $\varphi(\alpha+1, \beta)[n] = \varphi(\alpha+1,\beta[n])$

对于前一个变量是后继序数的情况已经考虑到了，让我们试图给出余下的定义。
首先是前一个变量等于0的情况：由上面的规则和前一章我们知道 $\varepsilon_\beta = \varphi(1, \beta)$ 是第$\beta$个指数不动点，也就是说：

4. $\varphi(0, \beta) = \omega^\beta$

然后是前一个变量是非零极限序数的情况，这里比较复杂。首先我们希望 $\varphi(\omega,0) = \sup_n\{\varphi(n,0)\}$，也就是：

5. $\alpha$ 是极限序数： $\varphi(\alpha, 0)[n] = \varphi(\alpha[n], 0)$

那么 $\varphi(\omega, 1)$ 便是从 $\varphi(\omega,0)$ 开始的由任何后继和 $\varphi(n,\cdot)$ 都无法有限表示的点，$\varphi(\omega, 1) = \sup_n\{\varphi(n, \varphi(\omega,0)+1)\}$：

6. $\alpha$ 是极限序数： $\varphi(\alpha, \beta+1)[n] = \varphi(\alpha[n], \varphi(\alpha, \beta)+1)$

最后，$\varphi(\omega, \omega)$ 是 $\varphi(\omega, n)$ 的上界：

7. $\alpha,\beta$ 是极限序数： $\varphi(\alpha, \beta)[n] = \varphi(\alpha, \beta[n])$

我们就补全了Veblen函数的定义。注意，规则3、7和4的一部分可以进行合并：
$\beta$ 是极限序数，$\varphi(\alpha,\beta)[n] = \varphi(\alpha, \beta[n])$

### 二元Veblen函数的枚举

$\varphi(1,0) = \varepsilon_0$
$\varphi(1,1) = \varepsilon_1$
$\varphi(1,\omega)$
$\varphi(1,\varphi(1,0))$
$\varphi(1,\varphi(1,\varphi(1,0)))$
$\varphi(2,0)$
$\varphi(1,\varphi(2,0)+1)$
$\varphi(1,\varphi(1,\varphi(2,0)+1))$
$\varphi(2,1)$
$\varphi(2,\omega)$
$\varphi(2,\varphi(1,0))$
$\varphi(2,\varphi(2,0))$
$\varphi(3,0)$
$\varphi(3,1)$
$\varphi(3,\varphi(3,0))$
$\varphi(4,0)$
$\varphi(5,0)$
$\varphi(\omega,0)$
$\varphi(1,\varphi(\omega,0)+1)$
$\varphi(2,\varphi(\omega,0)+1)$
$\varphi(\omega,1)$
$\varphi(\omega,\omega)$
$\varphi(\omega,\varphi(\omega, 0))$
$\varphi(\omega+1,0)$
$\varphi(\omega2,0)$
$\varphi(1, \varphi(\omega2,0)+1)$
$\varphi(2, \varphi(\omega2,0)+1)$
$\varphi(\omega, \varphi(\omega2,0)+1)$
$\varphi(\omega+1, \varphi(\omega2,0)+1)$
$\varphi(\omega2, 1)$
$\varphi(\omega2, \omega)$
$\varphi(\omega2+1, 0)$
$\varphi(\omega^2, 0)$
$\varphi(\varphi(1, 0), 0)$
$\varphi(\varphi(\varphi(1, 0), 0), 0)$
$\cdots$

这是$\varphi(\cdot, 0)$的第一个不动点。

$$\text{Feferman–Schütte Ordinal} = \Gamma_0 = \sup\{\varphi(1,0), \varphi(\varphi(1, 0), 0), \varphi(\varphi(\varphi(1, 0), 0), 0), \cdots \}$$

## 多元Veblen函数

让我们定义另一个版本的 $\varphi$ ：它的规则除了 $\varphi_{1}(0,\beta)$ 之外和 $\varphi$ 一致，$\varphi_{1}(0,\beta)$ 是 $\varphi(\cdot, 0)$ 的第 $\beta$ 个不动点。

它在第一个变量 $\varphi_{1}(\cdot, 0)$ 上也有不动点，我们可以再定义一个 $\varphi_2$ ：它的规则除了 $\varphi_{2}(0,\beta)$ 之外和 $\varphi$ 一致，$\varphi_{2}(0,\beta)$ 是 $\varphi_{1}(\cdot, 0)$ 的第 $\beta$ 个不动点。

......

我们回到了上一节结尾的情况，因此我们不妨把这个下标提到前面来：

$$
\varphi(\alpha, \cdot, \cdot) = \varphi_\alpha(\cdot, \cdot)
$$

它的第一个变量的不动点定义的一系列函数引出了四个变量的Veblen函数：

$$
\varphi(\alpha, \cdot, \cdot, \cdot) = \varphi_\alpha(\cdot, \cdot, \cdot)
$$

先别走太远，让我们试着形式化的定义多元Veblen函数。如果一个变量及其左边的变量均是0，那么我们将这一部分变量隐去不写。此外，我们将多元Veblen函数的变量分为四个部分$\varphi(S,\alpha,Z,\beta)$：

1. $S$ 是一列变量，它的内部结构应该不影响计算。
2. $\alpha$ 是一个非零变量。
3. $Z$ 是一串0，可以为空。
4. $\beta$ 是末位变量。

此后，我们给出Veblen函数的形式化定义。

一元Veblen函数的基础情况：

1. $\varphi(\beta) = \omega^\beta$

最右非零位是极限序数的情况：

2. $\beta$ 是极限序数：$\varphi(S,\alpha,Z,\beta)[n] = \varphi(S,\alpha,Z,\beta[n])$
3. $\alpha$ 是极限序数：$\varphi(S,\alpha,Z,0)[n] = \varphi(S,\alpha[n],Z,0)$

$\alpha$ 是后继序数的情况，这种情况下表示一个函数的第 $\beta$ 个不动点：

4. $\varphi(S,\alpha + 1, Z, 0) = \sup\{0, \varphi(S, \alpha, 0, Z), \varphi(S, \alpha, \varphi(S, \alpha, 0, Z), Z), \cdots\}$
5. $\varphi(S,\alpha + 1, Z, \beta + 1) = \sup\{\varphi(S,\alpha + 1, Z, \beta)+1, \varphi(S, \alpha, \varphi(S,\alpha + 1, Z, \beta)+1, Z), \varphi(S, \alpha, \varphi(S, \alpha, \varphi(S,\alpha + 1, Z, \beta)+1, Z), Z), \cdots\}$

$\alpha$ 是极限序数的情况，这种情况下表示在它之下的一系列函数的上界：

6. $\alpha$ 是极限序数：$\varphi(S, \alpha, Z, \beta + 1)[n] = \varphi(S, \alpha[n], Z, \varphi(S, \alpha, Z, \beta)+1)$

这样，我们就定义了所有的情况。

### 多元Veblen函数的枚举

$\varphi(1,0,0)$
$\varphi(1,\varphi(1,0,0)+1)$
$\varphi(2,\varphi(1,0,0)+1)$
$\varphi(\omega,\varphi(1,0,0)+1)$
$\varphi(\varphi(1,0),\varphi(1,0,0)+1)$
$\varphi(\varphi(\varphi(1,0),0),\varphi(1,0,0)+1)$
$\varphi(\varphi(1,0,0), 1)$
$\varphi(\varphi(1,0,0), \varphi(1,0))$
$\varphi(\varphi(1,0,0), \varphi(1,0,0))$
$\varphi(\varphi(1,0,0), \varphi(\varphi(1,0,0), 1))$
$\varphi(\varphi(1,0,0)+1, 0)$
$\varphi(\varphi(\varphi(1,0,0)+1, 0), 0)$
$\varphi(1,0,1)$
$\varphi(\varphi(1,0,1)+1, 0)$
$\varphi(1,0,2)$
$\varphi(1,0,\omega)$
$\varphi(1,0,\varphi(1,0,0))$
$\varphi(1,0,\varphi(1,0,\varphi(1,0,0)))$
$\varphi(1,1,0)$
$\varphi(\varphi(1,1,0)+1,0)$
$\varphi(\varphi(\varphi(1,1,0)+1,0),0)$
$\varphi(1,0,\varphi(1,1,0)+1)$
$\varphi(1,0,\varphi(1,0,\varphi(1,1,0)+1))$
$\varphi(1,1,1)$
$\varphi(1,1,\varphi(1,1,0))$
$\varphi(1,2,0)$
$\varphi(1,\omega,0)$
$\varphi(1,\varphi(1,0,0),0)$
$\varphi(2,0,0)$
$\varphi(\varphi(2,0,0)+1,0)$
$\varphi(1,0,\varphi(2,0,0)+1)$
$\varphi(1,0,\varphi(1,0,\varphi(2,0,0)+1))$
$\varphi(1,1,\varphi(2,0,0)+1)$
$\varphi(1,2,\varphi(2,0,0)+1)$
$\varphi(1,\varphi(1,0,0),\varphi(2,0,0)+1)$
$\varphi(1,\varphi(1,\varphi(1,0,0),0),\varphi(2,0,0)+1)$
$\varphi(1,\varphi(2,0,0),1)$
$\varphi(1,\varphi(2,0,0),\varphi(1,\varphi(2,0,0),1))$
$\varphi(1,\varphi(2,0,0)+1,0)$
$\varphi(1,\varphi(1,\varphi(2,0,0)+1,0),0)$
$\varphi(2,0,1)$
$\varphi(2,1,0)$
$\varphi(3,0,0)$
$\varphi(\varphi(1,0,0),0,0)$
$\varphi(1,0,0,0)$
$\varphi(1,\varphi(1,0,0,0)+1)$
$\varphi(1,0,\varphi(1,0,0,0)+1)$
$\varphi(1,0,\varphi(1,0,0,0)+1)$
$\varphi(1,\varphi(1,0,0,0),1)$
$\varphi(1,\varphi(1,0,0,0)+1,0)$
$\varphi(1,\varphi(1,\varphi(1,0,0,0)+1,0),0)$
$\varphi(2,0,\varphi(1,0,0,0)+1)$
$\varphi(\varphi(1,0,0,0),0,1)$
$\varphi(\varphi(1,0,0,0)+1,0,0)$
$\varphi(\varphi(\varphi(1,0,0,0)+1,0,0),0,0)$
$\varphi(1,0,0,1)$
$\varphi(1,0,1,0)$
$\varphi(1,1,0,0)$
$\varphi(2,0,0,0)$
$\varphi(\varphi(1,0,0,0),0,0,0)$
$\varphi(1,0,0,0,0)$
$\varphi(1,0,0,0,0,0)$
$\cdots$

最后我们达到序数：

$$
\text{SVO} = \text{Small Veblen Ordinal} = \sup\{\varphi(1),\varphi(1,0),\varphi(1,0,0),\varphi(1,0,0,0),\cdots\}
$$

这个序数距离$\text{TREE}$函数的增长率很近。

## 序元Veblen函数

到了这里，有限数量参数的Veblen函数就不够用了，考虑SVO这个极限，可以想象成参数1的位置从最右边（0）开始逐渐递增，移动到无穷远的位置（$\omega$）。我们可以这样表示参数的位置在超限序数：$1@\omega$，这样，

$$
\text{SVO} = \varphi(1@\omega) = \sup_{n<\omega}\{\varphi(1@n)\}
$$

当然，$\varphi(x@\omega)$ 的不动点会使参数位置进一，达到 $\varphi(x@(\omega+1))$。
此外，我们要求 $\varphi$ 的参数中只有有限个不是零，毕竟符号是要有限长的。这样，我们就将 $\varphi$ 的参数写成这样的形式：

$$
\varphi(\alpha_n@\beta_n, \cdots, \alpha_1@\beta_1, \alpha)
$$

要求 $\beta_1<\beta_2<\cdots$，$\alpha_1,\alpha_2,\cdots$ 非零。最后的 $\alpha$ 在零位置，可以省略不写。此外，位置大于 $\beta_1$ 类比之前的 $S$，具体结构不影响计算，因此用 $S$ 来表示。现在，我们就可以给出序元Veblen函数的定义了。

一元Veblen函数的基础情况：

1. $\varphi(\alpha) = \omega^\alpha$

末端非零参数是极限序数的情况：

2. $\alpha$ 是极限序数：$\varphi(S,\alpha_1@\beta_1, \alpha)[n] = \varphi(S,\alpha_1@\beta_1, \alpha[n])$
3. $\alpha_1$ 是极限序数：$\varphi(S, \alpha_1@\beta_1)[n] = \varphi(S, \alpha_1[n]@\beta_1)$

后继序数在极限序数的位置，可以看成是从下面“逐渐上升”到这个位置：

4. $\beta_1$ 是极限序数：$\varphi(S,(\alpha_1+1)@\beta_1)[n] = \varphi(S,\alpha_1@\beta_1,1@\beta_1[n])$
5. $\beta_1$ 是极限序数：$\varphi(S,(\alpha_1+1)@\beta_1, \alpha+1)[n] = \varphi(S,\alpha_1@\beta_1,1@\beta_1[n],\varphi(S,(\alpha_1+1)@\beta_1, \alpha))$

后继序数在后继序数的位置，沿用不动点的定义，这里就简写了：

6. $\varphi(S,(\alpha_1+1)@(\beta_1+1))$ 是 $\varphi(S, \alpha_1@(\beta_1+1), x@\beta_1)$ 的第 $0$ 个不动点。
7. $\varphi(S,(\alpha_1+1)@(\beta_1+1), \beta+1)$ 是 $\varphi(S, \alpha_1@(\beta_1+1), x@\beta_1)$ 的第 $\beta+1$ 个不动点。

极限序数在任意的位置，零位参数非零，表示它之下的一系列函数的上界：

8. $\alpha_1$ 是极限序数：$\varphi(S, \alpha_1@\beta_1, \alpha+1)[n] = \varphi(S, \alpha_1[n]@\beta_1,\varphi(S, \alpha_1@(\beta_1+1), \alpha)+1)$

### 序元Veblen函数的枚举

$\varphi(1@\omega)$
$\varphi(1@\omega,1)$
$\varphi(1@\omega,1@1)$
$\varphi(1@\omega,1@2)$
$\varphi(2@\omega)$
$\varphi(3@\omega)$
$\varphi(\omega @\omega)$
$\varphi(1@1, \varphi(\omega @\omega)+1)$
$\varphi(1@2, \varphi(\omega @\omega)+1)$
$\varphi(1@\omega, \varphi(\omega @\omega)+1)$
$\varphi(1@\omega, 1@1, \varphi(\omega @\omega)+1)$
$\varphi(2@\omega, \varphi(\omega @\omega)+1)$
$\varphi(3@\omega, \varphi(\omega @\omega)+1)$
$\varphi(\omega @\omega, 1)$
$\varphi(\omega @\omega, 1@1)$
$\varphi(\omega+1 @\omega)$
$\varphi(\varphi(1@\omega) @\omega)$
$\varphi(1@\omega+1)$
$\varphi(1@\omega+2)$
$\varphi(1@\omega2)$
$\varphi(1@\varphi(1,0))$
$\varphi(1@\varphi(1,0,0))$
$\varphi(1@\varphi(1,0,0,0))$
$\varphi(1@\varphi(1@\omega))$
$\varphi(1@\varphi(1@\varphi(1@\omega)))$
$\cdots$

最后我们达到序数：

$$
\text{LVO} = \text{Large Veblen Ordinal} = \sup\{\varphi(1,0), \varphi(1@\varphi(1,0)), \varphi(1@\varphi(1@\varphi(1,0))), \cdots\}
$$

这是 $\varphi(1@x)$ 的第一个不动点。

## 弱Veblen模式

对于Veblen函数的大家常用的拓展就结束了，但是我们实际上还可以给它续命。

我们注意到对于递增的序数函数$f$，不动点的现象是普遍存在的。如果我们将Veblen函数的一元基本情况修改为$\varphi(x) = f(x)$，在此之上便可以定义一系列类似Veblen函数的形式，我们称为弱Veblen模式，而 $f$ 的第 $x$ 个不动点在没有歧义的情况下，就可以写成 $f(1,0)$，此后我们有时会看到这样的表示。
而 $f(x) = \varphi(1@x)$ 满足这个性质，我们可以同样在这里使用弱Veblen模式：

$$
\text{LVO} = \varphi(1@(1,0))
$$

在此之上，有 $\varphi(1@(2,0))$，$\varphi(1@(1,0,0))$，$\varphi(1@(1@\omega))$，$\varphi(1@(1@\varphi(1@(1,0))))$，此后我们可以再度使用弱Veblen模式来表示这个新产生的不动点：$\varphi(1@(1@(1,0)))$。我们可以不断的进行下去。

### 枚举

$\varphi(1@(1,0))$
$\varphi(1@\varphi(1@(1,0))+1)$
$\varphi(1@\varphi(1@\varphi(1@(1,0))+1))$
$\varphi(1@\varphi(1@\varphi(1@\varphi(1@(1,0))+1)))$
$\varphi(1@(1,1))$
$\varphi(1@(1,\varphi(1@(1,0))))$
$\varphi(1@(1,\varphi(1@(1,\varphi(1@(1,0))))))$
$\varphi(1@(2,0))$
$\varphi(1@(\varphi(1@(1,0)),0))$
$\varphi(1@(1,0,0))$
$\varphi(1@(1,\varphi(1@(1,0,0))+1))$
$\varphi(1@(\varphi(1@(1,0,0)),1))$
$\varphi(1@(1,0,1))$
$\varphi(1@(1,1,0))$
$\varphi(1@(2,0,0))$
$\varphi(1@(1@3))$
$\varphi(1@(1@\omega))$
$\varphi(1@(1@\varphi(1@(1,0))))$
$\varphi(1@(1@\varphi(1@(1@\omega))))$
$\varphi(1@(1@(1,0)))$
$\varphi(1@\varphi(1@(1@(1,0)))+1)$
$\varphi(1@(1, \varphi(1@(1@(1,0)))+1))$
$\varphi(1@(\varphi(1@(1@(1,0))), 1))$
$\varphi(1@(1,0,\varphi(1@(1@(1,0)))+1))$
$\varphi(1@(1@\omega,\varphi(1@(1@(1,0)))+1))$
$\varphi(1@(1@\varphi(1@(1@(1,0))),\varphi(1@(1@(1,0)))+1))$
$\varphi(1@(1@(1,1)))$
$\varphi(1@(1@(1@2)))$
$\varphi(1@(1@(1@\omega)))$
$\varphi(1@(1@(1@(1,0))))$
$\varphi(1@(1@(1@(1@(1,0)))))$
$\cdots$

最后我们达到序数：

$$
\text{BHO} = \text{Bachmann–Howard ordinal} = \sup\{\varphi(1,0), \varphi(1@(1,0)), \varphi(1@(1@(1,0))), \cdots\}
$$

## 结语

实际上到这里，Veblen的各种规则加起来已经显得比较臃肿了，它在一些比较关键的节点上的复杂表现也不是很好理解，例如从 $\varphi(1,0,0)$ 到 $\varphi(1,0,1)$。当然，对于更高阶的Veblen函数拓展确实存在，而且确实能达到很高的位置，但是这里就不再继续讲解了。

从下一章节开始，我们要探索一个更加强大的序数符号：序数塌缩函数。我们这一章的一整节内容相当于序数塌缩函数的一个台阶。