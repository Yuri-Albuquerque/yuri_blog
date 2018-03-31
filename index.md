---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---
# First things First!

Hello! I am a professional mathematician and I like to share what I am discovering. So I hope this blog helps to understand and divulge my discoveries. Not everything I've published here is exactly my own work. Many things are disclosures from other researchers and papers that I am interested in.

The English language is not my native language so I may have committed several gaffes while writing here. Feel free to email me if you see something strangely written! Please!

In addition, I hope you like the texts released!

---
# EM-Field imaging methods

We introduce a new and useful method for computing electromagnetic \(EM\) responses of arbitrary conductivity distributions in the earth. The diffusive \(EM\) field is known to have a unique integral representation in terms of a fictitious wave field that satisfies a wave equation. We show that this integral transform can be extended to include vector fields. Our algorithm takes advantage of this relationship between the wave field and the actual EM field. Specifically, numerical computation is carried out for the wave field, and the result is transformed back to the \(EM\) field in the time domain.

The proposed approach has been successfully demonstrated using two-dimensional \(2-D\) models. The appropriate TE-mode diffusion equation in the time domain for the electric field is initially transformed into a scalar wave equation in an imaginary q domain, where q is a time-like variable. The corresponding scalar wave field is computed numerically using an explicit q-stepping technique. Standard finite-difference methods are used to approximate the fields, and absorbing boundary conditions are implemented.

<iframe width="440" height="390" src="https://www.youtube.com/embed/VBdzzYzJePM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

The computed wave field is then transformed back to the time domain. The result agrees fairly well with the solution computed directly in the time domain. In this approach, Maxwell’s equations in the time domain are first transformed into a system of coupled first- order wave equations in the \(q\) domain.These coupled equations are slightly modified and then cast into a "symmetric" and "divergence-free" form. We show that it is to this particular form of equations that numerical schemes developed for solving wave equations can be applied efficiently.

$\delta_s = \sqrt{\frac{2}{\omega\mu\sigma}}$
