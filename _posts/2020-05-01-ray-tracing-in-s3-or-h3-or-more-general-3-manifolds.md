---
layout: post
title: Ray Tracing in \(S^3\) or \(H^3\) (or more general 3-Manifolds?)
tags: [maths, coding]
---

I have a project in mind, and this project is to write a ray tracer for non-Euclidean geometries. While ultimately I am looking for full generality and would like to ray trace on any sufficiently regular 3-manifold, I will modestly set my first thousand-mile stone to ray tracing in the 3-sphere or in hyperbolic 3-space.

This project is mainly inspired by the film _Interstellar_, whose visual effects production studio [Double Negative](https://dneg.com) wrote a renderer in order to render the black hole in the film. This renderer, the _Double Negative Gravitational Renderer_, was written in collaboration with Kip Thorne with the intention to essentially "simulate" general relativity so that the viewer would see such effects as gravitational lensing.

So here's the plan of action.

1. I'm going to write this ray tracer in [rust](https://rust-lang.org) because I am not a good programmer and so am not to be trusted with such dangerous tools as C/C++. I'm first going to write this ray tracer for the CPU, and then I'm going to modify it so that it works on the GPU instead for performance benefits.
 
2. I'm going to write one for Euclidean 3-space first. I will include my own way of dealing with linear algebra, and make sure that stuff works in the standard way.

3. Depending on which seems easier, I will modify this Euclidean ray tracer to either ray trace in \\(S^3\\) or in \\(H^3\\).

In order to ray trace in \\(H^3\\) it may be that all I will have to do will be to change from ordinary linear algebra to Lorentzian linear algebra. But on the other hand, \\(S^3\\) can be modelled as a subset of \\(\mathbb{R}^4\\) rather easily and so it could be that this is actually easier. One could also unify these approaches by having a radius parameter that ranges over \\(\mathbb{C}\\), so that we have \\(S^3\\) when the radius is \\(1\\), and \\(H^3\\) when the radius is \\(i\\). Either way, we shall see.

Something to note is that there has been some research done into this already. From what I could find, there has been already some research done at the [Vision and Graphics Laboratory](https://www.visgraf.impa.br/home/) at IMPA in Brazil. A couple of useful papers are
* Luiz Velho, Vinicius da Silva, and Tiago Novello. **"Immersive Visualization of the Classical Non-Euclidean Spaces using Real-Time Ray Tracing in VR"**. In Proceedings of the 46th Graphics Interface, 2020. [pdf](https://www.visgraf.impa.br/Data/RefBib/PS_PDF/gi2020/gi2020.pdf)
* Tiago Novello, Vinicius da Silva, and Luiz Velho. **"Global Illumination of Non-Euclidean Spaces"**. Technical Report TR-06-2020, VISGRAF Lab - IMPA, 2020. [pdf](https://www.visgraf.impa.br/Data/RefBib/PS_PDF/tr-06-2020/tr-06-2020.pdf)

Another cautionary note is that a lot people on youtube who claim to have non-Euclidean ray tracers are actually just using portals and the such like. My project aims to accurately simulate the diffeo-geometric phenomena of ray tracing in curved 3-manifolds. For example, in \\(S^3\\), if you look in front of you, assuming that the light doesn't dim etc, then you should see your back, flipped horizontally and vertically. I want this to fall naturally out of the ray tracing mechanism, I don't want it to be some sort of contrived portal system.