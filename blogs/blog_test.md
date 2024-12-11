---
title: "Zhaofeng Peng - Blog"
layout: textlay
excerpt: "Zhaofeng Peng -- Blog"
sitemap: false
permalink: /blogtest/
---

# Blog Test

$$\frac{\partial L}{\partial x}-\frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L}{\partial \dot{x}}\right)$$

$$E = mc^2$$

## Equations

Advanced Dynamics:

**Euler Lagrange Equation** Therefore, it is good to reconstruct these equations.

<!--# [随笔]电动力学的创世纪

 **Author:** [Austeritas]

 **Link:** [https://zhuanlan.zhihu.com/p/640365597]

**1:1** 起初，神创造天地 $\mathbb R^{4}$ 和最小作用量原理 $\delta S=0$ 。

**1:2** 真空是空虚混沌。渊面黑暗。神的灵运行在量子涨落中。

**1:3** 神说，要有矢量场，就有了矢量场 $A^\mu=(\phi,\vec{A})$ .

**1:4** 神说，要有规范对称性，于是就有了规范对称性 $U(1)$ : $A^\mu \sim A^\mu+\partial^\mu\Lambda$ .

**1:5** 神说，要有规范不变量，于是就有了规范不变量 $F^{\mu \nu}=\partial^{\mu} A^{\nu}-\partial^{\nu} A^{\mu}$ .

**1:6** 神说，要有场源，于是就有了场源 $J^{\mu}=(\rho,\vec{J})$ .

**1:7** 神说，要有拉格朗日密度，于是就有了拉格朗日密度 ${\cal L}=-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} +J^{\mu} A_{\mu}$ .

**1:8** 神说，要有作用量，于是就有了作用量 $S=\int{\cal L}d^4x$ .

**1:9** 神说，要有运动方程，于是就有了运动方程 $\delta S=0\Rightarrow{\small \left\{ \begin{aligned} &\nabla \cdot \vec E =\frac{\rho}{\varepsilon_{0}}\\ &\nabla \cdot \vec B =0 \\ &\nabla \times \vec E =-\frac{\partial \vec B }{\partial t} \\ &\nabla \times \vec B =\mu_{0}\left(\vec J +\varepsilon_{0} \frac{\partial \vec E }{\partial t}\right) \end{aligned}\right.}$ .

**1:10** 神看这些方程是好的，于是称为麦克斯韦方程组。

**1:11** 称 $\small \vec E=-\nabla\phi-\partial_t\vec{A}$ 为电场强度，称 $\small  \vec B=\nabla\times \vec{A}$ 为磁感应强度。

**1:12** 神说：“要有光！”于是就有了光。



---

## 注释版  

> **·** 本文不涉及电磁场的量子化，所有的构造都在经典理论的意义下实现，只在补充内容提到一点量子场论。   
> **·** 本文使用高斯单位制： $\small \varepsilon_{0}={1}/{4 \pi},\ \mu_{0}=4 \pi,\ c=\sqrt{\small \varepsilon_{0}\mu_{0}}=1$ .   
> **·** 本文使用 $\rm Einstein$ 求和记号： $x^\mu x_\mu=x_\mu x^\mu \equiv \sum_{\mu}x^\mu x_\mu$ ， $\small \mu=0,1,2,3$ .   
> **·** 其中 $x^\mu$ 是逆变张量， $x_\mu$ 是协变张量， $x_\mu=g_{\mu\nu}x^\nu$ .

  


**1:1 起初，神创**造天地 $\mathbb R^{4}$和**最小作用量原理** $\delta S=0$ 。


> 这里 $\mathbb R^{4}$ 携带闵氏度规 $ds^2=-dt^2+dx^2+dy^2+dz^2$ ，也可记作 ${\mathbb R}^{1,3}$ ；   
> 经典世界服从最小作用量原理 $\delta S=0$ ； 真实世界服从量子规律，初态到末态的概率由概率幅给出： $\small \left\langle x_{b}, t_{b} \mid x_{a}, t_{a}\right\rangle=\!\!\!\!\!\!\!\!\!\!\!\!\sum_{\text {all possible paths} \text{ from }a\text{ to }b} \!\!\!\!\!\!\!\!\!\!\!\!\!\!\!{\rm e}^{i S(x)}\\$

**1:2 真空是空虚混沌。渊面黑暗。神的灵运行在量子涨落中。**

**1:3 神说，要有矢量场，就有了矢量场** $A^\mu=(\phi,\vec{A})$ .


> $A^\mu=(A_0,A_1,A_2,A_3)=(\phi,\vec{A}),\ {\small \mu=0,1,2,3}$ ；   
> 指标在右上角说明 $A^\mu$ 是一个逆变矢量场(直到一个规范变换)。“逆变矢量”是我们通常见到的矢量的变化规律：坐标轴正着转相当于矢量场反着转。

**1:4 神说，要有规范对称性，于是就有了规范对称性** $U(1)$ 


> 电磁场的 $\rm U(1)$ 规范对称性：$A^{\mu} \rightarrow A^{\mu}+\partial^{\mu} \Lambda$ 描述同一个场。  
>  其中 $\Lambda(x)={ 任意的光滑函数}$ ， $\partial^\mu=(\partial^0,\partial^1,\partial^2,\partial^3)$ .

**1:5 神说，要有规范不变量，于是就有了规范不变量 $F^{\mu \nu}=\partial^{\mu} A^{\nu}-\partial^{\nu} A^{\mu}$ : $F^{\mu \nu} \rightarrow F^{\mu \nu}$ 在规范变换下保持不变。**


> 在规范变换 $A^{\mu} \rightarrow A^{\prime \mu}=A^{\mu}+\partial^{\mu} \Lambda$ 下， $F^{\mu \nu} \rightarrow F^{\prime \mu \nu}=F^{\mu \nu}$ ，因此是规范不变的。 $F^{\mu \nu} =\partial^{\mu} A^{\nu}-\partial^{\nu} A^{\mu}$ 是最简单的规范不变量；实际上你可能会问选择这一规范不变量是否有什么特殊性，这在某种意义上是最小耦合(minimal coupling)的要求；也就是说，当我们试图构造一个规范变换下的协变导数 $\partial^\mu\to D^\mu$ 的时候，我们希望 $D^\mu$ 采取最简单的形式，也就是 $D_{\mu}= i \partial_{\mu}+A_{\mu}$ .   
> 现在我们已知了一个规范不变的二阶张量 $F^{\mu \nu} $ （二阶张量可以理解为一个矩阵）， 问题是：如何构造理论的拉格朗日密度？   
> 拉格朗日密度 ${\cal L}$ 是一个标量，而且是规范不变的； 从张量 $F^{\mu \nu} $ 生成一个标量，最简单的方法是逆变张量和协变张量缩并 $F^{\mu \nu} F_{\mu \nu} $ ，也就是对应求和；  
> 其中 $F_{\mu \nu} =g_{\mu\alpha}g_{\nu\beta}F^{\alpha \beta}$ ，度规张量 $g_{\mu\nu}={\rm diag(+,-,-,-)}= {\small \left(\begin{array}{rrrr} 1 & 0 & 0 & 0 \\ 0 & -1 & 0 & 0 \\ 0 & 0 & -1 & 0 \\ 0 & 0 & 0 & -1 \end{array}\right)}$ .   
>   
> 自由电磁场（即不含源）的拉格朗日密度 ${\cal L}=-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} \\$ 负号是约定俗成让 $\delta S=0$ 成为“最小作用量原理”，而不是最大作用量原理。  
> PS：你可能会注意到实际上 $F^{\mu\nu}F_{\mu\nu}=-2\left(E^2-{B^2}\right)$（Heaviside 单位制），因而是对称的；那么为什么电磁张量 $F^{\mu\nu}$ 不能以反对称的方式缩并，即 $\epsilon_{ijkl} F^{ij} F^{kl}=-8(\vec{B} \cdot \vec{E})$ ，从而让反对称项进入到拉格朗日密度 $\cal L$ 当中？  
> 这一点在Landau《场论》中得到了详细解释，具体原因有三个：① ·实验告诉我们自由电磁波的电场和磁场是垂直的，即 $\vec B \cdot \vec E=0$ ；② $\vec B \cdot \vec E$ 项是赝标量，即在时间反演下符号翻转，但是拉格朗日密度必须是真标量，即电磁学规律的时间反演对称性；③ $\epsilon_{ijkl} F^{ij} F^{kl}$ 实际上是一个全散度项因此积分之后成为常数 $C$ ，从而在对作用量变分 $\delta S$ 时可以忽略。

**1:6 神说要有场源，于是就有了场源** $J^{\mu}=(\rho,\vec{J})$ .


> 场源 $J^\mu$ 在洛伦兹变换下按照矢量表示变换，下面将指出可以通过狄拉克费米子构造 $J^\mu=\psi\gamma^\mu\psi$ 。

**1:7 神说，要有拉格朗日密度，于是就有了拉格朗日密度** ${\cal L}=-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} +J^{\mu} A_{\mu}$ .


> 拉格朗日密度中场源和场的耦合都是采取 $qV$ 的形式（想想引力势 $-m\frac{GM}{r}{}$ 中的力荷 $m$ 和位势 $-\frac{GM}{r}$ ），因此场源 $J^{\mu} $ 会以 $J^{\mu} A_{\mu}$ 的形式出现在拉格朗日量当中；实际上这符合最小耦合(minimal coupling)的精神。  
> 因此，为了获得一个含源的拉格朗日密度，只需要加上一项 $J^{\mu} A_{\mu}$ ，即 ${\cal L}=-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} +J^{\mu} A_{\mu}\\$ 这里有一个稍微微妙的一点：自由电磁场的作用量 ${\cal L}=-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} $ 显然满足：  
> ① 整体 $U(1)$ 对称性 ${A^{\mu}}^{\prime}=A^{\mu}+a^{\mu}$   
> ② 定域$U(1)$ 对称性 ${A^{\mu}}^{\prime}=A^{\mu}+\partial^{\mu} a(x)$   
> 而含源的拉格朗日密度 ${\cal L}=-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} +J^{\mu} A_{\mu}$ 中的 $J^{\mu} A_{\mu}$ 在定域规范不变性下显然是变化的： $J_{\mu} A^{\mu}\to J_{\mu} A^{\mu}+ \color{red}{\partial^{\mu} a(x)}\color{blue}{J_{\mu}}\\$ .那怎么办？场源 $J^{\mu} $ 不应当在规范变换下变化（规范变换没有物理效应），因此为了保持定域的$U(1)$ 对称性，拉氏量必须添加一项 $\phi$ ，它在关于 $a(x)$ 的规范变换下按照 $\phi- \color{red}{\partial^{\mu} a(x)}\color{blue}{J_{\mu}}$ 的方式变换。   
> 现在我们知道了两点： 1、这个 $\phi$ 和场源 $ J^μ $ 有某些关系； 2、我们需要找出这个额外的场 $\phi$ 并把它的运动学项加入电磁场的拉格朗日量当中从而保持理论的定域规范不变性。  
>  而我们恰好知道，狄拉克方程 $\left(i \gamma_{\mu} \partial^{\mu}-m\right) \Psi=0$ 描述的自旋 $1/2$ 自由粒子的拉氏量 ${\cal L} _{\text {Dirac }}=-m \bar{\Psi} \Psi+i \bar{\Psi} \gamma^{\mu} \partial_{\mu} \Psi\\$在规范变换 $\Psi\to \mathrm{e}^{ia(x)}\Psi$ 下有：$-m \bar{\Psi} \Psi\to-m \bar{\Psi} \Psi$ ，以及 $i \bar{\Psi} \gamma^{\mu} \partial_{\mu} \Psi\to i \bar{\Psi} \gamma^{\mu} \partial_{\mu} \Psi-\color{red}{\left(\partial^{\mu} a(x)\right) }\color{blue}{\bar{\Psi} \gamma_{\mu} \Psi}\\$ 这恰好是我们需要的变换， 这非常好！  
> 也就是说，假如我们的场源恰好是 $J_\mu=\bar{\Psi} \gamma_{\mu} \Psi$ ，那么我们只需要把刚才的电磁场的拉氏量和自由狄拉克场的拉氏量加起来： ${\cal L} _{\text {Total}}={\cal L} _{\text {Dirac}}+{\cal L} _{\text {EM}}=-m \bar{\Psi} \Psi+i \bar{\Psi} \gamma^{\mu} \partial_{\mu} \Psi-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} +\bar{\Psi} \gamma_{\mu} \Psi A^{\mu}\\$（严格来说还应该有一个耦合强度参数 $g$ ，使得耦合项形为 $g\bar{\Psi} \gamma_{\mu} \Psi A^{\mu}$ ，这里就为了简洁而归一化了。）   
> 可以看到，电磁场和狄拉克场是通过 $\bar{\Psi} \gamma_{\mu} \Psi A^{\mu}$ 的方式耦合起来的，其中 $\bar{\Psi} \gamma_{\mu} \Psi$ 充当了电磁场的场源；这一耦合方式保持了整体的拉氏量的 $\rm U(1)$ 规范不变性，因此被称为规范耦合(gauge coupling)。   
> 那么我们的场源是否确实是 $\bar{\Psi} \gamma_{\mu} \Psi$ 的形式呢？确实是的。（笑）  
> 说实话，我们是先有一个自旋 $1/2$ 的狄拉克场然后才有的一个具有 $U(1)$ 对称性的经典电磁场。 这一点可以从标准模型 $\rm SU(3)\times SU(2)\times U(1)$ 推出来，这里就先不展开了。  
>   
> 顺便一提，可以看到在偏微分算子 $\partial^\mu$ 作用下，在规范变换 $\Psi\to \mathrm{e}^{ia(x)}\Psi$ 前后每一项的形式是明显变换的，只是总体恰好抵消了而已；为了消除这种变化，使得在规范变换前后的每一项是显明不变的，我们会引入协变导数： $\partial_{\mu} \rightarrow D_{\mu}= i \partial_{\mu}+A_{\mu}\\$ 在这一替换下，原拉氏量写为 ${\cal L} _{\text {Total}}=-m \bar{\Psi} \Psi+i \bar{\Psi} \gamma^{\mu} D_{\mu} \Psi-\frac{1}{16 \pi} F_{\mu \nu} F^{\mu \nu} \\$ 现在每一项在规范前后都是不变的辽. : -)   
> 这里的从协变导数替换普通导数实际上遵循了最小替换的精神，即用协变导数替代普通导数，以及协变导数取最简单的形式。  
> 如果我们进一步考察“偏导数算子”的物理含义，我们会注意到偏导数实际上就是在时空的各个方向上的“梯度”或者说“转移”；于是我们注意到，电磁场实际上起到的作用是“告诉狄拉克场在各个方向上如何平移”，也就是两点之间的物理量是如何联系在一起的。这也正是电磁场作为规范场(gauge field)的含义。  
> 更详细的阐述可以看这一回答：

[规范场论中的“规范”是什么意思？](https://www.zhihu.com/question/27503026/answer/2138046384)
> 在一般的情形中，我们实际上默认了在时空各处要采取相同的规范。但这并非被什么对称性要求的，而只是一个特例。 我们现在试图考虑一个通用（general）的理论，在这个理论中我们允许在时空各处采用不一样的规范。这不会给质量项带来问题，但动能项则不然。由于动能项涉及到物质场在不同时空位置处的比较，在没有统一规范的情况下，这一项甚至没有良好定义。**规范场（gauge field）**就是为解决这一问题引入的。 所谓的规范场，就是描述规范作为时空位置函数的分布。我们首先定义一个**平行移动子（parallel transporter）**，用来描述物质场如何从一点 $x$ 移动（transport）到另一点 $y$ 。换句话说，它告诉我们这两点的规范是如何联系在一起的。举个经典的例子，这移动子其实就对应着两套参考系之间的变换矩阵。

  


**1:8 神说，要有作用量，于是就有了作用量** $S=\int{\cal L}d^4x$ **.**


> 拉格朗日密度的系数 $-\frac{\rm 1}{16\pi}$ 有时会随单位制的不同而不同，在 $\text{Lorentz-Heaviside}$ 单位制中取 $-\frac{1}{4}$ ，在国际单位制中取 $-\frac{1}{4 \mu_{0}}$ .

**1:9 神说，要有演化方程，于是就有了演化方程** $\delta S=0\Rightarrow{\small \left\{ \begin{aligned} &\nabla \cdot \vec E =\frac{\rho}{\varepsilon_{0}}\\ &\nabla \cdot \vec B =0 \\ &\nabla \times \vec E =-\frac{\partial \vec B }{\partial t} \\ &\nabla \times \vec B =\mu_{0}\left(\vec J +\varepsilon_{0} \frac{\partial\vec E }{\partial t}\right) \end{aligned}\right.}$ **.**


> 真空的麦克斯韦方程： $\delta S=0\Rightarrow{\small \left\{ \begin{aligned} &\nabla \cdot \vec E =0 \\ &\nabla \cdot \vec B =0 \\ &\nabla \times \vec E =-\frac{\partial \vec B }{\partial t} \\ &\nabla \times \vec B =\mu_{0}\varepsilon_{0} \frac{\partial \vec E }{\partial t} \end{aligned}\right.}$ 值得一提的是，为了强调 $\small \varepsilon_{0},\ \mu_{0}$ 的位置，使用了国际单位制中的麦克斯韦方程的形式。

**1:10 神看方程是好的，于是称为麦克斯韦方程组。**


> 需要指出的是，麦克斯韦当年提出的麦克斯韦方程组在这四条外，既包括欧姆定律，也包括连续性方程（后者可以从麦克斯韦方程中推出）参见：

[麦克斯韦方程组最初的那20个方程是什么？](https://www.zhihu.com/question/432697495/answer/1606681681)**1:11 神称** $\small \vec E=-\nabla \phi-\partial_t \vec{A}$ **为电场强度，称** $\small  \vec B=\nabla\times \vec{A}$ **为磁感应强度。**


> 其实是历史约定。（人民群众是历史的创造者）   
> 比如 $\vec B$ 为什么不叫磁场强度？因为已经用来命名 $\vec H$ 了。

**1:12 神说：“要有光！”于是就有了光。**



---

-->