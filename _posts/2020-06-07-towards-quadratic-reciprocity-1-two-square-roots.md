---
layout: post
title: Towards Quadratic Reciprocity
subtitle: Part 1 - Two Square Roots
tags: [maths,number-theory]
---
*(NB: This post was uploaded well after the exam, as these count as my own notes and wished to use them for the open book exam.)*

I have a number theory exam coming up, and I really need to understand the famous Law of Quadratic Reciprocity. In the following series of blogposts, I will outline a proof of this Law, beginning with the Two Square Roots Lemma, then moving on to Euler's Criterion (which we derive as a corollary of a more general theorem), after which we shall prove Gauss' Lemma (one of his many...), and then finally arrive at the Law.

The approach is based on lectures by Adam Harper, but I have reworded many things to suit my own taste of exposition.

Prerequisites include some very basic group and ring theory: the reader should be familiar with what an integral domain is, and should also be familiar with properties of groups like \\(\mathbb{Z}/p\mathbb{Z}\\) and \\((\mathbb{Z}/p\mathbb{Z})^{\times}\\).

**Lemma (Two Square Roots):** Let \\(p\\) be an odd prime. Then for any \\(a\in\mathbb{Z}\\) coprime to \\(p\\), the number of \\(x\in(\mathbb{Z}/p\mathbb{Z})^{\times}\\) such that \\(x^2\equiv_p a\\) is either \\(2\\) or \\(0\\).

*Proof:* Firstly, suppose that \\(x_1\\) and \\(x_2\\) solve \\(x^2\equiv_p a\\). Then \\(x_1^2 - x_2^2 \equiv_p 0\\), so \\((x_1-x_2)(x_1+x_2)\equiv_p0\\). Now since \\(\mathbb{Z}/p\mathbb{Z}\\) is an integral domain, we have that \\(x_1-x_2\equiv_p0\\) or \\(x_1+x_2\equiv_p0\\). So \\(x_1\equiv_p\pm x_2\\).

Secondly, suppose that \\(x_1\\) solves the same equation. Then \\(-x_1\\) also solves that equation. Since \\(p\\) is odd, \\(x_1\not\equiv_p-x_1\\). So if the equation has a solution, then it has exactly two solutions.

Therefore, either \\(x^2\equiv_p a\\) has no solutions, or it has at least one solution, in which case it has exactly two solutions. QED.

**Corollary:** There are precisely \\((p-1)/2\\) elements of \\((\mathbb{Z}/p\mathbb{Z})^{\times}\\) that are quadratic residues modulo \\(p\\), and precisely the same number that are not.

*Proof:* By the Two Square-Roots Lemma, for every \\(x\in(\mathbb{Z}/p\mathbb{Z})^{\times}\\), the equation \\(y^2\equiv_p x^2\\) has exactly two solutions: \\(y\equiv_px\\) and \\(y\equiv_p-x\\). So every element in \\((\mathbb{Z}/p\mathbb{Z})^{\times}\\) has a matching element which uniquely give rise to the same square. So there are \\(\\#(\mathbb{Z}/p\mathbb{Z})^{\times}/2 = (p-1)/2\\) pairs, so there are the same number of squares (i.e. quadratic residues) modulo \\(p\\). Therefore there are the same number of elements that are *not* squares (i.e. quadratic *non*-residues) modulo \\(p\\). QED.