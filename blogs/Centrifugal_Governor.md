---
title: "Zhaofeng Peng - Blog"
layout: textlay
excerpt: "Zhaofeng Peng -- Blog"
sitemap: false
permalink: /blog/centrifugal_governor/
---

<script type="text/javascript">
    window.MathJax = {
        tex: {
            inlineMath: [['$', '$'], ['\\(', '\\)']],
            processEscapes: true,
            packages: {'[+]': ['base', 'ams', 'braket', 'newcommand', 'mhchem', 'physics', 'noerrors']}
        },
        options: {
            skipHtmlTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            processHtmlClass: 'mathjax'
        }
    };
</script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.1/es5/tex-chtml.js" type="text/javascript"></script>

# 离心调速器——从物理建模到微分方程平衡解的稳定性分析

 **Author:** Quaternion

 **Link:** For Chinese version, click [here](https://zhuanlan.zhihu.com/p/673357410)

## 前言  
笔者这学期选修了常微分方程，最近（2023年12月19日）学习到了有关李雅普诺夫稳定性的相关内容。在浏览庞特里亚金的《常微分方程》时，我恰巧看到其中有一节内容与离心调速器的稳定性分析有关，思绪一下就被拉回到初二时躺在床上打着手电读《三体》的快乐时光，云天明的三个故事给当时的我带来了莫大的震撼。于是，我决定参照庞特里亚金书中的内容，写一写关于离心调速器的事。

受限于文章篇幅，这篇文章无法做到面面俱到。因此，我们需要读者已经有一定的前置知识，其中包括（但不限于）了解常系数线性微分方程以及方程组的解法等。

我们先从物理建模开始。

## 模型  
我们首先来看一看离心调速器（Centrifugal governor）的定义。维基百科（Wikipedia）上给出了如下的定义：


> A **centrifugal governor** is a specific type of governor with a feedback system that controls the speed of an engine by regulating the flow of fuel or working fluid, so as to maintain a near-constant speed. It uses the principle of proportional control.  
> 离心调速器是一种具有反馈系统的特定类型的调速器，其通过调控燃料或工作流体的流量来控制引擎的速度，以达到保持接近恒定速度的目的。它用到了比例控制的原理。

其示意图为（图片来自维基百科）

![]((20240501)离心调速器从物理建模到微分方程平衡解的稳定性分析_Quaternion/v2-e8f3b205e9d97711f5ee2ef4f0ef658c_1440w.jpg)  


离心式“飞球”调速器的示意图；随着速度的增加，球体向外摆动，从而关闭阀门，直至速度降低到所需的恒定值

  
  
总而言之，离心调速器是一种借助于离心运动的自动控制系统。

1868年，麦克斯韦（James Clerk Maxwell）写了一篇著名的论文《论调速器》（*On Governors*），这篇论文被广泛认为是反馈控制理论中的经典。1876年，伊万·维什涅格拉德斯基（Ива́н Алексе́евич Вышнегра́дский）独立地分析了蒸汽机系统中的离心调速器，为工程提供了重要的指导。接下来，我们将把目光聚焦于维什涅格拉德斯基的研究成果上。

按照庞特里亚金书中所述，我们将离心调速器简化为如下的模型：

![]((20240501)离心调速器从物理建模到微分方程平衡解的稳定性分析_Quaternion/v2-407351d37d73251bca706ce8625ae320_1440w.jpg)  


图片摘自该书的英文版

  
  
图中 $S$ 是一根可以绕自己垂直轴心旋转的垂直枢轴，其上端通过铰链与两根同样长度的杆 $L_1$ 和 $L_2$ 相连，杆 $L_1$ 和 $L_2$ 的下端各带有质量为 $m$ 的相同重球。杆 $L_1$ 和 $L_2$ 又与辅助杆通过铰链相连，从而可以带动套在枢轴 $S$ 上的特制套管 $M$ 。设各杆与枢轴 $S$ 之间的夹角均为 $\varphi$ ，杆 $L_1$ 和 $L_2$ 的长度为单位长度。当枢轴 $S$ 以角速度 $\theta$ 旋转时，（在以枢轴为参照物的旋转系中）重球将受到离心力、重力和杆对它的作用力。如果重球在该参考系中保持静止，则上述三个力的合力为零。根据上述假设，作用在重球上的离心力大小为 $m\theta^2\sin\varphi$ ，重力大小为 $mg$ 。这两个力可以按垂直于杆轴线和沿杆轴线的方向分解，如下图所示：

![]((20240501)离心调速器从物理建模到微分方程平衡解的稳定性分析_Quaternion/v2-a0cfe8255957748386daaf4ee106a6e9_1440w.jpg)  


图片摘自该书的英文版

  
  
当枢轴 $S$ 的转速保持恒定时，（在没有扰动的情况下）重球能够相对于枢轴 $S$ 保持静止，此时离心力与重力沿杆轴线方向的分量和杆对重球的作用力相平衡；其垂直于杆轴线方向的分量之和为零，即 $$m\theta^2\sin\varphi\cos\varphi-mg\sin\varphi=0\tag{1}\\$$  
实际上我们知道，重球会随枢轴 $S$ 的转动角速度增加而向外摆动（可以类比拨浪鼓）。在这一过程中，我们还需要考虑铰链的摩擦力。书中提到：“它（摩擦力）以十分复杂的形式依赖于所发生的运动。为了在本质上简化这里存在的复杂性，我们假设摩擦力与质量 $m$ （即重球）的运动速度 $\dot{\varphi}$ 成正比，且有与这个速度相反的符号，即有量 $-b\dot{\varphi}$ ，其中 $b$ 为常数。”根据牛顿第二定律，我们可以得到一个关于 $\varphi$ 的微分方程 $$m\ddot{\varphi}=m\theta^2\sin\varphi\cos\varphi-mg\sin\varphi-b\dot{\varphi}\tag{2}$$  
（注意：当 $\theta$ 和 $\varphi$ 变动时产生的附加的力与杆及铰链的反作用力平衡。）

在离心调速器的示意图中，我们可以注意到一个以角速度 $\omega$ 旋转的飞轮。飞轮受到蒸汽的驱动而旋转，并且能输出有用功，例如提升重物。设飞轮的惯性矩为 $J$ ，根据角动量定理可得 $$J\dot{\omega}=P_1-P\tag{3}$$  
其中 $P_1$ 是蒸汽的作用力矩， $P$ 是重物的重量作用在飞轮上的力矩。飞轮与调速器的枢轴 $S$ 通过传动齿相互联系，因此当飞轮转速过快时蒸汽的输入量就会减小，飞轮转速过慢时蒸汽的输入量就会增大。传动齿将飞轮转动的角速度 $\omega$ 和枢轴 $S$ 转动的角速度 $\theta$ 通过 $$\theta=n\omega\tag{4}$$  
关联了起来，其中 $n$ 为一常量，称为转换数。

最后，我们还需要将以上式子中的 $\varphi$ 和 $(3)$ 右侧的 $P_1-P$ 联系起来，以便得到刻画该模型的微分方程组。我们知道，离心调速器的作用是保持飞轮的转速基本恒定，由 $(1)$ 和 $(4)$ 能够看出 $\varphi$ 也应该保持基本恒定。设 $\varphi$ 的值在 $\varphi^{\ast}$ 附近变化（即 $\varphi^{\ast}$ 是 $\varphi$ 的“平均值”）。当飞轮转速加快时， $\varphi$ 值增大，套管 $M$ 向上移动，并通过杠杆带动气门（供给蒸汽的闸门）关闭，蒸汽的作用力矩 $P_1$ 减小；当飞轮转速减慢时， $\varphi$ 值减小，套管 $M$ 向下移动，并通过杠杆带动气门打开，蒸汽的作用力矩 $P_1$ 增大。因此，我们假定 $$P_1=F_1+k(\cos\varphi-\cos\varphi^{\ast})\tag{5}$$  
其中 $F_1$ 是当 $\varphi=\varphi^{\ast}$ 时 $P_1$ 的值， $k>0$ 是比例常数。（可以看出， $(\cos\varphi-\cos\varphi^{\ast})$ 这一项其实正比于套管 $M$ 上下移动的距离。）

结合关系式 $(2)-(5)$ ，描述该系统的微分方程组为 $$\left\{ \begin{array}{l} m\ddot{\varphi}=mn^2\omega^2\sin\varphi\cos\varphi-mg\sin\varphi-b\dot{\varphi}\\ J\dot{\omega}=k\cos\varphi-F \end{array}\right.\tag{6}$$  
其中 $F=P-F_1+k\cos\varphi^{\ast}$ 是一与负载有关的量。至此，我们建立起了所需研究的物理模型及其对应的微分方程。

以上内容（物理建模部分）基本来自庞特里亚金的《常微分方程》（第6版；林武忠，倪明康译；高等教育出版社；2006）第五章§27。

接下来，我们简要介绍一下解的稳定性的定义和一些解稳定性的判定条件。对这些内容比较熟悉的读者可以略去这部分，直接阅读文章的最后一节：方程平衡解的稳定性分析。

## 解的稳定性的定义  
在进行下一步之前，我们首先介绍一下李雅普诺夫稳定性的概念。考虑一个自治的非线性动力系统： $$\dot{x}=f(x(t)),\qquad x(0)=x_0\tag{7}$$  
其中 $x(t)\in\mathcal{D}\subseteq\mathbb{R}^n$ 表示系统的状态矢量， $\mathcal{D}$ 是一个包含原点的开集， $f:\mathcal{D}\rightarrow\mathbb{R}^n$ 是 $\mathcal{D}$ 上的连续向量场。假设 $f$ 在 $x_e$ 存在一个平衡使得 $f(x_e)=0$ （即 $x=x_e$ 是 $\dot{x}=f(x)$ 的一个解），那么

1. 该平衡是李雅普诺夫稳定的，如果对任意 $\varepsilon>0$ ，都存在一个 $\delta>0$ ，使得只要 $\|x(0)-x_e\|<\delta$ 时，对所有 $t\ge0$ 都有 $\|x(t)-x_e\|<\varepsilon$ ；
2. 该平衡是渐近稳定的，如果它是李雅普诺夫稳定的，且存在 $\delta_0>0$ ，使得只要 $\|x(0)-x_e\|<\delta_0$ 时，有 $\displaystyle\lim_{t\to\infty}\|x(t)-x_e\|=0$ ；
3. 该平衡是全局渐近稳定的，如果 $\mathcal{D}=\mathbb{R}^n$ ，且在渐近稳定的定义中 $\delta_0$ 可取 $+\infty$ 。

以上内容基本翻译自维基百科（Wikipedia）的李雅普诺夫稳定性（Lyapunov stability）词条。

为了更加直观地解释李雅普诺夫稳定性的概念，我们在此处给出三幅示意图：

![]((20240501)离心调速器从物理建模到微分方程平衡解的稳定性分析_Quaternion/v2-7167bda2b8ea9e792f39d83d865b0cd2_1440w.jpg)  


李雅普诺夫意义下的稳定性、渐近稳定性和不稳定性的示意图

  
  
图中的蓝线表示以 $x(0)=x_0$ 为初始值的解 $x(t)$ 。这三幅图从左至右依次表示平衡解 $x=x_e$ 在李雅普诺夫意义下的稳定、渐近稳定与不稳定。从直觉上理解，对处于平衡的系统加一小扰动，如果该系统的状态能一直维持在该平衡的附近，则该平衡是李雅普诺夫稳定的；如果系统的状态不仅能维持在该平衡附近，还能最终收敛到该平衡，则该平衡渐近稳定。

## 常系数齐次线性方程的稳定性  
常系数齐次线性方程是一类常见的线性动力系统，其具有如下形式： $$\frac{\mathrm{d}x}{\mathrm{d}t}=Ax\tag{8}$$  
即 $\dot{x}=Ax$ ；其中 $x=x(t)$ 是 $n$ 维列向量， $A$ 是 $n\times n$ 常矩阵。容易得知， $x=0$ （零解）是该系统的平衡解。对于该零解是否稳定，我们有以下判定定理：

1. 零解是渐近稳定（实际上是全局渐近稳定）的，当且仅当 $A$ 的全部特征根都有负的实部；
2. 零解是稳定的，当且仅当 $A$ 的全部特征根的实部是非正的，并且那些实部为零的特征根对应的若尔当小块都是一阶的；
3. 零解是不稳定的，当且仅当 $A$ 的特征根中至少有一个实部为正，或者至少有一个实部为零，而它所对应的若尔当小块是高于一阶的。

受限于篇幅，此处我们仅简要给出上述第1条判定定理的证明。


> **证明：**方程 $\dot{x}=Ax$ 的基本解矩阵为 $e^{At}$ ，则当初始值为 $x(0)=x_0$ 时，对应的解为 $x(t)=e^{At}x_0$ 。  
> 设 $\displaystyle\max_i\left\{\mathfrak{Re}\left[\lambda_i(A)\right]\right\}=-\alpha_0$ ，其中 $\alpha_0>0$ 。选取 $0<\alpha<\alpha_0$ ，则 $\lambda_i(A)=\alpha_i+j\beta_i=-\alpha-\tilde{\alpha}_i+j\beta_i$ ，其中 $\alpha_i<0$ ， $\tilde{\alpha}_i>0$ 且满足 $\alpha_i=-(\alpha+\tilde{\alpha}_i)$ 。  
> 根据常系数齐次线性方程解的特点，可知基本解矩阵中每个元素的形式都为 $e^{\lambda_it}Q_i(t)$ ，其中 $Q_i(t)$ 为多项式。代入 $\lambda_i$ ，可得 $e^{\lambda_i}Q_i(t)=e^{-\alpha t}\cdot e^{(-\tilde{\alpha}_i+j\beta_i)t}Q_i(t)$ ，而 $e^{(-\tilde{\alpha}_i+j\beta_i)t}Q_i(t)$ 是有界的。  
> 由此可以证明，存在 $K>0$ 和 $\alpha>0$ ，当 $t\ge 0$ 时有 $\|e^{At}\|\le Ke^{-\alpha t}$ ，进而有 $\|x(t)\|\le\mathscr{K}e^{-\alpha t}$ （其中 $\mathscr{K}>0$ ）。综上，零解是渐近稳定的。

对于上述三条判定定理的具体证明方法感兴趣的读者，可以参考常微分方程教材中的相关内容。从这些定理可以看出，判定常系数齐次线性方程的零解是否稳定可以转换为求解相应的特征值的问题。

人们常用赫尔维茨（Hurwitz）定理来判断矩阵特征根的实部是否均为负值，进而判定对应微分方程的零解是否渐近稳定。其具体内容如下：

* 设 $Q(\lambda)=\lambda^n+a_1\lambda^{n-1}+\cdots+a_{n-1}\lambda+a_n$ 是一实系数多项式。记 $D_1=a_1$ ，和 $D_k=\det \begin{bmatrix} a_1 & a_3 & a_5 & \cdots & a_{2k-1} \\ 1 & a_2 & a_4 & \cdots & a_{2k-2} \\ 0 & a_1 & a_3 & \cdots & a_{2k-3} \\ 0 & 1 & a_2 & \cdots & a_{2k-4} \\ \vdots & \vdots & \vdots & &\vdots \\ 0 & 0 & 0 & \cdots & a_k\\ \end{bmatrix},\ (k=2,\cdots,n)$ ，其中 $a_i=0,\ i>n$ 。那么， $Q(\lambda)=0$ 所有根的实部均是负的，当且仅当 $D_k>0,\ k=1,\cdots,n$ ，并且 $a_i>0,\ i=1,\cdots,n$ 。

在后续内容中，我们会用该定理来计算离心调速器对应微分方程组平衡解稳定的条件。

## 非线性方程的稳定性：线性化方法  
对于一般的非线性动力系统 $$\frac{\mathrm{d}x}{\mathrm{d}t}=f(t,x)\tag{9}$$  
记满足初始条件 $x(\tau)=\xi_0$ 的解为 $x(t)=\phi(t,\tau,\xi_0)$ 。通过变换 $x=y+\phi(t,\tau,\xi_0)$ ，方程组 $(9)$ 即可转变为 $$\frac{\mathrm{d}y}{\mathrm{d}t}=f(t,y+\phi(t,\tau,\xi_0))-f(t,\phi(t,\tau,\xi_0))\tag{10}$$  
可以看出， $y=0$ 是方程组 $(10)$ 的平衡解，即方程组 $(9)$ 的解 $\phi(t,\tau,\xi_0)$ 和方程组 $(10)$ 的零解等价。因此，我们不妨假设方程组 $(9)$ 有零解 $x=0$ ，而且在适当的可微性假设下，其可以改写为 $$\frac{\mathrm{d}x}{\mathrm{d}t}=A(t)x+R(t,x)\tag{11}$$  
其中 $R(t,x)$ 是 $f(t,x)$ 关于 $x$ 的展开式中所有高于一次的项的总和。假设 $A(t)$ 是常矩阵 $A$ ， $R(t,x)$ 满足一定的连续性条件，并对 $x$ 满足局部李氏（Lipschitz）条件。 $R(t,x)$ 还满足 $R(t,0)=0$ ，且对 $t>\tau$ 一致地有 $\displaystyle\lim_{|x|\to0}\frac{R(t,x)}{|x|}=0$ 。那么，方程组 $(11)$ 的零解的稳定性在一定程度上可以由其第一近似 $\dot{x}=Ax$ 来决定。我们有以下判定定理（请注意，我们在此处假设了 $A(t)$ 是常矩阵 $A$ ）：

1. 若 $A$ 的全部特征根都有负的实部，则方程组 $(11)$ 的零解是渐近稳定的；
2. 若 $A$ 的特征根中至少有一个具有正的实部，则方程组 $(11)$ 的零解是不稳定的。

以上定理的证明请参考常微分方程教材中的对应内容。人们常用雅可比矩阵（Jacobian）对方程进行线性化，即 $$\dot{x}=\mathrm{J}x,\qquad \mathrm{J}=\left.\frac{\partial f}{\partial x}\right|_{x=x_e}\tag{12}$$  
其中 $\mathrm{J}$ 即为在平衡点 $x=x_e$ （即满足 $f(x_e)=0$ ）处的雅可比矩阵。如果该雅可比矩阵的特征值的实部都严格小于零，那么该平衡解 $x=x_e$ 是渐近稳定的。同样地，我们可以用赫尔维茨定理来帮助判断平衡解是否渐近稳定。

以上内容（线性化方法部分）基本来自伍卓群，李勇编写的《常微分方程》（第1版；高等教育出版社；2004）第五章1.2节。

## 方程平衡解的稳定性分析  
我们之前已经得到了所需研究的微分方程组 $(6)$ ，但是其中的第一个方程是二阶的，因此我们引入 $\psi=\dot{\varphi}$ ，从而可以将 $(6)$ 转化为标准形式： $$\left\{ \begin{array}{l} \dot{\varphi}=\psi\\ \dot{\psi}=n^2\omega^2\sin\varphi\cos\varphi-g\sin\varphi-\dfrac{b}{m}\psi\\ \dot{\omega}=\dfrac{k}{J}\cos\varphi-\dfrac{F}{J} \end{array}\right.\tag{13}$$  
令方程组 $(13)$ 的右端等于零，得到该方程组的平衡位置 $\varphi=\varphi_0,\ \psi=\psi_0,\ \omega=\omega_0$ 满足 $$\left\{  \begin{array}{l}  \psi_0=0\\ \cos\varphi_0=\dfrac{F}{k}\\ n^2\omega_0^2=\dfrac{g}{\cos\varphi_0} \end{array}\right.\tag{14}$$  
这样的平衡表示当负载不变（即 $F$ 是常数）时，飞轮的旋转角速度 $\omega$ 保持恒定（ $\omega=\omega_0$ ），供应蒸汽的闸门是不动的，角度 $\varphi$ 也保持不变（ $\varphi=\varphi_0$ ）。为了研究该平衡的稳定性，我们用雅可比矩阵对方程组 $(13)$ 进行线性化，得到 $$\frac{\mathrm{d}}{\mathrm{d}t} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix}= \left.\begin{bmatrix} 0 & 1 & 0 \\ n^2\omega^2\cos2\varphi-g\cos\varphi & -\frac{b}{m} & n^2\omega\sin2\varphi \\ -\frac{k}{J}\sin\varphi & 0 & 0\\ \end{bmatrix} \right|_{\varphi=\varphi_0,\,\psi=\psi_0,\,\omega=\omega_0} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix} \tag{15}$$  
简单化简后，得到 $$\frac{\mathrm{d}}{\mathrm{d}t} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix}= \begin{bmatrix} 0 & 1 & 0 \\ -\frac{g\sin^2\varphi_0}{\cos\varphi_0} & -\frac{b}{m} & \frac{2g\sin\varphi_0}{\omega_0} \\ -\frac{k\sin\varphi_0}{J} & 0 & 0\\ \end{bmatrix} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix} \tag{16}$$  
根据之前给出的判定定理，我们需要通过该方程组系数矩阵的特征根实部的正负来判定平衡的稳定性。由此，方程组 $(16)$ 的特征多项式为 $$Q(\lambda)= \begin{vmatrix} \lambda & -1 & 0 \\ \frac{g\sin^2\varphi_0}{\cos\varphi_0}  & \lambda+\frac{b}{m} & -\frac{2g\sin\varphi_0}{\omega_0} \\ \frac{k\sin\varphi_0}{J} & 0 & \lambda \end{vmatrix} \tag{17}$$  
即特征方程 $Q(\lambda)=0$ 为 $$\lambda^3+\frac{b}{m}\lambda^2+\frac{g\sin^2\varphi_0}{\cos\varphi_0}\lambda+\frac{2kg\sin^2\varphi_0}{J\omega_0}=0\tag{18}$$  
该方程的所有系数都是正的，我们可以根据赫尔维茨定理给出其稳定性的充分必要条件。简单计算后可得：平衡位置稳定，当且仅当 $$\frac{bJ}{m}>\frac{2k\cos\varphi_0}{\omega_0}=\frac{2F}{\omega_0}\tag{19}$$  
由此，我们得到了机器-调节器系统的稳定性充分条件，即关系式 $(19)$ 。

为了说明不等式 $(19)$ 右端的意义，我们引入在工程上起重要作用的蒸汽机运行不均衡性（nonuniformity of performance）的概念。根据 $(14)$ ，当关于负载的量 $F=P-F_1+k\cos\varphi^{\ast}$ 发生变化（即当负载 $P$ 变化）时，平衡时的稳定速度 $\omega_0$ 也会发生变化。那么， $\displaystyle\frac{\mathrm{d}\omega_0}{\mathrm{d}P}$ 描述了当负载 $P$ 变化时 $\omega_0$ 的变化率，其绝对值 $\displaystyle\nu=\left|\frac{\mathrm{d}\omega_0}{\mathrm{d}P}\right|$ （正如我们将要看到的那样，导数 $\displaystyle\frac{\mathrm{d}\omega_0}{\mathrm{d}P}$ 是负的）称为蒸汽机的运行不均衡性。根据平衡条件 $(14)$ ，可得 $F\omega_0^2=\text{const.}$ ，因此求导即得 $\displaystyle\frac{\mathrm{d}\omega_0}{\mathrm{d}F}=-\frac{\omega_0}{2F}$ 。于是， $\displaystyle\nu=\frac{\omega_0}{2F}$ ，而稳定性条件 $(19)$ 最终可以写为 $$\frac{bJ}{m}\cdot\nu>1\tag{20}\\$$  
维什涅格拉德斯基根据公式 $(20)$ 曾作出以下推论：

1. 增加重球的质量 $m$ 有害于稳定性；
2. 减小摩擦系数 $b$ 有害于稳定性；
3. 减小飞轮的惯性矩 $J$ 有害于稳定性；
4. 减小运行的不均衡性 $\nu$ 有害于稳定性。

在19世纪中叶，由于离心调速器的部分设计发生了改变，导致其变得不可靠。具体而言，由于工程技术的发展，出现在不等式 $(20)$ 中的四个量都向着破坏稳定性的方向变化。由于气门重量的提升（它与机器功率的增大有关）而使用质量更大的重球；零件表面加工的改进导致摩擦的减小；为了提高机器的运转速度必然要减小飞轮的惯性矩 $J$ ；减小速度对负载的依赖性的趋势导致运行不均衡性的减小。查明上述原因后，维什涅格拉德斯基建议人为地增加摩擦（利用特殊的缓冲装置）和加大运行不均衡性（依靠与机器结构有关的参数 $n$ 和 $k$ 的变化）。

以上内容（稳定性分析部分）基本来自庞特里亚金的《常微分方程》（第6版；林武忠，倪明康译；高等教育出版社；2006）第五章§27。

我还试着用 MATLAB 求解了非线性方程组 $(13)$ ，并针对两组不同的参数（略去单位）得到了以下结果：

1. $g=10,\,m=1,\,b=0.5,\,J=10,\,n=1,\,k=10,\,F=5$ ，则平衡位置为 $\displaystyle\varphi_0=\arccos\left(\frac{F}{k}\right)=\frac{\pi}{3},\,\psi_0=0,\,\omega_0=\frac{1}{n}\sqrt{\frac{gk}{F}}=2\sqrt5$ 。同时可以计算得 $\displaystyle\frac{bJ}{m}\cdot\nu=\sqrt5>1$ 。设定初始条件为 $\displaystyle\varphi_i=\frac{\pi}{2},\,\psi_i=3,\,\omega_i=6$ ，利用中阶龙格库塔方法（ode45）在时间区间 $[0,\,100]$ 上求解方程组 $(13)$ 。得到的结果如下图（a）所示。可以看到平衡解是渐近稳定的。
2. $g=10,\,m=5,\,b=0.5,\,J=10,\,n=1,\,k=10,\,F=5$ ，则平衡位置仍为 $\displaystyle\varphi_0=\frac{\pi}{3},\,\psi_0=0,\,\omega_0=2\sqrt5$ 。此时， $\displaystyle\frac{bJ}{m}\cdot\nu=\frac{\sqrt5}{5}<1$ 。设定初始条件为 $\displaystyle\varphi_i=\frac{\pi}{3},\,\psi_i=0.05,\,\omega_i=2\sqrt{5}$ （即与平衡位置仅有一极小偏差，相当于一个小扰动），利用相同的方法求解方程组 $(13)$ 。得到的结果如下图（b）所示。可以看到，即使仅有一极小扰动，系统也无法演化到稳定平衡状态之上。

![]((20240501)离心调速器从物理建模到微分方程平衡解的稳定性分析_Quaternion/v2-884519cd9924fd75cda529c9bb86aedd_1440w.jpg)  


（a）左图为φ，ψ和ω随时间的变化，右图是解对应的相空间中的轨迹；可以看到，平衡解是稳定的

  
  
![]((20240501)离心调速器从物理建模到微分方程平衡解的稳定性分析_Quaternion/v2-8c708d3798313148464d2a477adde74e_1440w.jpg)  


（b）左图为φ，ψ和ω随时间的变化，右图是解对应的相空间中的轨迹；可以看到，平衡解是不稳定的

  
  
## 后记  
笔者原本计划在寒假写完这篇文章的，但是还是拖延到了第二个学期。不过总体来说，这次确实比上一篇文章的拖延程度减轻了不少，毕竟上一篇文章拖延了将近9个月……

笔者原本只是想简单按照庞特里亚金书中的内容写写离心调速器的工作原理的（即文章的物理建模部分），没想到后来越写越多，最后摊了这么大的一张饼……

BTW，封面的这幅图是用必应的 Copilot 创作的。

2024年5月1日

