# Generating Slides

The [slides](https://cambridge-iccs.github.io/Summer-school-Intro-Git) used to teach this course are generated using [quarto](https://quarto.org).

To be able to generate those yourself from quarto's source files (those with extension `.qmd`) make sure you have `quarto` installed on your machine with `quarto --version`.
If not, [install quarto cli](https://quarto.org/docs/get-started/).

At this point, you can simply run
```shell
quarto render intro-git.qmd
```
which will output the slide deck (in `html` form) with a root file `index.html` along with auxiliary files located into a directory `intro-git_files`. 

You can now view the deck in your browser by opening `index.html`.