#! https://zhuanlan.zhihu.com/p/663384314
# 大数数学入门（Part 2.4-更多的非递归序数）

## 引入 $\Omega_3$

我们在上一节看到，当我们引入了 $\Omega_2$ 之后，OCF的极限从 $\varphi(1,\omega)$ 增加到了超越BHO的强度。而这样的拓展，完全可以再做一次。
引入 $\Omega_3$ 的方式与引入 $\Omega_2$ 的方式没什么不同。对比之前的定义，我们写出新的定义：

1. $C_0^0(x) = \{0, 1, \Omega, \Omega_2, \Omega_3\}$，$C_0^{i}(x) = \Omega_{i} \cap \{0, 1, \Omega, \Omega_2, \Omega_3\} (i\ge 1)$
2. $C_{n+1}^i(x) = \{\alpha+\beta, \psi(\gamma), \psi_1(\gamma), \psi_2(\gamma) | \alpha,\beta,\gamma \in C_n^i(x), \gamma < x\}$
3. $C^i(x) = \bigcup_{n<\omega} C_{n+1}^i(x)$
4. $\psi_i(x) = \sup C(x) \cap \Omega_{i+1}$

具体的计算规则也与此前很像：现在引入的 $\Omega_3$ 将折叠 $\psi_2$ 的不动点。对于 $\Omega_1$ 和 $\psi_0$，我们分别使用 $\Omega$ 和 $\psi$ 来简写。

### 枚举

我们将会使用不那么标准的形式：我们允许乘法和指数的存在。

$\psi(\Omega_2 \omega)$
$\psi(\Omega_2 \omega + 1)$
$\psi(\Omega_2 \omega + \omega)$
$\psi(\Omega_2 \omega + \psi(\Omega_2 \omega))$
$\psi(\Omega_2 \omega + \Omega)$
$\psi(\Omega_2 \omega + \Omega^2)$
$\psi(\Omega_2 \omega + \Omega^\Omega)$
$\psi(\Omega_2 \omega + \psi_1(\Omega_2))$
$\psi(\Omega_2 \omega + \psi_1(\Omega_2 + \Omega))$
$\psi(\Omega_2 \omega + \psi_1(\Omega_2 + \psi_1(\Omega_2)))$
$\psi(\Omega_2 \omega + \psi_1(\Omega_2 2))$
$\psi(\Omega_2 \omega + \psi_1(\Omega_2 \omega))$
$\psi(\Omega_2 \omega + \psi_1(\Omega_2 \omega + \psi_1(\Omega_2 \omega)))$
$\psi(\Omega_2 \omega + \Omega_2)$
$\psi(\Omega_2 \omega 2)$
$\psi(\Omega_2 \Omega)$
$\psi(\Omega_2 \psi_1(\Omega_2))$
$\psi(\Omega_2^2)$
$\psi(\Omega_2^\omega)$
$\psi(\Omega_2^{\Omega_2})$
$\psi(\Omega_2^{\Omega_2^{\Omega_2}})$
$\psi(\Omega_3) = \psi(\psi_2(\Omega_3))$
$\psi(\Omega_3 + 1)$
$\psi(\Omega_3 + \omega)$
$\psi(\Omega_3 + \Omega)$
$\psi(\Omega_3 + \Omega_2)$
$\psi(\Omega_3 2)$
$\psi(\Omega_3 3)$
$\psi(\Omega_3 \omega)$

## 引入自然数多个非递归序数

我们可以进一步引入第四个非递归序数，然后再引入下一个，方法和之前相同。因此我们不妨引入自然数个非递归序数。

1. $C_0^0(x) = \{0, 1\} \cup \{\Omega_i | i<\omega\}$，$C_0^{i}(x) = C_0^0(x) \cap \Omega_i (i\ge 1)$
2. $C_{n+1}^i(x) = \{\alpha+\beta, \psi_m(\gamma) | \alpha,\beta,\gamma \in C_n^i(x), \gamma < x, m< \omega\}$
3. $C^i(x) = \bigcup_{n<\omega} C_{n+1}^i(x)$
4. $\psi_i(x) = \sup C^i(x) \cap \Omega_{i+1}$

### 枚举

$\psi(\Omega_3 \omega + 1)$
$\psi(\Omega_3 \omega + \Omega)$
$\psi(\Omega_3 \omega + \Omega_2)$
$\psi(\Omega_3 \omega + \Omega_3)$
$\psi(\Omega_3 \omega 2)$
$\psi(\Omega_3 \Omega)$
$\psi(\Omega_3^2)$
$\psi(\Omega_3^\omega)$
$\psi(\Omega_3^\Omega)$
$\psi(\Omega_3^{\Omega_3})$
$\psi(\Omega_3^{\Omega_3^{\Omega_3}})$
$\psi(\Omega_4)$
$\psi(\Omega_4 \omega)$
$\psi(\Omega_4^2)$
$\psi(\Omega_4^{\Omega_4})$
$\psi(\Omega_5)$
$\psi(\Omega_6)$

尽管我们并没有引入 $\Omega_\omega$，但是它是 $\Omega, \Omega_2, \Omega_3, \cdots$ 的上确界。这个序数便是BO。

$$
\text{BO} = \text{Buchholz Ordinal} = \psi(\Omega_\omega)
$$

## 引入序数多个非递归序数

我们或许可以在最开始的 $C(0)$ 中加入更多的 $\Omega$，但是没有这个必要：我们不如直接将 $x\mapsto \Omega_x$ 加入进去。我们使用 $R_2(S)$ 来表示 $S$ 之中的非递归序数构成的子集。

1. $C_0^{\Omega}(x) = \{0,1\}$, $C_0^{\Omega_{\alpha + 1}}(x) = \Omega_{\alpha} \cup \{\Omega_\alpha\}$
2. $C_{n+1}^\nu(x) = \{\alpha + \beta, \psi_\delta(\gamma), \Omega_\alpha | \alpha, \beta, \gamma \in C_n(x), \gamma < x, \delta \in R_2(C^\nu_n(x))\}$
3. $C^\nu(x) = \bigcup_{n<\omega} C_n^\nu(x)$
4. $\psi_\nu(x) = \sup C^\nu(x) \cap \nu$

这里我们就不使用自然数下标了：我们用 $\psi_\nu$ 表示将序数塌缩至 $\nu$ 之下的序数塌缩函数。$\nu$ 是一个非递归序数，$\psi_\nu(x) < \nu$。此前的 $\psi, \psi_1, \psi_2$ 分别是现在的 $\psi_\Omega, \psi_{\Omega_2}, \psi_{\Omega_3}$，当然，我们依然用 $\psi$ 指代 $\psi_\Omega$。

此外，下标必须是非递归序数。也就是说，$\psi_{\Omega_\omega}$ 并不存在。

计算规则也不难理解，$\Omega_{\alpha+1}$ 是用来折叠与 $\psi_{\Omega_{\alpha+1}}$ 相关的不动点的。

### 枚举

$\psi(0)$
$\psi(\Omega)$
$\psi(\Omega_2)$
$\psi(\Omega_3)$
$\psi(\Omega_\omega)$
$\psi(\Omega_\omega + 1)$
$\psi(\Omega_\omega + \psi(\Omega))$
$\psi(\Omega_\omega + \psi(\Omega_\omega))$
$\psi(\Omega_\omega + \psi(\Omega_\omega + \psi(\Omega)))$
$\psi(\Omega_\omega + \Omega)$
$\psi(\Omega_\omega + \Omega^\Omega)$
$\psi(\Omega_\omega + \psi_1(\Omega_2))$
$\psi(\Omega_\omega + \psi_1(\Omega_\omega))$
$\psi(\Omega_\omega + \psi_1(\Omega_\omega + \psi_1(\Omega_\omega)))$
$\psi(\Omega_\omega + \Omega_2)$
$\psi(\Omega_\omega + \Omega_3)$
$\psi(\Omega_\omega 2)$
$\psi(\Omega_\omega \omega)$
$\psi(\Omega_\omega \psi(\Omega_\omega))$
$\psi(\Omega_\omega \Omega)$
$\psi(\Omega_\omega \psi_1(\Omega_\omega))$
$\psi(\Omega_\omega \Omega_2)$
$\psi(\Omega_\omega \Omega_3)$
$\psi(\Omega_\omega^2)$
$\psi(\Omega_\omega^\Omega)$
$\psi(\Omega_\omega^{\Omega_\omega})$
$\psi(\Omega_\omega^{\Omega_\omega^{\Omega_\omega}})$

到达 TFBO，这个序数的结构相比 BO 复杂了很多。
$$ \psi(\Omega_{\omega+1}) = \psi(\psi_{\Omega_{\omega+1}}(\Omega_{\omega+1})) = \psi(\Omega_\omega^{\Omega_\omega^{\Omega_\omega^\cdots}}) = \text{Takeuti–Feferman–Buchholz ordinal} = \text{TFBO} $$

$\psi(\Omega_{\omega+1} + 1)$
$\psi(\Omega_{\omega+1} + \Omega)$
$\psi(\Omega_{\omega+1} + \Omega_\omega)$
$\psi(\Omega_{\omega+1} + \psi_{\Omega_{\omega+1}}(\Omega_{\omega+1}))$
$\psi(\Omega_{\omega+1} + \psi_{\Omega_{\omega+1}}(\Omega_{\omega+1} + \psi_{\Omega_{\omega+1}}(\Omega_{\omega+1})))$
$\psi(\Omega_{\omega+1}2)$
$\psi(\Omega_{\omega+1}^2)$
$\psi(\Omega_{\omega+1}^{\Omega_{\omega+1}})$
$\psi(\Omega_{\omega+2})$
$\psi(\Omega_{\omega2})$
$\psi(\Omega_{\omega^2})$
$\psi(\Omega_{\psi(\Omega)})$
$\psi(\Omega_{\psi(\Omega_2)})$
$\psi(\Omega_{\psi(\Omega_\omega)})$
$\psi(\Omega_{\psi(\Omega_{\psi(\Omega)})})$

同样的，$\Omega$ 折叠 $\psi$ 的不动点，我们到达了 Bird's Ordinal：

$$ \psi(\Omega_\Omega) = \text{BIO} = \text{Bird's Ordinal}$$

$\psi(\Omega_{\Omega+1})$
$\psi(\Omega_{\Omega2})$
$\psi(\Omega_{\Omega^\Omega})$
$\psi(\Omega_{\Omega^{\Omega^\Omega}})$
$\psi(\Omega_{\psi_{\Omega_2}(\Omega_2)})$
$\psi(\Omega_{\psi_{\Omega_2}(\Omega_\Omega)})$
$\psi(\Omega_{\psi_{\Omega_2}(\Omega_{\psi_{\Omega_2}(\Omega_2)})})$
$\psi(\Omega_{\psi_{\Omega_2}(\Omega_{\psi_{\Omega_2}(\Omega_{\psi_{\Omega_2}(\Omega_2)})})})$
$\psi(\Omega_{\Omega_2})$
$\psi(\Omega_{\psi_{\Omega_3}(\Omega_3)})$
$\psi(\Omega_{\Omega_4})$
$\psi(\Omega_{\Omega_\omega})$
$\psi(\Omega_{\Omega_{\omega+1}})$
$\psi(\Omega_{\Omega_{\psi(\Omega_{\Omega_\omega})}})$
$\psi(\Omega_{\Omega_{\psi(\Omega_{\Omega_{\psi(\Omega_{\Omega_\omega})}})}})$
$\psi(\Omega_{\Omega_\Omega})$
$\psi(\Omega_{\Omega_{\Omega_2}})$
$\psi(\Omega_{\Omega_{\Omega_\Omega}})$

最后，我们到达了有限次的 $\Omega_x$ 函数无法达到的地方，也就是第一个 $\Omega$ 不动点所塌缩达到的序数：

$$
\psi(\Omega_{\Omega_{\Omega_\cdots}}) = \text{EBO} = \text{Extended Buchholz Ordinal}
$$