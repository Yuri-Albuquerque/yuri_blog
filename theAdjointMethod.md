<!-- <script type="text/x-mathjax-config"> -->
<!--   MathJax.Hub.Config({ -->
<!--     tex2jax: { -->
<!--       inlineMath: [ ['$','$'], ["\\(","\\)"] ], -->
<!--       processEscapes: true -->
<!--     } -->
<!--   }); -->
<!-- MathJax.Hub.Config({ -->
<!--   TeX: { equationNumbers: { autoNumber: "AMS" } } -->
<!-- }); -->
<!-- </script> -->
<!--  -->
<!-- <script type="text/javascript" -->
<!--     src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"> -->
<!-- </script> -->
<!--  -->
<!-- [//]: <> (A rotina acima deve ser incluida no inicio do texto em markdown p/ que ele reconheca os simbolos $ $ para formulas inline) -->
<!--   -->
 <style type="text/css">
.centerImage
{
 text-align:center;
 display:block;
}
</style>
 
# Lecture Notes

## terça, 11. junho 2019 04:03 
---

### The adjoint method 
Let $x\in\mathbb{R}^{n_x}, p\in\mathbb{R}^{n_p}$, a measure of merit $f(x,p):\mathbb{R}^{n_x}\times\mathbb{R}^{n_p}\to\mathbb{R}$ and the relationship $g(x,p)=0$ for a function $g:\mathbb{R}^{n_x}\times\mathbb{R}^{n_p}\to\mathbb{R}^{n_x}$ nonsingular in everywhere.
First
\begin{align}
d_pf &= d_pf(x(p)) = \partial_xfd_px \label{df}
\end{align}

second, 
\begin{align}
g(x,p) = 0 \Rightarrow d_pg =0 \nonumber
\end{align}
only because $g =0$ everywhere. Now, expanding the total derivative
\begin{align}
g_xd_px+g_p &=0 \Rightarrow d_px = -g_x^{-1}g_p \nonumber 
\end{align}
Substituting $d_px$ in $\eqref{df}$ 

\begin{align}
d_pf &= \underset{=\lambda}{\underbrace{-\partial_xfg_x^{-1}}}g_p \nonumber
\end{align}

The term $-\partial_xfg_x^{-1}$ is a row vector times a $n_x\times n_p$ matrix and will be understood as the solution to the linear equation 

\begin{align}
-\partial_x f g_x^{-1} &= \lambda \nonumber
\end{align}
thus, 

\begin{align}
g_x^{\mathsf{T}} \lambda &= -\partial_x f \nonumber
\end{align}

**In terms of $\lambda$ Eq. $\eqref{df}$ turns to, $d_p f = \lambda^{\mathsf{T}}g_p$.**

---

Another derivation is useful. Define the *Lagrangian*

\begin{align}
\mathcal{L}(x,p,\lambda) &= f(x) + \lambda^{\mathsf{T}}g_p
\end{align}
 
<!---
<center>
<img src="./test.png" alt="drawing" width="450px" />
</center>
--->
