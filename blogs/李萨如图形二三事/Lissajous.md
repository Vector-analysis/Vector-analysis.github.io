---
title: "Zhaofeng Peng - Blog"
layout: textlay
excerpt: "Zhaofeng Peng -- Blog"
sitemap: false
permalink: /blog/lissajous/
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

# A Few Things About Lissajous Figures

I just completed a semester of Theoretical Mechanics (vector mechanics for mechanics majors), but due to various reasons (subjective laziness, objective pandemic), I didn't grasp it very solidly QAQ. So I plan to spend some time during the winter break to organize and thoroughly appreciate (read: suffer through) theoretical mechanics, preparing for future courses. *(In the end, I dragged it all the way to the end of the summer vacation... someone save me from procrastination @_@)*

Today, let's talk about Lissajous figures. One of the major assignments this semester was about Lissajous figures, so I tried making a small program using the Unity engine to demonstrate them. Part of this article is based on our group report. I won't go into too much detail about the concept of Lissajous figures here. The Lissajous figure in this article is defined by the following parametric equations:
$$x=\cos(\omega_xt)\ ,\\y=\cos(\omega_yt+\varphi)\ .$$

Simply denoted as $(\omega_x,\omega_y,\varphi)$.

First, what caught our interest was this phenomenon: when the phase $\varphi$ in the parametric equations changes, the shape of the figure also changes, making it look as if a certain three-dimensional figure is rotating. As shown below:

![](./assets/v2-d078a1933a929a91d93ce1b1542ba079_b.gif)

![](./assets/v2-fd91cdfe81525c8ebcca42f0ee8b3d53_b.gif)

![](./assets/v2-42bf99e0ae0a5e8677568ed0d61b1e44_b.gif)

The three images above look as if the observer's position is fixed and the figure is "rotating" around the $y$-axis. Can we prove that the change in the phase $\varphi$ of the 2D Lissajous figure is indeed equivalent to the rotation of a 3D figure? This led us to introduce the concept of a "3D Lissajous figure." The "3D Lissajous figure" is defined by the following parametric equations:
$$x=\cos(\omega_xt+\varphi_x)\ ,\\y=\cos(\omega_yt+\varphi_y)\ ,\\z=\cos(\omega_zt+\varphi_z)\ .$$
Based on observation, let's first propose some conjectures. For the above images, my subjective feeling (some friends might feel differently) is: a 3D figure rotates around the $y$-axis, clockwise (i.e., $\vec{\omega}$ points to the negative $y$-axis; sometimes it also feels like the rotation direction becomes counterclockwise, i.e., $\vec{\omega}$ points to the positive $y$-axis). Viewing this rotating figure as a rigid body, if we focus on a fixed point on the body (like a point at the very bottom where $y =-1$), we feel that this point is moving in a circular path around the $y$-axis. Therefore, we speculate that this rotating 3D curve should be represented by the following parametric equations:
$$x=\cos(\omega_xt)\ ,\\y=\cos(\omega_yt)\ ,\\z=\sin(\omega_xt)\ .$$

Looking from the negative $y$-axis upward (or from the positive $y$-axis downward), the projection of the 3D curve on the $x\text{O}z$ plane is a unit circle, i.e., $x^2+z^2=1$; looking from the positive $z$-axis downward, the projection of the 3D curve on the $x\text{O}y$ plane is the 2D Lissajous figure $(\omega_x,\omega_y,0)$. This 3D curve is a special "3D Lissajous figure" with $\varphi_x=\varphi_y=0\ ,\ \varphi_z=-\frac{\pi}{2}$. Using the small program I made, let's first draw the "3D Lissajous figures" corresponding to the three images above (the vertical axis in the figures is the $y$-axis):

![](./assets/v2-abebb3378bb587f58536c32fd6bd8b70_r.jpg)

![](./assets/v2-ca48e6d18991dc70afbf958064b5ae2e_r.jpg)

![](./assets/v2-8965986bd050ef7be67a4924d89b4b05_r.jpg)

They seem somewhat similar.

Next, let's specifically prove that the rotation of such a 3D Lissajous figure is equivalent to the phase $\varphi$ change of the 2D Lissajous figure. First, we need to do some preparatory work. To eliminate the perspective effect (foreshortening), we need to re-project the 3D figure onto a certain 2D plane (containing the $y$-axis) (as if the "3D Lissajous figure" has fallen onto a "2D foil"); at this point, observing the above 3D figure from a direction perpendicular to the axis of rotation (i.e., perpendicular to the $y$-axis, with the observer's position in the $x\text{O}z$ plane) is equivalent to observing the projected curve on the 2D plane. If the proposition holds, the projected curve on this plane should be the Lissajous figure $(\omega_x,\omega_y,\varphi)$, where $\varphi$ is determined by the normal vector of the plane. For this, we first need to derive the formula for the projection coordinates of a point onto a plane.

Let the plane be $\Omega :Ax+By+Cz+D=0$, and let $M(x_0,y_0,z_0)$ be a point not on this plane, so $Ax_0+By_0+Cz_0+D\ne0$. Let the projection of point $M $ onto plane $\Omega$ be point $N(x_1,y_1,z_1)$. Then $\vec{MN}$ should be parallel to the plane's normal vector $\vec{n}=[A\ B\ C]^\mathrm{T}$. Thus we can set up the following equations:

$$Ax_1+By_1+Cz_1+D=0\\\frac{x_1-x_0}{A}=\frac{y_1-y_0}{B}=\frac{z_1-z_0}{C}$$
Solving these yields:
$$x_1=\frac{1}{A^2+B^2+C^2}[(B^2+C^2)x_0-ABy_0-ACz_0-AD],\\y_1=\frac{1}{A^2+B^2+C^2}[-ABx_0+(A^2+C^2)y_0-BCz_0-BD],\\z_1=\frac{1}{A^2+B^2+C^2}[-ACx_0-BCy_0+(A^2+B^2)z_0-CD].$$
This is the formula for the projection coordinates of a point onto a plane.

With this tool, we can further explore the relationship between the above 3D space curve and the 2D plane curve. We know a plane has three degrees of freedom. Since we require the projection plane to contain the $y$-axis (losing two degrees of freedom), the spatial position of the plane is now determined by only one parameter. For convenience in later processing, let's set this parameter as the angle $\theta$ between the line $l$ (half of it, a ray) where the projection plane intersects the $x\text{O}z$ plane and the $x$-axis, as shown below:

![](./assets/v2-e8aefa20c22498146d4f1d0f33c63f45_r.jpg)

Next, we transform the rotation of the figure into a change in the observer's position. Due to the relativity of motion, the figure rotating while the observer is stationary is equivalent to the observer rotating around the figure while the figure remains stationary. As illustrated below:

![](./assets/v2-18c9e25ca7040633f58a8adeb970c365_r.jpg)

Now we can finally project the 3D curve onto the aforementioned projection plane. The unit normal vector of the illustrated projection plane is $\vec{n}=(\sin\theta,0,\cos\theta)$; corresponding to the point projection formula, we have $A=\sin\theta,C=\cos\theta,B=D=0$. According to the earlier parametric equations of the 3D Lissajous figure, we have:
$$x_0=\cos(\omega_xt)\ ,\\y_0=\cos(\omega_yt)\ ,\\z_0=\sin(\omega_xt)\ ;$$
Substituting these conditions into the point projection formula yields:
$$x_1=\cos^2\theta x_0-\sin\theta\cos\theta z_0=\cos^2\theta \cos(\omega_xt)-\sin\theta\cos\theta \sin(\omega_xt),\\y_1=y_0=\cos(\omega_yt),\\z_1=-\sin\theta\cos\theta x_0+\sin^2\theta z_0=-\sin\theta\cos\theta \cos(\omega_xt)+\sin^2\theta \sin(\omega_xt).$$
This is the parametric expression of the curve obtained by projecting the 3D curve onto the projection plane. As we can see, its form is relatively complex, due to the angle $\theta$ between the projection plane and the $x\text{O}y$ plane, which results in the projected 2D parametric curve having a $z$ component. If we then rotate the projection plane, along with its projection, to coincide with the $x\text{O}y$ plane, we can obtain the expression of the projected curve on the $x\text{O}y$ plane, and now this parametric curve will have no $z$ component. For this, we need the axis rotation formula (which can be understood as rotating the entire coordinate system around the $y$-axis until the projection plane coincides with the $x\text{O}y$ plane):

![](./assets/v2-10429cf65f80b717729effb2097f2eba_r.jpg)

$$\begin{bmatrix} X\\Z \end{bmatrix}= \begin{bmatrix} \cos\theta & -\sin\theta\\ \sin\theta & \cos\theta \end{bmatrix} \begin{bmatrix} x\\z \end{bmatrix}$$
Substituting $x=x_1,z=z_1$, we calculate:
$$X=\cos\theta\cos(\omega_xt)-\sin\theta\sin(\omega_xt)=\cos(\omega_xt+\theta),\\ Y=y_1=\cos(\omega_yt),\\ Z=0.$$
That is, placing the projected curve on the $X\text{O}Y$ plane, its parametric form is:
$$\begin{matrix} X=\cos(\omega_xt+\theta)\\ Y=\cos(\omega_yt) \end{matrix} \Leftrightarrow \begin{matrix} X=\cos(\omega_x\tilde{t})\\ Y=\cos(\omega_y\tilde{t}-\frac{\omega_y}{\omega_x}\theta) \end{matrix}$$
This is the 2D Lissajous figure $(\omega_x,\omega_y,-\frac{\omega_y}{\omega_x}\theta)$. Thus, we have proven that the rotation of the aforementioned 3D Lissajous figure (equivalent to the change in the projection plane parameter $\theta$) is equivalent to the phase $\varphi$ change of the 2D Lissajous figure.

Finally, a little bonus. We found that the 3D Lissajous figure with $\omega_x:\omega_y=1:2$ looks very much like a potato chip (exposing the author's foodie nature); from a solid geometry perspective, this shape can be abstracted as a hyperbolic paraboloid, with the surface equation:
$$\frac{x^2}{a^2}-\frac{y^2}{b^2}=2z$$

![](./assets/v2-7bf2a95c0631821ffd813e573e6b1abf_r.jpg)

For the 3D Lissajous figure with $\omega_x:\omega_y=1:2$, its parametric equations are:
$$x=\cos(\omega t),\\ y=\cos(2\omega t),\\ z=\sin(\omega t).$$
After verification, it satisfies the equation $x^2-z^2=y$. This shows that this 3D Lissajous curve "lies on" a hyperbolic paraboloid.

Flowers of completion~

September 8, 2023