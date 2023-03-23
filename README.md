# Minithesis
A small thesis template and makefile.

This requires some standard latex software to be installed in your environment.
I don't recall which exact packages are needed, so I wish you the best of luck.

## Layout
Begin in `main.tex`; this is the core latex file from which you can follow
the imports to all others.

Component tex files are in `main/`.

Figures are in `figures/`.

The bibliography file is `bib.bib`.


## Build
Your thesis comes in several versions for different purposes:
- `main.pdf` is a draft without figures.
Build it with `make main.pdf`, or just `make`.
- `main.hard.pdf` is the hard-bound version.
Build it with `make main.hard.pdf`.
- `main.soft.pdf` is the soft-bound version.
Build it with `make main.hard.pdf`.

To build all three in parallel, use `make all -j`.

Building the thesis produces many additional files, which we place into a
directory named `scratch/`.

When you get cryptic errors, inspect the log files named
`scratch/main*.log`; search these log files for 'error'-like keywords.

The build scripts in `Makefile` are tuned to minimize output noise and build
time.
For particularly stubborn bugs, consider using a standard `pdflatex` build
that pipes less output to `/dev/null`.


### Clean-up

Use `make clean` to remove stuff after builds.


### Latexdiff
Latexdiff is a pain.
See the comments in `Makefile` for a template that points it to diff against
a previous version of your thesis, which should exist in a different directory.
