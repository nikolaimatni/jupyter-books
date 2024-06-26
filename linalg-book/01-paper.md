---
jupytext:
  text_representation:
    format_name: myst
kernelspec:
  display_name: Python 3
  name: python3
title: Sample notes in markdown
subject: Sample notes
subtitle: Let's show off some markdown functionality
short_title: Notes in markdown
authors:
  - name: Nikolai Matni
    affiliations:
      - Dept. of Electrical and Systems Engineering
      - University of Pennsylvania
    email: nmatni@seas.upenn.edu
license: CC-BY-4.0
keywords: sample notes, ese 2030, linear algebra
abstract: |
    We use this page to highlight the feature of using MyST to write lecture notes in markdown.  We have a companion page where we show how interactive code can be embedded, modified, and run from within your browser!
---

## Quotes and Admonitions

Key to pleasant to read and easy to follow notes are different kinds of environments.  These can be used to focus student's attention on key results or definitions, warn about pitfalls, include worked examples, etc.  We show a few different options below.  First, we can highlight important facts with a _quote_ environment:

> Mitochondria are the powerhouse of the cell

If we want to make something even more eye-catching, we can try a _pull-quote_:

:::{pull-quote}
Linear algebra is the powerhouse of modern science and engineering.
:::

Of course, quotes are nice, but sometimes, we really want a box and some color.  For example, here's a tip:

(apple)= 
:::{tip}
An apple a day keeps the doctor away!
:::


If something is important, we should make sure to highlight that too:
:::{important}
In linear algebra, _concepts_ and _computation_ are equally important.
:::

Of course, sometimes, we need to make sure students are aware of certain pitfalls, so we may want to warn them:

:::{warning}
This course can be challenging at times, but it is potentially the most wortwhile undergraduate math class you'll take.
:::

And in case of extreme risks, we should alert them of danger!
````{danger}
:name: divide-by-zero
Dividing by zero can get you into some serious trouble, just ask this guy:
```{image} divide_by_zero.png
:alt: He divided by zero
:width: 250px
:align: center
```
````

Of course, students can be forgetful, so we may need to remind them that they shoudl eat [an 🍎 a day](#apple)

## A sample worked example

Here's an example of how we might use these items to present a worked example, where we separate out the question, a hint, and a full solution.

````{exercise}  My first system of linear equations
:label: my-exercise
Find the solution to the following system of linear equations
\begin{eqnarray}
\label{eq:linsys}
x_1 - 2x_2 & = -1 \\
-x_1 + 3x_2 & = 3
\end{eqnarray}
:::{hint} Click me for a hint!
:class: dropdown
Try adding the two equations of [](#eq:linsys) together to eliminate $x_1$.[^note]

[^note]: By the way, did you try hovering over the equation number?
:::
```{solution} my-exercise
:class: dropdown
Adding the two equations of [](#eq:linsys) gives us that $x_2 = 2$, which we plug back into $x_1 - 2x_2 = -1$ to conclude that $x_1=3$.  We conclude that the system of linear equations [](#eq:linsys) has a unique solution $(3,2)$.
```
````

## Some more mathematical content

Here's just a taste of what we can do.

:::{prf:definition} Linear dependence
:label: def-lindep
A sequence of vectors $\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k$ from a vector space $\mathcal{V}$ is said to be _linearly dependent_, if there exist scalars $a_1, a_2, \dots, a_k,$ not all zero, such that
$$
\label{eq-lindep}
a_1\mathbf{v}_1 + a_2\mathbf{v}_2 + \cdots + a_k\mathbf{v}_k = \mathbf{0},
$$
where $\mathbf{0}$ denotes the zero vector.
:::

:::{prf:definition} Linear independence
:label: def-linindep
A sequence of vectors $\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k$ from a vector space $\mathcal{V}$ is said to be _linearly independent_, if they are not [linearly dependent](#def-lindep), i.e.,
$$
a_1\mathbf{v}_1 + a_2\mathbf{v}_2 + \cdots + a_k\mathbf{v}_k = \mathbf{0},
$$
only if $a_1=a_2=\cdots=a_k=0$.
:::

:::{prf:theorem} Unique coefficients
:label: thm-coeffs
Suppose a vector $\mathbf{x}$ is a combination of linearly independent vectors $\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k$:
$$
\label{rep1}
\mathbf{x}=a_1\mathbf{v}_1 + a_2\mathbf{v}_2 + \cdots + a_k\mathbf{v}_k.
$$
Then the coefficients $\{a_i\}_{i=1}^k$ are unique, i.e., if 
$$
\label{rep2}
\mathbf{x}=b_1\mathbf{v}_1 + b_2\mathbf{v}_2 + \cdots + b_k\mathbf{v}_k,
$$
then $a_i=b_i$ for $i=1,\dots,k$.
:::
:::{prf:proof} Proof of [](#thm-coeffs)
:label: prf-coeffs
:class: dropdown
Subtracting equation [](#rep2) from equation [](#rep1), we see that 
$$
(a_1-b_1)\mathbf{v}_1 + (a_2-b_2)\mathbf{v}_2 + \cdots + (a_k-b_k)\mathbf{v}_k=\mathbf 0.
$$
Since the vectors $\mathbf{v}_1, \mathbf{v}_2, \dots, \mathbf{v}_k$ are [linearly independent](#def-linindep) and the above sums to $\mathbf 0$, we must have that $a_i-b_i=0$ for $i=1,\dots,k$.
:::

## How about some executable code?
```{code-cell} python
hello = "hello"
there = "there"
phrase = f"{hello}, {there}!"
print(phrase)
```

```{code-cell} python
:tags: remove-input
print("This will show output with no input!")
```

[2i2c]: https://2i2c.org/
[curvenote]: https://curvenote.com
[docutils]: https://docutils.sourceforge.io/
[executablebooks]: https://executablebooks.org/
[jupyterbook]: https://jupyterbook.org/
[jupyterlab-myst]: https://github.com/executablebooks/jupyterlab-myst
[sphinx]: https://www.sphinx-doc.org/
