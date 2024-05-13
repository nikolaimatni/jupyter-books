---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.16.2
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

---
title: MyST Markdown Basics
subtitle: In JupyterLab
license: CC-BY-4.0
github: https://github.com/executablebooks/mystjs
subject: Tutorial
venue: MyST Markdown
biblio:
  volume: '1'
  issue: '42'
authors:
  - name: Rowan Cockett
    email: rowan@curvenote.com
    corresponding: true
    orcid: 0000-0002-7859-8394
    affiliations:
      - Curvenote
      - ExecutableBooks
date: 2023/07/05
math:
  '\dobs': '\mathbf{d}_\text{obs}'
  '\dpred': '\mathbf{d}_\text{pred}\left( #1 \right)'
  '\mref': '\mathbf{m}_\text{ref}'
abbreviations:
    MyST: Markedly Structured Text
---

+++

MyST is an ecosystem of open-source, community-driven tools designed to revolutionize scientific communication. MyST supports blogs, online books, scientific papers, reports and journals articles.

::::{important} Objective

The goal of this quickstart is to get you up and running in JupyterLab with MyST Markdown and provide an editable example of many of the features available in MyST Markdown.

For a full tutorial on MyST Markdown see the [MyST Markdown Guide](https://mystmd.org/guide/quickstart-myst-markdown) which provides more depth on syntax and pointers to other resources.
::::

+++

## Editing Markdown Cells

Working with markdown cells is exactly the same as normal in Jupyter, try taking a look at the source of this cell.

🛠 Double click to edit this cell, then type `Shift-Enter` to re-render the cell

:::{warning} Let's start with Callouts! 💬
:class: dropdown

This is a callout (or admonition) in MyST, there are a few variants available including `{note}`, `{important}`, and `{warning}`.
You can find the [full documentation for callouts here](https://mystmd.org/guide/admonitions).
:::

To change the style of the callout, try changing it to a `{note}`

🛠 Edit the callout in this cell to `{note}` instead of a `{tip}`

You can also add [directive options](https://mystmd.org/guide/syntax-overview#directives), with a `:class: dropdown` as the first line of the directive. Adding the dropdown class will turn this callout into a dropdown that is initially hidden, which is great for hiding solutions in JupyterLab for students, for example!

+++

## Figures & Cross References

MyST has support for figures, images and rich cross-references to preview the figures when you hover over a reference.

🛠 Double click the next cell to see the MyST `{figure}` syntax

+++

```{figure} https://source.unsplash.com/random/800x200?beach
:name: beach
:align: left
:width: 90%
Relaxing at the beach 🏖
```

+++

You can reference a figure with a markdown link to the name of the figure, for example, `[](#beach)`.

🛠 Hover the cross-references to the figures

In [](#beach) we can (hopefully) see someone enjoying the beach, and in [](#fruit) we can see fruit! These figures are also automatically numbered, and will update based on their position in the document.

🛠 Drag the markdown cell with fruit up to make it `Figure 1`

Both the caption number and all references to those cells will update instantly! ⚡️

+++


```{figure} https://source.unsplash.com/random/800x200?fruit
:name: fruit
:align: left
:width: 90%
A random picture of fruit 🍎🍊
```

+++

::::{seealso} See the MyST Markdown Documentation
:class: dropdown

:::{card} 📖 Images & Figures
:link: https://mystmd.org/guide/figures
MyST Markdown can be used to include images and figures in your documents as well as referencing those images easily throughout your website, article or paper.
:::

:::{card} 📖 Cross-References
:link: https://mystmd.org/guide/cross-references
References refer to labeled content (e.g. a figure, document or table) and automatically generates links and extra information, like numbering.
:::
::::

+++

## Equations

All of the standard markdown syntax for equations will also work with the MyST renderer. The easiest way to create math is to use the dollar-syntax, for example, for inline math:\
`$Ax=b_i$` will become $Ax=b_i$

+++

$$
\label{maxwell}
\begin{aligned}
\nabla \times \vec{e}+\frac{\partial \vec{b}}{\partial t}&=0 \\
\nabla \times \vec{h}-\vec{j}&=\vec{s}\_{e}
\end{aligned}
$$

+++

You can also now label and reference your equations, this is using a $\LaTeX$ style `\label{}` in the dollar-math block[^math-directives]:

🛠 Double click this cell to see the label syntax

$$
\label{cross}
\mathbf{u} \times \mathbf{v}=\left|\begin{array}{ll}u_{2} & u_{3} \\ v_{2} & v_{3}\end{array}\right| \mathbf{i}+\left|\begin{array}{ll}u_{3} & u_{1} \\ v_{3} & v_{1}\end{array}\right| \mathbf{j}+\left|\begin{array}{ll}u_{1} & u_{2} \\ v_{1} & v_{2}\end{array}\right| \mathbf{k}
$$

Similar to figures, you can link to the equation using a markdown link and they will be auto-labeled.

🛠 Hover the cross-references to the equation

> In [](#cross) you can see a cross-product or [Equation %s](#maxwell) is [Maxwell's equations](https://en.wikipedia.org/wiki/Maxwells_equations)

[^math-directives]: You can also use math as a "directive" -- see the [MyST docs on math](https://mystmd.org/guide/math#math-directives).

Similar to the figures, these equations are auto numbered.

🛠 Drag the markdown cell with Maxwell's equations up to make it Equation 1

+++

::::{seealso} See the MyST Markdown Documentation
:class: dropdown

:::{card} 📖 Math and equations
:link: https://mystmd.org/guide/math
There are several ways to make writing math in your documents as familiar as possible. Math can either be (1) inline or (2) displayed as an equation block. In addition to the usual MyST syntax, you can also use "dollar math", which is derived from LaTeX and surrounds inline math with single dollar signs (`$`), and equation blocks with two dollar signs (`$$`). 
:::

::::

+++

## External References

MyST Markdown creates _structured_ documents that are linked to other sources, which allows us to preview directly in the editing experience. 

---

You can link to any **Wikipedia** article and it will show a tooltip inline, for example, we linked to [Maxwell's equations](https://en.wikipedia.org/wiki/Maxwells_equations) above!

🛠 Using the short-hand `wiki:` link, add a link to a Wikipedia article

[](wiki:Geophysics)

---

You can also link to **GitHub** issues, pull requests and even code. Just paste the link in and MyST will provide a linked preview.

> For example, when we migrated to support JupyterLab 4.0, we did some work in [#142](https://github.com/executablebooks/jupyterlab-myst/pull/142). Some of the pipeline for MyST uses unifiedjs, and can be [seen here](https://github.com/executablebooks/jupyterlab-myst/blob/45155d53a69a02fb998db3b083dc396dc0ba57a9/src/myst.ts#L114-L124) as a series of plugins.

🛠 Follow the link to the code, copy a new permalink to a different line and paste it below!

+++

::::{seealso} See the MyST Markdown Documentation
:class: dropdown

:::{card} 📖 External References
:link: https://mystmd.org/guide/external-references
MyST Markdown allows you to connect your documents to external linked content like Wikipedia, which allow for hover-references with external content. External references are references to structured content or documents that are outside of your project.
:::

::::

+++

# Task Lists

Jupyter already can render tasks, but you can't edit them when you are working through something -- but you can in MyST!

🛠 Try editing a task below and see the markdown change

:::{important} Steps to revolutionize technical communication 🚀
- [x] Make tasklists work with JupyterLab
- [ ] Give an awesome webinar on very little sleep ☕️
- [ ] Create a community around MyST
- [ ] Probably other things 🤔
- [ ] Revolutionize technical communication
:::

+++

## Next Up

There are a few other nifty things that you can do with MyST Markdown below. You can also see all of the live demos in the documentation at <https://mystmd.org/guide>. That is it for this quickstart tutorial, next up we will take a look at actually using a bit of Jupyter with inline execuation and widgets!

:::{card} 🪐 Inline Execution
:link: ./03-inline-interactivity.ipynb
You can use the `{eval}` role to evaluate variables directly inside of your markdown cells, including widgets, sparklines and other variables.
:::

+++

## Diagrams

We have included a few other things in this notebook so that you can explore, for example mermaid diagrams!

```{mermaid}
flowchart LR
  A[Jupyter Notebook] --> C
  B[MyST Markdown] --> C
  C(mystmd) --> D{AST}
  D <--> E[LaTeX]
  E --> F[PDF]
  D --> G[Word]
  D --> H[React]
  D --> I[HTML]
  D <--> J[JATS]
```

+++

## Proofs

You can add an reference proofs ([](#weyls-criterion)). See the [docs](https://mystmd.org/guide/proofs-and-theorems).

:::{prf:criterion} Weyl's criterion
:label: weyls-criterion

Weyl's criterion states that the sequence $a_n$ is equidistributed modulo $1$ if
and only if for all non-zero integers $m$,

```{math}
\lim_{n \rightarrow \infty} \frac{1}{n} \sum_{j=1}^{n} \exp^{2 \pi i m a_j} = 0
```
:::

+++

## Solutions and Exercises

See the [docs](https://mystmd.org/guide/exercises)

```{exercise}
:label: my-exercise

Recall that $n!$ is read as "$n$ factorial" and defined as
$n! = n \times (n - 1) \times \cdots \times 2 \times 1$.

There are functions to compute this in various modules, but let's
write our own version as an exercise.

In particular, write a function `factorial` such that `factorial(n)` returns $n!$
for any positive integer $n$.
```

````{solution} my-exercise
:label: my-solution

Here's one solution.

```{code-block} python
def factorial(n):
    k = 1
    for i in range(n):
        k = k * (i + 1)
    return k

factorial(4)
```
````

+++

## Tabs, Grids, and Cards

See the [docs](https://mystmd.org/guide/dropdowns-cards-and-tabs)

````{tab-set}
```{tab-item} Tab 1
:sync: tab1
Tab one can sync (see below)!
```
```{tab-item} Tab 2
:sync: tab2
Tab two
```
````

These tabs are set to sync:

````{tab-set}
```{tab-item} Tab 1 - Sync!
:sync: tab1
Tab one can sync!
```
```{tab-item} Tab 2
:sync: tab2
Tab two
```
````


::::{grid} 1 1 2 3

:::{card}
:header: Text content ✏️
Structure books with text files and Jupyter Notebooks with minimal configuration.
:::

:::{grid-item-card}
:header: MyST Markdown ✨
Write MyST Markdown to create enriched documents with publication-quality features.
:::

:::{grid-item-card}
:header: Executable content 🔁
Execute notebook cells, store results, and insert outputs across pages.
:::
::::

:::{card}
:header: MyST Markdown 🚀
:link: https://mystmd.org
Write content in JupyterLab!
:::
