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

# Centrifugal Governor: From Physical Modeling to Stability Analysis of Differential Equation Equilibrium Solutions

**Link:** For the Chinese version, click [here](https://zhuanlan.zhihu.com/p/673357410).

*Note: The English version of the first half was translated with the help of [Microsoft Copilot](https://www.microsoft.com). The second half was translated by [DeepSeek](https://www.deepseek.com).*

## Introduction
This semester, I chose to study Ordinary Differential Equations. Recently (December 19, 2023), I learned about Lyapunov stability. While browsing through Pontryagin's *Ordinary Differential Equations*, I came across a section on stability analysis for centrifugal governors, which immediately brought back fond memories of my middle school days, lying in bed with a flashlight reading *The Three-Body Problem*. Yun Tianming's three stories left a deep impression on me back then. Therefore, I decided to refer to Pontryagin's book and write something about centrifugal governors.

Due to the limited length of this article, it cannot cover every detail comprehensively. Readers are expected to have some prerequisite knowledge, including (but not limited to) familiarity with solutions to linear differential equations with constant coefficients and systems of equations.

Let's begin with physical modeling.

## Model
First, let's look at the definition of a centrifugal governor. Wikipedia provides the following:

> A **centrifugal governor** is a specific type of governor with a feedback system that controls the speed of an engine by regulating the flow of fuel or working fluid, thus maintaining a nearly constant speed. It operates on the principle of proportional control.

Here is an illustration (image from Wikipedia):

<figure>
  <img src="https://pica.zhimg.com/v2-e8f3b205e9d97711f5ee2ef4f0ef658c_1440w.jpg" alt="Centrifugal Governor" style="display: block; margin-left: auto; margin-right: auto; width: 86%;">
  <figcaption style="text-align: center; font-size: 14px; color: #555;">A schematic diagram of a centrifugal "flyball" governor; as the speed increases, the balls swing outward, thereby closing the valve until the speed drops to the desired constant value.
  </figcaption>
</figure>

In summary, a centrifugal governor is an automatic control system that utilizes centrifugal motion.

In 1868, James Clerk Maxwell wrote a famous paper titled *On Governors*, widely regarded as a classic in feedback control theory. In 1876, Ivan Alekseevich Vyshnegradsky independently analyzed the centrifugal governor in steam engine systems, providing crucial guidance for engineering. Next, we will focus on Vyshnegradsky's research.

According to Pontryagin's book, we can simplify the centrifugal governor as follows:

<figure>
  <img src="https://pic3.zhimg.com/v2-407351d37d73251bca706ce8625ae320_1440w.jpg" alt="Simplified Model" style="display: block; margin-left: auto; margin-right: auto; width: 86%;">
  <figcaption style="text-align: center; font-size: 14px; color: #555;">The image is taken from the English version of the book.
  </figcaption>
</figure>

In the diagram, $S$ is a vertical pivot that can rotate about its vertical axis, with its upper end connected by hinges to two rods of equal length, $L_1$ and $L_2$. The lower ends of $L_1$ and $L_2$ each carry a heavy ball of mass $m$. $L_1$ and $L_2$ are also connected by hinges to auxiliary rods, which drive a special sleeve $M$ sliding along the pivot $S$. The angle between each rod and the pivot $S$ is denoted as $\varphi$, and the lengths of $L_1$ and $L_2$ are taken as unit length. When the pivot $S$ rotates with angular velocity $\theta$, the heavy balls experience centrifugal force, gravity, and the force from the rods. If the heavy balls remain stationary relative to the pivot in this rotating frame, the sum of these three forces is zero. Under this assumption, the centrifugal force on each heavy ball is $m\theta^2\sin\varphi$, and gravity is $mg$. These two forces can be decomposed into components perpendicular to and along the rod axis, as shown below:

<figure>
  <img src="https://pic4.zhimg.com/v2-a0cfe8255957748386daaf4ee106a6e9_1440w.jpg" alt="Force Decomposition" style="display: block; margin-left: auto; margin-right: auto; width: 86%;">
  <figcaption style="text-align: center; font-size: 14px; color: #555;">The image is taken from the English version of the book.
  </figcaption>
</figure>

When the rotational speed of pivot $S$ is constant, and the heavy balls are stationary relative to $S$ (undisturbed), the components of centrifugal force and gravity along the rod axis balance the rod forces; the sum of the components perpendicular to the rod axis is zero, i.e.,

$$m\theta^2\sin\varphi\cos\varphi - mg\sin\varphi = 0 \tag{1}$$

We know that the heavy balls swing outward as the angular velocity of pivot $S$ increases (similar to a toy rattle-drum). In this process, we must also consider hinge friction. The book states: "It (friction) depends in a very complex form on the motion that occurs. To simplify essentially, we assume the friction is proportional to the velocity $\dot{\varphi}$ of mass $m$ (the heavy balls) and has the opposite sign, with magnitude $-b\dot{\varphi}$, where $b$ is a constant." According to Newton's second law, we obtain a differential equation for $\varphi$:

$$m\ddot{\varphi} = m\theta^2\sin\varphi\cos\varphi - mg\sin\varphi - b\dot{\varphi} \tag{2}$$

(Note: Additional forces due to changes in $\theta$ and $\varphi$ are balanced by reaction forces from the rods and hinges.)

In the centrifugal governor schematic, we see a flywheel rotating at angular velocity $\omega$. The flywheel is driven by steam and can perform useful work, such as lifting weights. Let $J$ be the moment of inertia of the flywheel. According to the angular momentum theorem:

$$J\dot{\omega} = P_1 - P \tag{3}$$

where $P_1$ is the torque exerted by steam, and $P$ is the torque from the load on the flywheel. The flywheel is connected to the pivot $S$ of the governor via transmission gears, so steam input decreases when flywheel speed is too high and increases when it is too low. The gear transmission relates flywheel angular velocity $\omega$ to pivot $S$ angular velocity $\theta$:

$$\theta = n\omega \tag{4}$$

where $n$ is a constant called the gear ratio.

Finally, we need to relate $\varphi$ to $P_1 - P$ on the right side of $(3)$ to obtain the differential equations describing the model. The centrifugal governor's function is to keep the flywheel speed essentially constant. From $(1)$ and $(4)$, $\varphi$ should also remain nearly constant. Suppose $\varphi$ fluctuates around $\varphi^{\ast}$ (i.e., $\varphi^{\ast}$ is the "mean value" of $\varphi$). As flywheel speed increases, $\varphi$ increases, raising sleeve $M$ and closing the steam valve via a lever, reducing steam torque $P_1$; as speed decreases, $\varphi$ decreases, lowering sleeve $M$ and opening the steam valve, increasing $P_1$. Thus, we assume:

$$P_1 = F_1 + k(\cos\varphi - \cos\varphi^{\ast}) \tag{5}$$

where $F_1$ is $P_1$ when $\varphi = \varphi^{\ast}$, and $k > 0$ is a proportionality constant. (Note that $(\cos\varphi - \cos\varphi^{\ast})$ is proportional to the vertical displacement of sleeve $M$.)

Combining relations $(2)-(5)$, we obtain the differential equation system describing the model:

$$\left\{ \begin{array}{l} m\ddot{\varphi} = mn^2\omega^2\sin\varphi\cos\varphi - mg\sin\varphi - b\dot{\varphi} \\ J\dot{\omega} = k\cos\varphi - F \end{array} \right. \tag{6}$$

where $F = P - F_1 + k\cos\varphi^{\ast}$ is a quantity related to the load. Thus, we have established the physical model and its corresponding differential equations.

The above content (physical modeling part) is primarily from Pontryagin's *Ordinary Differential Equations* (6th ed.; translated by Lin Wuzhong and Ni Mingkang; Higher Education Press; 2006), Chapter 5, §27.

Next, we briefly introduce the definition of solution stability and some criteria for determining it. Readers familiar with this content may skip to the final section: *Analysis of the Stability of Equilibrium Solutions of the Equation*.

## Definition of Solution Stability
Before proceeding, we first introduce the concept of Lyapunov stability. Consider an autonomous nonlinear dynamical system:
$$\dot{x}=f(x(t)),\qquad x(0)=x_0\tag{7}$$
where $x(t)\in\mathcal{D}\subseteq\mathbb{R}^n$ is the system state vector, $\mathcal{D}$ is an open set containing the origin, and $f:\mathcal{D}\rightarrow\mathbb{R}^n$ is a continuous vector field on $\mathcal{D}$. Assume $f$ has an equilibrium at $x_e$ such that $f(x_e)=0$ (i.e., $x=x_e$ is a solution of $\dot{x}=f(x)$). Then:

1. The equilibrium is **Lyapunov stable** if for every $\varepsilon>0$, there exists a $\delta>0$ such that if $\|x(0)-x_e\|<\delta$, then $\|x(t)-x_e\|<\varepsilon$ for all $t\ge0$;
2. The equilibrium is **asymptotically stable** if it is Lyapunov stable and there exists $\delta_0>0$ such that if $\|x(0)-x_e\|<\delta_0$, then $\displaystyle\lim_{t\to\infty}\|x(t)-x_e\|=0$;
3. The equilibrium is **globally asymptotically stable** if $\mathcal{D}=\mathbb{R}^n$ and in the definition of asymptotic stability, $\delta_0$ can be taken as $+\infty$.

The above is largely translated from the Wikipedia entry on Lyapunov stability.

To illustrate the concept more intuitively, we provide three schematic diagrams:

<figure>
  <img src="https://pic3.zhimg.com/v2-7167bda2b8ea9e792f39d83d865b0cd2_1440w.jpg" alt="Lyapunov Stability" style="display: block; margin-left: auto; margin-right: auto; width: 86%;">
  <figcaption style="text-align: center; font-size: 14px; color: #555;">Schematic diagrams of stability, asymptotic stability, and instability in the sense of Lyapunov.
  </figcaption>
</figure>

The blue line in the figure represents the solution $x(t)$ with initial value $x(0)=x_0$. The three images from left to right represent the equilibrium solution $x=x_e$ being stable, asymptotically stable, and unstable in the Lyapunov sense. Intuitively, if a small perturbation is applied to a system at equilibrium and the system's state remains near the equilibrium, the equilibrium is Lyapunov stable; if the state not only stays near the equilibrium but also eventually converges to it, the equilibrium is asymptotically stable.

## Stability of Homogeneous Linear Equations with Constant Coefficients
Homogeneous linear equations with constant coefficients are a common class of linear dynamical systems, with the form:
$$\frac{\mathrm{d}x}{\mathrm{d}t}=Ax\tag{8}$$
i.e., $\dot{x}=Ax$; where $x=x(t)$ is an $n$-dimensional column vector and $A$ is an $n\times n$ constant matrix. Clearly, $x=0$ (the zero solution) is an equilibrium. For the stability of this zero solution, we have the following criteria:

1. The zero solution is asymptotically stable (in fact, globally asymptotically stable) if and only if all eigenvalues of $A$ have negative real parts;
2. The zero solution is stable if and only if all eigenvalues of $A$ have non-positive real parts, and any eigenvalue with zero real part corresponds to a Jordan block of order one;
3. The zero solution is unstable if and only if at least one eigenvalue of $A$ has a positive real part, or at least one eigenvalue has zero real part and corresponds to a Jordan block of order greater than one.

Due to space constraints, we briefly outline the proof for the first criterion.

> **Proof:** The fundamental solution matrix of $\dot{x}=Ax$ is $e^{At}$. For initial value $x(0)=x_0$, the corresponding solution is $x(t)=e^{At}x_0$.  
> Let $\displaystyle\max_i\left\{\mathfrak{Re}\left[\lambda_i(A)\right]\right\}=-\alpha_0$, where $\alpha_0>0$. Choose $0<\alpha<\alpha_0$, then $\lambda_i(A)=\alpha_i+j\beta_i=-\alpha-\tilde{\alpha}_i+j\beta_i$, where $\alpha_i<0$, $\tilde{\alpha}_i>0$, and $\alpha_i=-(\alpha+\tilde{\alpha}_i)$.  
> Based on the nature of solutions to constant-coefficient homogeneous linear equations, each element of the fundamental solution matrix has the form $e^{\lambda_it}Q_i(t)$, where $Q_i(t)$ is a polynomial. Substituting $\lambda_i$, we get $e^{\lambda_i}Q_i(t)=e^{-\alpha t}\cdot e^{(-\tilde{\alpha}_i+j\beta_i)t}Q_i(t)$, and $e^{(-\tilde{\alpha}_i+j\beta_i)t}Q_i(t)$ is bounded.  
> Thus, we can prove there exist $K>0$ and $\alpha>0$ such that for $t\ge 0$, $\|e^{At}\|\le Ke^{-\alpha t}$, and hence $\|x(t)\|\le\mathscr{K}e^{-\alpha t}$ (where $\mathscr{K}>0$). Therefore, the zero solution is asymptotically stable.

Readers interested in detailed proofs of these criteria may refer to standard ordinary differential equation textbooks. These theorems show that determining the stability of the zero solution reduces to examining the eigenvalues of $A$.

The Hurwitz theorem is often used to determine if all eigenvalues have negative real parts, thereby assessing asymptotic stability of the zero solution. It states:

* Let $Q(\lambda)=\lambda^n+a_1\lambda^{n-1}+\cdots+a_{n-1}\lambda+a_n$ be a real-coefficient polynomial. Define $D_1=a_1$, and $D_k=\det \begin{bmatrix} a_1 & a_3 & a_5 & \cdots & a_{2k-1} \\ 1 & a_2 & a_4 & \cdots & a_{2k-2} \\ 0 & a_1 & a_3 & \cdots & a_{2k-3} \\ 0 & 1 & a_2 & \cdots & a_{2k-4} \\ \vdots & \vdots & \vdots & &\vdots \\ 0 & 0 & 0 & \cdots & a_k\\ \end{bmatrix},\ (k=2,\cdots,n)$, where $a_i=0$ for $i>n$. Then all roots of $Q(\lambda)=0$ have negative real parts if and only if $D_k>0$ for $k=1,\cdots,n$, and $a_i>0$ for $i=1,\cdots,n$.

We will use this theorem later to compute conditions for stability of the equilibrium solution for the centrifugal governor differential equations.

## Stability of Nonlinear Equations: Linearization Method
For a general nonlinear dynamical system:
$$\frac{\mathrm{d}x}{\mathrm{d}t}=f(t,x)\tag{9}$$
denote the solution satisfying initial condition $x(\tau)=\xi_0$ as $x(t)=\phi(t,\tau,\xi_0)$. By transforming $x=y+\phi(t,\tau,\xi_0)$, system $(9)$ becomes:
$$\frac{\mathrm{d}y}{\mathrm{d}t}=f(t,y+\phi(t,\tau,\xi_0))-f(t,\phi(t,\tau,\xi_0))\tag{10}$$
It can be seen that $y=0$ is an equilibrium of system $(10)$; i.e., the solution $\phi(t,\tau,\xi_0)$ of $(9)$ is equivalent to the zero solution of $(10)$. Thus, we may assume system $(9)$ has a zero solution $x=0$, and under suitable differentiability assumptions, it can be rewritten as:
$$\frac{\mathrm{d}x}{\mathrm{d}t}=A(t)x+R(t,x)\tag{11}$$
where $R(t,x)$ is the sum of all terms of order higher than one in the expansion of $f(t,x)$ with respect to $x$. Assume $A(t)$ is a constant matrix $A$, $R(t,x)$ satisfies certain continuity conditions and a local Lipschitz condition in $x$. Also, $R(t,0)=0$ and $\displaystyle\lim_{|x|\to0}\frac{R(t,x)}{|x|}=0$ uniformly for $t>\tau$. Then, the stability of the zero solution of $(11)$ can, to some extent, be determined by its first approximation $\dot{x}=Ax$. We have the following criteria (note we assume $A(t)=A$ is constant):

1. If all eigenvalues of $A$ have negative real parts, then the zero solution of $(11)$ is asymptotically stable;
2. If at least one eigenvalue of $A$ has a positive real part, then the zero solution of $(11)$ is unstable.

Proofs of these theorems can be found in standard ODE textbooks. The Jacobian matrix is commonly used to linearize the equation:
$$\dot{x}=\mathrm{J}x,\qquad \mathrm{J}=\left.\frac{\partial f}{\partial x}\right|_{x=x_e}\tag{12}$$
where $\mathrm{J}$ is the Jacobian matrix evaluated at the equilibrium point $x=x_e$ (satisfying $f(x_e)=0$). If all eigenvalues of this Jacobian matrix have strictly negative real parts, then the equilibrium solution $x=x_e$ is asymptotically stable. The Hurwitz theorem can again be used to help determine asymptotic stability.

The above content (on linearization) is largely from Wu Zhuogun and Li Yong's *Ordinary Differential Equations* (1st ed.; Higher Education Press; 2004), Chapter 5, Section 1.2.

## Stability Analysis of Equilibrium Solutions of the Equation
We previously derived the differential equation system $(6)$ to be studied. However, the first equation is second-order, so we introduce $\psi=\dot{\varphi}$ to convert $(6)$ into standard form:
$$\left\{ \begin{array}{l} \dot{\varphi}=\psi\\ \dot{\psi}=n^2\omega^2\sin\varphi\cos\varphi-g\sin\varphi-\dfrac{b}{m}\psi\\ \dot{\omega}=\dfrac{k}{J}\cos\varphi-\dfrac{F}{J} \end{array}\right.\tag{13}$$
Setting the right-hand sides of $(13)$ to zero yields the equilibrium positions $\varphi=\varphi_0,\ \psi=\psi_0,\ \omega=\omega_0$ satisfying:
$$\left\{  \begin{array}{l}  \psi_0=0\\ \cos\varphi_0=\dfrac{F}{k}\\ n^2\omega_0^2=\dfrac{g}{\cos\varphi_0} \end{array}\right.\tag{14}$$
This equilibrium represents that when the load is constant (i.e., $F$ is constant), the flywheel's angular velocity $\omega$ remains constant ($\omega=\omega_0$), the steam supply valve is stationary, and the angle $\varphi$ is constant ($\varphi=\varphi_0$). To study the stability of this equilibrium, we linearize system $(13)$ using the Jacobian matrix, obtaining:
$$\frac{\mathrm{d}}{\mathrm{d}t} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix}= \left.\begin{bmatrix} 0 & 1 & 0 \\ n^2\omega^2\cos2\varphi-g\cos\varphi & -\frac{b}{m} & n^2\omega\sin2\varphi \\ -\frac{k}{J}\sin\varphi & 0 & 0\\ \end{bmatrix} \right|_{\varphi=\varphi_0,\,\psi=\psi_0,\,\omega=\omega_0} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix} \tag{15}$$
After simplification:
$$\frac{\mathrm{d}}{\mathrm{d}t} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix}= \begin{bmatrix} 0 & 1 & 0 \\ -\frac{g\sin^2\varphi_0}{\cos\varphi_0} & -\frac{b}{m} & \frac{2g\sin\varphi_0}{\omega_0} \\ -\frac{k\sin\varphi_0}{J} & 0 & 0\\ \end{bmatrix} \begin{bmatrix} \varphi\\ \psi\\ \omega\\ \end{bmatrix} \tag{16}$$
According to the earlier criteria, we determine stability by the signs of the real parts of the eigenvalues of the coefficient matrix. The characteristic polynomial of $(16)$ is:
$$Q(\lambda)= \begin{vmatrix} \lambda & -1 & 0 \\ \frac{g\sin^2\varphi_0}{\cos\varphi_0}  & \lambda+\frac{b}{m} & -\frac{2g\sin\varphi_0}{\omega_0} \\ \frac{k\sin\varphi_0}{J} & 0 & \lambda \end{vmatrix} \tag{17}$$
Thus, the characteristic equation $Q(\lambda)=0$ is:
$$\lambda^3+\frac{b}{m}\lambda^2+\frac{g\sin^2\varphi_0}{\cos\varphi_0}\lambda+\frac{2kg\sin^2\varphi_0}{J\omega_0}=0\tag{18}$$
All coefficients of this equation are positive. We can apply the Hurwitz theorem to derive necessary and sufficient conditions for stability. Simple calculation yields: the equilibrium is stable if and only if
$$\frac{bJ}{m}>\frac{2k\cos\varphi_0}{\omega_0}=\frac{2F}{\omega_0}\tag{19}$$
Thus, we obtain a sufficient condition for stability of the machine-regulator system, given by relation $(19)$.

To explain the right-hand side of inequality $(19)$, we introduce the engineering concept of *nonuniformity of performance*. According to $(14)$, when the load-related quantity $F=P-F_1+k\cos\varphi^{\ast}$ changes (i.e., when load $P$ changes), the equilibrium steady speed $\omega_0$ also changes. Then, $\displaystyle\frac{\mathrm{d}\omega_0}{\mathrm{d}P}$ describes the rate of change of $\omega_0$ with respect to load $P$. Its absolute value $\displaystyle\nu=\left|\frac{\mathrm{d}\omega_0}{\mathrm{d}P}\right|$ (as we will see, the derivative $\displaystyle\frac{\mathrm{d}\omega_0}{\mathrm{d}P}$ is negative) is called the nonuniformity of performance of the steam engine. From equilibrium condition $(14)$, we have $F\omega_0^2=\text{const.}$, so differentiation gives $\displaystyle\frac{\mathrm{d}\omega_0}{\mathrm{d}F}=-\frac{\omega_0}{2F}$. Hence, $\displaystyle\nu=\frac{\omega_0}{2F}$, and stability condition $(19)$ can be written as:
$$\frac{bJ}{m}\cdot\nu>1\tag{20}\\$$
Based on formula $(20)$, Vyshnegradsky drew the following conclusions:

1. Increasing the mass $m$ of the heavy balls is detrimental to stability;
2. Decreasing the friction coefficient $b$ is detrimental to stability;
3. Decreasing the flywheel's moment of inertia $J$ is detrimental to stability;
4. Decreasing the nonuniformity of performance $\nu$ is detrimental to stability.

In the mid-19th century, certain design changes to centrifugal governors made them unreliable. Specifically, due to technological advancements, the four quantities in inequality $(20)$ changed in ways that undermined stability: heavier balls were used due to increased valve weight (associated with higher machine power); improved surface finishing reduced friction; higher operating speeds necessitated smaller flywheel inertia $J$; and the trend to reduce speed dependence on load decreased performance nonuniformity $\nu$. After identifying these causes, Vyshnegradsky recommended artificially increasing friction (using special dampers) and increasing performance nonuniformity (by adjusting parameters $n$ and $k$ related to machine design).

The above content (stability analysis part) is largely from Pontryagin's *Ordinary Differential Equations* (6th ed.; translated by Lin Wuzhong and Ni Mingkang; Higher Education Press; 2006), Chapter 5, §27.

I also attempted to solve the nonlinear system $(13)$ using MATLAB, obtaining results for two different parameter sets (units omitted):

1. $g=10,\,m=1,\,b=0.5,\,J=10,\,n=1,\,k=10,\,F=5$. The equilibrium is $\displaystyle\varphi_0=\arccos\left(\frac{F}{k}\right)=\frac{\pi}{3},\,\psi_0=0,\,\omega_0=\frac{1}{n}\sqrt{\frac{gk}{F}}=2\sqrt5$. Also, $\displaystyle\frac{bJ}{m}\cdot\nu=\sqrt5>1$. With initial conditions $\displaystyle\varphi_i=\frac{\pi}{2},\,\psi_i=3,\,\omega_i=6$, solving system $(13)$ on time interval $[0,\,100]$ using a medium-order Runge-Kutta method (ode45) yields the results shown in Figure (a). The equilibrium solution is asymptotically stable.
2. $g=10,\,m=5,\,b=0.5,\,J=10,\,n=1,\,k=10,\,F=5$. The equilibrium remains $\displaystyle\varphi_0=\frac{\pi}{3},\,\psi_0=0,\,\omega_0=2\sqrt5$. Now, $\displaystyle\frac{bJ}{m}\cdot\nu=\frac{\sqrt5}{5}<1$. With initial conditions $\displaystyle\varphi_i=\frac{\pi}{3},\,\psi_i=0.05,\,\omega_i=2\sqrt{5}$ (a tiny deviation from equilibrium, equivalent to a small perturbation), solving $(13)$ with the same method yields results in Figure (b). Even with a minute perturbation, the system does not evolve to a stable equilibrium.

![](https://picx.zhimg.com/v2-884519cd9924fd75cda529c9bb86aedd_1440w.jpg)

(a) Left: $\varphi,\ \psi$, and $\omega$ versus time; Right: trajectory in phase space. The equilibrium solution is stable.

![](https://pica.zhimg.com/v2-8c708d3798313148464d2a477adde74e_1440w.jpg)

(b) Left: $\varphi,\ \psi$, and $\omega$ versus time; Right: trajectory in phase space. The equilibrium solution is unstable.

## Postscript
I originally planned to finish this article during the winter vacation, but it got delayed until the second semester. However, overall, this delay was much less than for my previous article, which was postponed for nearly nine months...

Initially, I intended to simply follow Pontryagin's book to explain how centrifugal governors work (the physical modeling part). Unexpectedly, it grew into such a large undertaking...

May 1, 2024

<p>&nbsp;</p>