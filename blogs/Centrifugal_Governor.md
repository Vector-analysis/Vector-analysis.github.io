---
title: "Zhaofeng Peng - Blog"
layout: piclay
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

# Centrifugal Governor: From Physical Modeling to Stability Analysis of Differential Equation Equilibrium Solutions

**Link:** For the Chinese version, click [here](https://zhuanlan.zhihu.com/p/673357410).

*Note: The English version was translated with the help of [Microsoft Copilot](https://www.microsoft.com).*

## Introduction
This semester, I chose to study Ordinary Differential Equations. Recently (December 19, 2023), I learned about Lyapunov stability. While browsing through Pontryagin's *Ordinary Differential Equations*, I happened to see a section related to the stability analysis of centrifugal governors, which instantly took me back to those joyful moments in middle school when I would lie in bed reading *The Three-Body Problem* with a flashlight. Yun Tianming's three stories left a profound impact on me back then. Hence, I decided to refer to Pontryagin's book and write something about centrifugal governors.

Due to the limited length of this article, it can't cover everything in detail. Therefore, readers are expected to have some prerequisite knowledge, including (but not limited to) understanding the solutions of linear differential equations with constant coefficients and systems of equations.

Let's start with physical modeling.

## Model
First, let's look at the definition of a centrifugal governor. Wikipedia provides the following definition:

> A **centrifugal governor** is a specific type of governor with a feedback system that controls the speed of an engine by regulating the flow of fuel or working fluid, so as to maintain a near-constant speed. It uses the principle of proportional control.  

Here's an illustration (image from Wikipedia):

![Centrifugal Governor](https://pica.zhimg.com/v2-e8f3b205e9d97711f5ee2ef4f0ef658c_1440w.jpg)

<figure>
  <img src="https://pica.zhimg.com/v2-e8f3b205e9d97711f5ee2ef4f0ef658c_1440w.jpg">
</figure>

<figure>
  <img src="{{ site.url }}{{ site.baseurl }}/images/homepage/IMG_20230506_124705.jpg" style="display: block; margin-left: auto; margin-right: auto; width: 50%;">
</figure>

<figure>
    <img src="https://pica.zhimg.com/v2-e8f3b205e9d97711f5ee2ef4f0ef658c_1440w.jpg" alt="Centrifugal Governor" style="display: block; margin-left: auto; margin-right: auto; width: 68%;">
    <figcaption style="text-align: center; font-size: 12px; color: #555;">A schematic diagram of a centrifugal "flyball" governor; as the speed increases, the balls swing outward, thereby closing the valve until the speed drops to the desired constant value.</figcaption>
</figure>

In summary, a centrifugal governor is an automatic control system that utilizes centrifugal motion.

In 1868, James Clerk Maxwell wrote a famous paper titled *On Governors*, which is widely regarded as a classic in feedback control theory. In 1876, Ivan Alekseevich Vyshnegradsky independently analyzed the centrifugal governor in steam engine systems, providing important guidance for engineering. Next, we will focus on Vyshnegradsky's research results.

According to Pontryagin's book, we simplify the centrifugal governor as follows:

<!--![Simplified Model](https://pic3.zhimg.com/v2-407351d37d73251bca706ce8625ae320_1440w.jpg)-->
<div class="fig">
    <img src="https://pic3.zhimg.com/v2-407351d37d73251bca706ce8625ae320_1440w.jpg" alt="Simplified Model">
    <div class="fig-caption">The image is taken from the English version of the book.</div>
</div>

In the diagram, $S$ is a vertical pivot that can rotate about its vertical axis, with its upper end connected by hinges to two rods of the same length, $L_1$ and $L_2$. The lower ends of $L_1$ and $L_2$ each carry a heavy ball of mass $m$. $L_1$ and $L_2$ are also connected by hinges to auxiliary rods, which can drive a special sleeve $M$ that slides on the pivot $S$. The angle between each rod and the pivot $S$ is denoted as $\varphi$, and the lengths of $L_1$ and $L_2$ are unit lengths. When pivot $S$ rotates at an angular velocity $\theta$, the heavy balls experience centrifugal force, gravity, and the force from the rods. If the heavy balls remain stationary relative to the pivot in this rotating frame, the sum of these three forces is zero. According to this assumption, the centrifugal force acting on the heavy balls is $m\theta^2\sin\varphi$, and the gravity is $mg$. These two forces can be decomposed into components perpendicular to and along the rod axis, as shown in the following diagram:

![Force Decomposition](https://pic4.zhimg.com/v2-a0cfe8255957748386daaf4ee106a6e9_1440w.jpg)

The image is taken from the English version of the book.

When the rotation speed of pivot $S$ is constant, the heavy balls remain stationary relative to the pivot $S$ (without disturbances), and the components of centrifugal force and gravity along the rod axis balance the force from the rods; the sum of the components perpendicular to the rod axis is zero, i.e., 
$$m\theta^2\sin\varphi\cos\varphi - mg\sin\varphi = 0 \tag{1}$$

In fact, we know that the heavy balls swing outward as the angular velocity of the pivot $S$ increases (similar to a toy drum). In this process, we also need to consider the friction of the hinges. The book mentions: "It (friction) depends in a very complex form on the motion that occurs. To simplify the complexity essentially, we assume the friction is proportional to the velocity $\dot{\varphi}$ of mass $m$ (i.e., the heavy balls) and has the opposite sign, with a magnitude $-b\dot{\varphi}$, where $b$ is a constant." According to Newton's second law, we can obtain a differential equation for $\varphi$:
$$m\ddot{\varphi} = m\theta^2\sin\varphi\cos\varphi - mg\sin\varphi - b\dot{\varphi} \tag{2}$$

(Note: The additional forces generated by the changes in $\theta$ and $\varphi$ are balanced by the reaction forces from the rods and hinges.)

In the schematic diagram of the centrifugal governor, we can see a flywheel rotating at an angular velocity $\omega$. The flywheel is driven by steam and can output useful work, such as lifting weights. Let $J$ be the moment of inertia of the flywheel. According to the angular momentum theorem:
$$J\dot{\omega} = P_1 - P \tag{3}$$

where $P_1$ is the torque exerted by the steam, and $P$ is the torque exerted by the weight on the flywheel. The flywheel is connected to the pivot $S$ of the governor through transmission gears, so the steam input decreases when the flywheel speed is too high, and the steam input increases when the flywheel speed is too low. The transmission gears relate the angular velocity $\omega$ of the flywheel to the angular velocity $\theta$ of the pivot $S$:
$$\theta = n\omega \tag{4}$$

where $n$ is a constant known as the gear ratio.

Finally, we need to relate $\varphi$ in the above equations to the right-hand side of $(3)$, $P_1 - P$, to obtain the differential equations describing the model. We know that the function of the centrifugal governor is to maintain the flywheel speed essentially constant. From $(1)$ and $(4)$, we see that $\varphi$ should also remain essentially constant. Suppose the value of $\varphi$ fluctuates around $\varphi^{\ast}$ (i.e., $\varphi^{\ast}$ is the "mean value" of $\varphi$). As the flywheel speed increases, the value of $\varphi$ increases, moving the sleeve $M$ upward and closing the steam valve through a lever, thereby reducing the torque $P_1$ exerted by the steam; as the flywheel speed decreases, the value of $\varphi$ decreases, moving the sleeve $M$ downward and opening the steam valve through a lever, thereby increasing the torque $P_1$ exerted by the steam. Therefore, we assume:
$$P_1 = F_1 + k(\cos\varphi - \cos\varphi^{\ast}) \tag{5}$$

where $F_1$ is the value of $P_1$ when $\varphi = \varphi^{\ast}$, and $k > 0$ is a proportional constant. (It can be seen that $(\cos\varphi - \cos\varphi^{\ast})$ is actually proportional to the distance the sleeve $M$ moves up or down.)

Combining the relations $(2)-(5)$, we obtain the system of differential equations describing the model:
$$\left\{ \begin{array}{l} m\ddot{\varphi} = mn^2\omega^2\sin\varphi\cos\varphi - mg\sin\varphi - b\dot{\varphi} \\ J\dot{\omega} = k\cos\varphi - F \end{array} \right. \tag{6}$$

where $F = P - F_1 + k\cos\varphi^{\ast}$ is a quantity related to the load. Thus, we have established the physical model to be studied and its corresponding differential equations.

The above content (physical modeling part) is mainly from Pontryagin's *Ordinary Differential Equations* (6th edition; translated by Lin Wuzhong and Ni Mingkang; Higher Education Press; 2006), Chapter 5, §27.

Next, we briefly introduce the definition of solution stability and some criteria for determining solution stability. Readers who are familiar with these contents can skip this part and directly read the last section of the article: Analysis of the Stability of Equilibrium Solutions of the Equation.

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

