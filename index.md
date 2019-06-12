---
layout: default
---
# First Things First!

<p align="center">
  <img src="images/books.jpg" width="280" height="200" />
</p>

Hello! I am PHD candidate in Applied Math and I'd like to share some of my work. So 
Not everything I've published here is exactly my own work. Many things are progress from other researchers and papers that I am interested in.
English language is not my native language so may I have committed several mistakes while writing here. 
Feel free to send me an email, if you see something strangely written! Please!

Anyway, I hope you like the texts! :blush:

###### Please remember that the only abstract math is the one you didn't understand yet. 

---
## Imaging methods with Electromagnetic data through wave PDE
 
The diffusive \\(EM\\) field is known to have a unique integral representation in terms of a fictitious wave field that satisfies a wave equation PDE. One can show that this integral transform can be extended to include vector fields. The algorithm that I presented in my master's degree takes advantage of the relationship between the wave field and the actual \\(EM\\) field. Specifically, numerical computation is carried out for the wave field, and the result is transformed back to the \\(EM\\) field in the time domain.

The electric field \\(\mathbf{E}(\mathbf{r},t)\\) in a homogeneous media,  can be described through the equation 

\begin{align}\label{E}\nabla \times \nabla \times \mathbf{E}(\mathbf{r},t) + \mu\sigma(\mathbf{r})\frac{\partial }{\partial t}\mathbf{E}(\mathbf{r},t) &= -\mathbf{S}(\mathbf{r},t) \end{align}
\begin{align}\mathbf{E}(\mathbf{r},0) = 0,\qquad \mathbf{E}_{\Gamma} = \mathbf{E}(\mathbf{r}_b,t); & \quad t>0\end{align}  
where \\(\mathbf{r}\\) are the Cartesian coordinates, \\(\mu\\) is the magnetic permeability and \\(\sigma(\mathbf{r})\\) is the resistivity of the media. 

If we set the wave field \\(\mathbf{U}(\mathbf{r},q)\\) as a solution hyperbolic differential equation
\begin{align}\label{U}\frac{1}{\mathbf{c}^2(\mathbf{r},q)}\frac{\partial^2}{\partial q^2}\mathbf{U}(\mathbf{r},q)+\nabla \times \nabla \times \mathbf{U}(\mathbf{r},q) &= -\mathbf{F}(\mathbf{r},q)\end{align}
\begin{align}\mathbf{U}(\mathbf{r},0) &= 0\end{align}
\begin{align}\frac{\partial}{\partial q}\mathbf{U}(\mathbf{r},0) &= 0\end{align}
\begin{align}\mathbf{U}\Bigg|_{\Gamma} &= \mathbf{U}(\mathbf{r}_b,q); \quad q>0 \end{align}
where \\(\mathbf{c}(\mathbf{r},q) = \frac{1}{\sqrt{\mu\sigma(\mathbf{r})}}\\) and \\(q = \sqrt{t}\\) it is a time like variable.
And though it is not easy to obtain, but it is possible to achieve the following equivalence between these two fields,
\begin{equation}\label{equiv}\mathbf{E}(\mathbf{r},t) = \frac{1}{2\sqrt{\pi t^3}}\int_0^{\infty} qe^{-\frac{q^2}{4t}}\mathbf{U}(\mathbf{r},q)\;dq\end{equation}

The proposed approach has been successfully demonstrated using two-dimensional \\(2-D\\) models <a href="http://repositorio.unicamp.br/handle/REPOSIP/325361">[ALBUQUERQUE, Yuri Flores (2016)]</a>. The appropriate \\(TE\\)-mode diffusion equation in the time domain for the electric field is initially transformed into a scalar wave equation in an imaginary \\(q\\) domain, which is a time-like variable. The corresponding scalar wave field is computed numerically using an explicit \\(q\\)-stepping technique. Standard finite-difference methods are used to approximate the fields, and absorbing boundary conditions are implemented. The computed wave field is then transformed back to the time domain. The result agrees fairly well with the solution computed directly in the time domain.


The video bellow is an instance of how electromagnetic data are collected in the seabed.

<p align="center">
  <iframe width="280" height="200" src="https://www.youtube.com/embed/VBdzzYzJePM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</p>

 In this approach, Maxwell’s equations in the time domain are first transformed into a system of coupled first- order wave equations in the \\(q\\) domain.These coupled equations are slightly modified and then cast  equations that numerical schemes developed for solving wave equations can be applied efficiently.

##### How it works

 After mapping the resistivity characteristics of the medium and collecting the data of the electromagnetic resistivity, one can calculate the relation between the \\(EM \\) - field and wave and use finite differences to calculate the responses of artificial waves with collected resistivity data. Getting the image of substructures in layers of the earth.

See the prototype bellow.

<p align="center">
  <img src="images/onda.gif" width="280" height="200" />
</p>

This image shows a circular cylinder of electrical conductivity \\(\sigma  = 0.4(\Omega m)^{-1}\\) immersed in a medium of electrical conductivity \\(\sigma = 0.1(\Omega m)^{-1}\\). The adopted model have a variation in the \\(x\\) position of ́\\(0 m\\) to  \\(500 m\\) and depth at the \\(z\\) position of \\(0 m\\) to \\(500 m\\). A circular cylinder centered at point \\(x = 250 m\\) and \\(z = 170 m\\), and the source of the pulse is located at \\((250 m, 0 m)\\).

---
<h1 id='references'>References</h1>

<p>Albuquerque, Yuri Flores (2016), &#38;. <i>Electromagnetic Response of conductive media</i>. IMECC-Unicamp &#8217;Masters dissertation.</p>
---

## [The Adjoint Method](https://yuri-albuquerque.github.io/yuri_blog/theAdjointMethod)
