---
draft: true
title: Newtonian Mechanics for A' Level
tags:  [ 'a-level', 'maths', 'physics' ]
---

## Introduction

In these notes we are going to explain clearly how to, _in principle_, solve any mechanics problem posed. The aim is to _demystify_ the process; very often we are confronted with problems and have no idea what to do, especially if the problem is of an unfamiliar sort. This method is informed by Newton's laws: as should any method. Here are the laws:

1. A particle moves at constant velocity if and only if the net force acting on it is zero.
2. If \\(F\\) is the total force exerted on a particle, \\(m\\) is the mass of the particle, and \\(x:\mathbb{R}\to\mathbb{R}^3\\) is the position function of the particle, then

\\[ F = m\ddot{x} \\]
3. If a particle \\(A\\) exerts a force \\(F_{AB}\\) on a particle \\(B\\) then particle \\(B\\) exerts a force \\(F_{BA} = -F_{AB}\\) on particle \\(A\\).

We will then see that any mechanics problem can be boiled down to a system of ODEs. The question is is then "can you solve this system of ODEs?" For any A' level problem, you should be able to solve the ODEs.

## The Method

Now, we outline the method:

1. Draw a diagram, including all particles and forces.
2. Choose  reference frame.
3. For each particle, write down Newton's second law for it. Since associated to each particle we have an ODE, completing this step will give you a system of ODEs.
4. Solve the system.
