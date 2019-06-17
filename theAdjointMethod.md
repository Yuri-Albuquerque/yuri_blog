[Main][principal]
# Lecture Notes
## terça, 11. junho 2019 04:03 
---

### The adjoint method 
###### source: [@bradley2010pde]
Let \\(x\in\mathbb{R}^{n_x}, p\in\mathbb{R}^{n_p}\\), a measure of merit \\(f(x,p):\mathbb{R}^{n_x}\times\mathbb{R}^{n_p}\to\mathbb{R}\\) and the relationship \\(g(x,p)=0\\) for a function \\(g:\mathbb{R}^{n_x}\times\mathbb{R}^{n_p}\to\mathbb{R}^{n_x}\\) nonsingular in everywhere.
First
\begin{align}
d_pf &= d_pf(x(p)) = \partial_xfd_px \label{df}
\end{align}

second, 
\begin{align}
g(x,p) = 0 \Rightarrow d_pg =0 \nonumber
\end{align}
only because \\(g =0\\) everywhere. Now, expanding the total derivative
\begin{align}
g_xd_px+g_p &=0 \Rightarrow d_px = -g_x^{-1}g_p \nonumber 
\end{align}
Substituting \\(d_px\\) in \\(\eqref{df}\\) 

\begin{align}
d_pf &= \underset{=\lambda}{\underbrace{-\partial_xfg_x^{-1}}}g_p \nonumber
\end{align}

The term \\(-\partial_xfg_x^{-1}\\) is a row vector times a \\(n_x\times n_p\\) matrix and will be understood as the solution to the linear equation 

\begin{align}
-\partial_x f g_x^{-1} &= \lambda \nonumber
\end{align}
thus, 

\begin{align}
g_x^{\mathsf{T}} \lambda &= -\partial_x f \label{adjointEq} 
\end{align}

**In terms of \\(\lambda\\) Eq. \\(\eqref{df}\\) turns to, \\(d_p f = \lambda^{\mathsf{T}}g_p\\).**

---

Another derivation is useful. Define the *Lagrangian*

\begin{align}
\mathcal{L}(x,p,\lambda) &= f(x) + \lambda^{\mathsf{T}}g
\end{align}
 \begin{align}
\mathcal{L}(x,p,\lambda) &= f(x) + \lambda^{\mathsf{T}}g(x,p) \nonumber
\end{align}
 
 As $g(x,p) = 0 $ in everywhere and we may chosse $\lambda$ freely, $f(x,p) = \mathcal{L}(x,p,\lambda)$ 
 $$
 \begin{align}
 d_p f = d_p \mathcal{L} &= \partial_x f d_p x + d_p \lambda^{\mathsf{T}} g +\lambda^{\mathsf{T}}(\partial_x g d_p x + \partial_p g)\nonumber\\
 & = \partial_x f d_px + \lambda^{\mathsf{T}}(\partial_x g d_p x+ \partial_p g) \nonumber\\
 & = (\partial_x f+ \lambda^{\mathsf{T}}\partial_x g)d_p x + \lambda^{\mathsf{T}}\partial_p g \label{df2}
 \end{align}
 $$
 
If we choose $\lambda$ as a solution of

$$ \partial_x g^{\mathsf{T}} \lambda = -\partial_x f$$

then we can avoid the need to compute $d_p x$ in \eqref{df2}. This condition is exactly the adjoint equation \eqref{adjointEq}. What remains as the first derivation $d_p f = \lambda^{\mathsf{T}} g_p$. 

{% include image.html url="https://media.giphy.com/media/Q1aRmd8e90WIw/giphy.gif" description="It will be clear why we are doing this accounts." width="70" height="50" %}

In second approach the problem solver must
> * evaluate $f(x,p)$
> * solve $g(x,p)=0$
> * compute the gradient $d_p f$  

#### Problem Statement 
Consider the problem
 $$
 \begin{align}
 \underset{p}{\hbox{min}} \; F(x,p) &= \int^T_0 f(x,p,t)\label{mainOptProblem}\\
 \hbox{subject to,} &\begin{cases} h(x,\dot{x},p,t) =0 \\
 g(x(0),p) = 0
 \end{cases}\nonumber
 \end{align} 
 $$
 where, 
 > $p$ is vector of unknown parameters,
 > $x$ is a vector valued function,
 > $h(x,\dot{x}, p, t)=0$ is an ODE in implicit form,
 > and $g(x(p),p) = 0$ is the initial conditions.

A gradiente-based optmization algorithm requires to calculate the total derivative

$$
\begin{align}
d_p F(x,p) &= \int_0^T \partial_x f d_p x + \partial_p f\; dt \nonumber
\end{align} 
$$

but, calculating $d_p x$ is difficult in most cases. 

###### How to work around this problem?
Let

$$
\begin{align}
\mathcal{L}(x,p,\lambda,t)&\equiv \int_0^T f(x,p,t)+\lambda^{\mathsf{T}}h(x,\dot{x},p,t)\; dt +\mu^{\mathsf{T}}g(x(0),p)\label{lagrangian}
\end{align}
$$

be the Lagrangian corresponding to the optimization problem $\eqref{mainOptProblem}$.  

> where, the vector of *Lagrange* multipliers $\lambda(t)$ is a function of time and $\mu$ is vector of multipliers associated with initial conditions. 

So, one can computing

$$
\begin{align}
d_p\mathcal{L} \equiv & \int_0^T\partial_x f d_p x + \partial_p f + \lambda^{\mathsf{T}}(\partial_x d d_p x +\partial_{\dot{x}}hd_p\dot{x} + \partial_p h)\; dt\nonumber\\
& + \mu^{\mathsf{T}}(\partial_{x(0)}g d_p x(0)+\partial_p g)\label{dpL}
\end{align}
$$

and this comes from the fact that

$$
\begin{align}
h\equiv 0, \qquad g\equiv 0, \hbox{ thus }\qquad d_p\mathcal{L} = d_p F.\nonumber
\end{align}
$$

Integrating by parts the term with $d_p\dot{x}$

$$
\begin{align}
\int_0^T \lambda^{\mathsf{T}}\partial_{\dot{x}}h d_p\dot{x} dt &= \lambda^{\mathsf{T}}\partial_{\dot{x}}h d_px\bigg|_{0}^T -\int_0^T(\lambda^{\mathsf{T}}\partial_{\dot{x}}+\lambda^{\mathsf{T}}d_t \partial_{\dot{x}}h)d_px\; dt\nonumber
\end{align}
$$

substituting in $\eqref{dpL}$ 

$$
\begin{align}
d_p\mathcal{L} \equiv & \int_0^T [\partial_x f + \lambda^{\mathsf{T}}(\partial_x h -d_t \partial_{\dot{x}}h)-\dot{\lambda^{\mathsf{T}}}\partial_{\dot{x}}h]d_p x + \partial_{p}f + \lambda^{\mathsf{T}}\partial_p h\; dt \nonumber\\
& + \lambda^{\mathsf{T}}\partial_{\dot{x}}h d_p x\bigg|_{T} + (\lambda^{\mathsf{T}}\partial_{\dot{x}}h + \mu^{\mathsf{T}}g_{x(0)})\bigg|_{0} d_p x(0) + \mu^{\mathsf{T}}g_p\nonumber
\end{align}
$$

Setting $\lambda(T)=0$, $\mu^{\mathsf{T}}=\lambda^{\mathsf{T}}\partial_{\dot{x}}h\bigg|_{0}$ $g^{-1}_{x(0)}$ and

$$
\begin{align}
\partial_{x}f + \lambda^{\mathsf{T}}(\partial_x h-d_t\partial_{\dot{x}}h)=0 \nonumber
\end{align}
$$

we can avoid to calculate $d_px$ for all time $t>0$.  

---
[Main][principal]

[principal]: https://yuri-albuquerque.github.io/yuri_blog
[@bradley2010pde]: https://cs.stanford.edu/~ambrad/adjoint_tutorial.pdf "Bradley, Andrew M. "Pde-constrained optimization and the adjoint method." (2010)."
