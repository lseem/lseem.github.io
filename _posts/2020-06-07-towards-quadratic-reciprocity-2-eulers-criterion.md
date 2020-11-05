---
layout: post
title: Towards Quadratic Reciprocity
subtitle: Part 2 - Euler's Criterion 
tags: [maths,number-theory]
---

In this blog post, we continue where we left off in order to derive Euler's Criterion. First, we define some key terms that will be important to us.

**Definition (quadratic residue):** Let \\(m\in\mathbb{N}\\), and let \\(a\in\mathbb{Z}\\) be coprime to \\(m\\). We say that \\(a\\) is a quadratic residue modulo \\(m\\) if there exists \\(x\in\mathbb{Z}\\) such that \\(x^2\equiv_m a\\). We say that \\(a\\) is a quadratic non-residue modulo \\(m\\) if there does not exist any such \\(x\\).

**Definition (Legendre symbol):** Let \\(p\\) be an odd prime, and let \\(a\in\mathbb{Z}\\). Then the Legendre symbol is defined as
\\[ \begin{pmatrix}a\\\p\end{pmatrix} := \begin{cases}
    0 & \text{if } p|a \\\
    1 & \text{if } a \text{ is a quadratic residue modulo }p \\\
    -1 & \text{if }a \text{ is a quadratic non-residue modulo }p. \end{cases} \\]

**Theorem 1:** Let \\(p\\) be an odd prime. Then for any \\(a\in\mathbb{Z}\\) that is coprime to \\(p\\), we have
\\[ -\begin{pmatrix} a \\\ p \end{pmatrix} a^{(p-1)/2} \equiv_p (p-1)!. \\]

*Proof:* Suppose first that \\(a\\) is a quadratic non-residue modulo \\(p\\). Then
\\[ (p-1)! \equiv_p a\cdot\prod_{j\in(\mathbb{Z}/p\mathbb{Z})^{\times}\setminus\\{1,a\\}}j. \\]
Now, since \\((\mathbb{Z}/p\mathbb{Z})^{\times}\\) is a group, for each \\(j\\) in the above product there is a unique element \\(y\\) in the product such that \\(jy\equiv_p a\\). So we match these elements up with each other to obtain \\((p-1)/2\\) pairs whose product is \\(a\\), giving
\\[ (p-1)! \equiv_p a\cdot a^{(p-3)/2} \equiv_p a^{(p-1)/2} \equiv_p - \begin{pmatrix} a \\\ p \end{pmatrix} a^{(p-1)/2}. \\]

Now suppose that \\(a\\) is a quadratic residue modulo \\(p\\), so that \\(a\equiv_p x^2\\) for some \\(x\in(\mathbb{Z}/p\mathbb{Z})^{\times}\\). Since \\(p\\) is odd, \\(x\not\equiv_pp-x\\), and so \\(x(p-x)\equiv_p-x^2\equiv_pa\\). Therefore,
\\[ (p-1)! \equiv_p -a\cdot\prod_{j\in(\mathbb{Z}/p\mathbb{Z})^{\times}\setminus\\{x,p-x\\}}j. \\]
Similarly to the first case, since \\((\mathbb{Z}/p\mathbb{Z})^{\times}\\) is a group, for each \\(j\\) in the above product there is a unique element \\(y\\) in the product such that \\(jy\equiv_p a\\). So we match these elements up with each other to obtain \\((p-1)/2\\) pairs whose product is \\(a\\), giving
\\[ (p-1)! \equiv_p -a\cdot a^{(p-3)/2} \equiv_p -a^{(p-1)/2} \equiv_p -\begin{pmatrix} a \\\ p \end{pmatrix} a^{(p-1)/2}. \\]
QED.

**Corollary (Wilson's Theorem):** If \\(p\\) is prime, then \\((p-1)!\equiv_p -1\\). If \\(m\geq6\\) is composite, then \\((m-1)!\equiv_m0\\).

*Proof:* If \\(p\\) is prime, then take \\(a=1\\) in Theorem 1, and the result follows.

So let \\(m\geq6\\) be composite. Then \\(m=ab\\) for some \\(a,b\in\mathbb{Z}\\). Then noticing that
\\[ a+b = a+\frac{m}{a} \leq 2 + \frac{m}{2} \leq m-1, \\]
we break the product up:
\\[ (m-1)! = \prod_{j=1}^aj\cdot\prod_{k=a+1}^{a+b}k\cdot\prod_{l=a+b+1}^{m-1}l, \\]
whence we deduce that, since \\(a\\) divides the first product and \\(b\\) divides the second product, the whole product is divisible by \\(ab=m\\), and so
\\[ (m-1)! \equiv_m 0.\\]
QED.

**Corollary (Euler's Criterion):** Let \\(p\\) be an odd prime and let \\(a\in\mathbb{Z}\\) be coprime to \\(p\\). Then
\\[ \begin{pmatrix}a\\\ p\end{pmatrix}\equiv_p a^{(p-1)/2}. \\]
*Proof:* By Wilson's Theorem \\((p-1)!\equiv_p -1\\). So by Theorem 1, 
\\[ -1 \equiv_p (p-1)! \equiv_p -\begin{pmatrix}a\\\p\end{pmatrix}a^{(p-1)/2}, \\]
therefore
\\[ a^{(p-1)/2} \equiv_p \left[1\middle/ \begin{pmatrix}a\\\p\end{pmatrix}\right] \equiv_p \begin{pmatrix}a\\\p\end{pmatrix}.\\]
QED.
