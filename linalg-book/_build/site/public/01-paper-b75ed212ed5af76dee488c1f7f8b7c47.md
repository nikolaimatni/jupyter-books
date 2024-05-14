---
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

## Different kinds of environments

Key to pleasant to read and easy to follow notes are different kinds of environments.  These can be used to focus student's attention on key results or definitions, warn about pitfalls, include worked examples, etc.  We show a few different options below.  First, we can highlight important facts with a _quote_ environment:

> Mitochondria are the powerhouse of the cell

If we want to make something even more eye-catching, we can try a _pull-quote_:

:::{pull-quote}
Linear algebra is the powerhouse of modern science and engineering.
:::

Of course, quotes are nice, but sometimes, we really want a box and some color.  For example, here's a tip:

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

:::{danger}
Dividing by zero can get you into some serious trouble, just ask this guy:
```{image} divide_by_zero.png
:alt: He divided by zero
:width: 500px
:align: inline
```
:::

[2i2c]: https://2i2c.org/
[curvenote]: https://curvenote.com
[docutils]: https://docutils.sourceforge.io/
[executablebooks]: https://executablebooks.org/
[jupyterbook]: https://jupyterbook.org/
[jupyterlab-myst]: https://github.com/executablebooks/jupyterlab-myst
[sphinx]: https://www.sphinx-doc.org/
