# Note for LaTex

Any comment would be welcome!

## Tools

- [Overleaf](https://www.overleaf.com/)
  - editor, LaTex environment, remote repository
- GitHub
  - remote repository, backup storage
- Dropbox
  - local repository, backup storage
- matplolib
- [Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/index.html)
- Inkscape
  - plot and log

## Overleaf

- editor, remote storage, pdf compiler
  - all complete on web browser, like Chrome
- not necessary to prepare LaTex environment!
- able to connect to GitHub directly
  - `git pull` from GitHub repository directly
  - `git commit` and `git push` to GitHub repository directly
- see more: [Overleaf](https://www.overleaf.com/)

## LaTex packages

- graphicx
  - for figure
- cite
  - for bibtex
- amsmath
  - for math equation
- setspace
  - for double spacing
- siunitx
  - for si unit
- bm
  - for bold style vector

### For Japanese

- jsarticle
- inputenc
- pxchfon

## figure (plot)

1. prepare csv file to plot
1. use Jupyter notebook and matplotlib.pyplot
1. save plot in **svg**
1. use Inkscape for minor modifications
1. save svg and **pdf**

- `\newcommand{\figwidth}{width}`
  - for set figure width like `\includegraphics[width=\figwidth]{fig.pdf}`
- useful reference
  - [GUIDE TO PREPARING FIGURES FOR SCIENCE RESEARCH JOURNALS](http://www.sciencemag.org/sites/default/files/Figure_prep_guide.pdf)

### why pdf?

- see: [graphics \- Which figure type to use: pdf or eps? \- TeX \- LaTeX Stack Exchange](https://tex.stackexchange.com/questions/2092/which-figure-type-to-use-pdf-or-eps)

### Inkscape

1. open svg written by pyplot
1. create **layer**
1. add and modification
1. save layer \*.tar and **pdf**

- tar for reuse added layer

- after save pdf, run below code in Jupyter to extract \*.tar

```Jupyter
name="filename"
!mkdir {name}_layer
!tar -xf {name}.tar -C {name}_layer
```

## Equation

- Multiple line equation
  - amsmath package
  - ref: [Show equation number only once in align environment \- TeX \- LaTeX Stack Exchange](https://tex.stackexchange.com/questions/17528/show-equation-number-only-once-in-align-environment)

```latex
\begin{align}
    \begin{split}
        a &= b \\
        &=c \\
    \end{split}
\end{align}
```

- use `~`, non-breaking space for reference
  - e.g. `Fig.~\ref{fig:figure.pdf}`
  - [LaTeX/Labels and Cross\-referencing \- Wikibooks, open books for an open world](https://en.wikibooks.org/wiki/LaTeX/Labels_and_Cross-referencing)
- use `\bm` for bold style vector like $\bm{a}$
  - [math mode \- Bold italic vectors \- TeX \- LaTeX Stack Exchange](https://tex.stackexchange.com/questions/14395/bold-italic-vectors)

## [Vega\-Lite](https://vega.github.io/vega-lite-v1/)
- Good :)
    - All information necessary to plot is in *json*
        - data, property, and so on 
    - [Online vega-lite editor](https://vega.github.io/editor/#/examples/vega-lite/bar) 
    - python wrapper: [altair](https://altair-viz.github.io/)
- Bad :(
    - plotting multiple line is troublesome