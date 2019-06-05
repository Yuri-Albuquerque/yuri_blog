---
layout: default
---
# First things First!

<p align="center">
  <img src="images/books.jpg" width="280" height="200" />
</p>

Hello! I am PHD candidate in Applied Math and I'd like to share some of my work. So 
Not everything I've published here is exactly my own work. Many things are progress from other researchers and papers that I am interested in.
English language is not my native language so may I have committed several mistakes while writing here. 
Feel free to send me an email, if you see something strangely written! Please!

Anyway, I hope you like the texts!

---
## The only abstract math is the one you didn't understand yet.

In this article, one can introduce to the reader a new and useful method for computing electromagnetic \\(EM\\) responses of arbitrary conductivity distributions in the earth. I worked with this methods in my masters degree, and this allowed me to understand deeply some fields of study like physical-mathematics, numerical analysis and functional analysis.

#### EM-Field imaging methods

 The diffusive \\(EM\\) field is known to have a unique integral representation in terms of a fictitious wave field that satisfies a wave equation. One can show that this integral transform can be extended to include vector fields. The algorithm that I presented in my master's degree takes advantage of the relationship between the wave field and the actual \\(EM\\) field. Specifically, numerical computation is carried out for the wave field, and the result is transformed back to the \\(EM\\) field in the time domain.

The proposed approach has been successfully demonstrated using two-dimensional \\(2-D\\) models. The appropriate \\(TE\\)-mode diffusion equation in the time domain for the electric field is initially transformed into a scalar wave equation in an imaginary \\(q\\) domain, which is a time-like variable. The corresponding scalar wave field is computed numerically using an explicit \\(q\\)-stepping technique. Standard finite-difference methods are used to approximate the fields, and absorbing boundary conditions are implemented. The computed wave field is then transformed back to the time domain. The result agrees fairly well with the solution computed directly in the time domain.


The video bellow is an instance of how electromagnetic data are collected in the seabed.

<p align="center">
  <iframe width="280" height="200" src="https://www.youtube.com/embed/VBdzzYzJePM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</p>

 In this approach, Maxwell’s equations in the time domain are first transformed into a system of coupled first- order wave equations in the \\(q\\) domain.These coupled equations are slightly modified and then cast  equations that numerical schemes developed for solving wave equations can be applied efficiently.

##### How it works

 After mapping the resistivity characteristics of the medium and collecting the data of the electromagnetic resistivity, one can calculate the relation between the \\(EM \\) - field and wave and use finite differences to calculate the responses of artificial waves with collected resistivity data. Getting the image of substructures in layers of the earth.

For instance, observe the prototype bellow.

<p align="center">
  <img src="images/onda.gif" width="280" height="200" />
</p>

This image shows a circular cylinder of electrical conductivity \\(\sigma  = 0.4(\Omega m)^{-1}\\) immersed in a medium of electrical conductivity \\(\sigma = 0.1(\Omega m)^{-1}\\). The adopted model have a variation in the \\(x\\) position of ́\\(0 m\\) to  \\(500 m\\) and depth at the \\(z\\) position of \\(0 m\\) to \\(500 m\\). A circular cylinder centered at point \\(x = 250 m\\) and \\(z = 170 m\\), and the source of the pulse is located at \\((250 m, 0 m)\\).

[show me the math!](https://yuri-albuquerque.github.io/yuri_blog/EW)
