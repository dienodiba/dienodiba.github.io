---
layout: archive
title: ""
permalink: /FITE2DMT/
author_profile: true
---

{% include base_path %}

<!-- {% for post in site.teaching reversed %}
  {% include archive-single.html %}
{% endfor %} -->

<img src="/images/FITE2DMTbanner.jpg" style="width:100%">

# A fast and accurate 2-D magnetotelluric inversion code
FITE2DMT stands for _FInite Triangular Elements for Two-Dimensional MagnetoTelluric_. As the name suggests, it is a two-dimensional (2-D) finite element magnetotelluric (MT) inversion code that uses an unstructured mesh of triangular elements to represent the resistivity structure. The code is developed in Julia and freely available for use as a Julia package.

## What are the benefits of using an unstructured mesh in MT inversion?
Using an unstructured mesh in 2-D MT inversion has some great benefits. It lets you refine the mesh where the geology is complex, which means more accurate results without bogging down your computations. Plus, it’s flexible enough to handle tricky geological features like faults and varying topographies. This means the inversion can better capture the real subsurface details. On top of that, unstructured meshes help optimize your computational resources by reducing the number of elements needed, making the process more efficient and precise.

## Why [Julia](https://julialang.org/){:target="_blank"}?
Julia has a lot of upsides when it comes to MT inversion. It is super fast and handles complex calculations efficiently. Its syntax is pretty user-friendly and a lot like Python’s or MATLAB's, but it is as speedy as C or Fortran. This makes it great for creating complicated inversion algorithms. Plus, Julia has a ton of libraries for scientific computing, including stuff for linear algebra and parallel processing, which are crucial for MT inversion. It also integrates well with other tools and libraries, making it flexible and easy to scale up the code.

## What type of datasets are compatible with FITE2DMT?
Apparent resistivity, phase, and _tipper_

## What functionalities are in FITE2DMT?
- Node-based finite element formulation for triangular element
- Regularized least-squares objective function
- Data-space Gauss-Newton minimization algorithm
- Reciprocity method for assembling the sensitivity matrix

For more please check out the original documentation of FITE2DMT here:

Diba D, Nurhasan, Uyeshima M, Usui Y (2024) Two-dimensional magnetotelluric inversion using unstructured triangular mesh implemented in Julia. Journal of Physics: Conference Series, **2734** 012008. [doi.org/10.1088/1742-6596/2734/1/012008](https://doi.org/10.1088/1742-6596/2734/1/012008){:target="_blank"}.

## Considering trying out FITE2DMT?
Awesome! FITE2DMT is free and you can get it as a Julia package from [my Github page](https://github.com/dienodiba/Fite2dmt.jl){:target="_blank"}. Just remember to cite the original documentation if you use it in your work—it's a great way to give credit and support future updates.
