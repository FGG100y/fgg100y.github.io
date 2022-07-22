---
layout: post
title: "Jupyterlab & Kernels"
subtitle: "Julia, Python and R kernels in jupyterlab"
background: '/img/posts/jupyter_kernels/jupyter_kernels.png'
---

New machine needs to be tailored for a better personal workflow. And this is
about how [jupyter](https://jupyter.org/) can be a multi-language support
co-work platform for regular DataScience works. Also note that Julia community
has [pluto](https://github.com/fonsp/Pluto.jl) notebook, and R has its
[RStudio](https://www.rstudio.com/).

# JuPyteR: Julia + Python + R all in one

1 check the Python came with system

```sh
$ which python3
```

If there is no python3 yet, install one:

```sh
$ sudo apt install python3
```

Note that this would install the latest version of Python.

2 Poetry or Virtualenv (Poetry is way tooooo slow 2021-12)

```sh
# create virtual envs:
python3 -m venv dsvenv
# install jupyterlab:
./dsvenv/bin/python -m pip install jupyterlab
```

Note that this may create a venv without `activate` scripts.
If this is the case, check [more discussion
here](https://stackoverflow.com/questions/26215790/venv-doesnt-create-activate-script-python3)

3 [install R](https://mirrors.tuna.tsinghua.edu.cn/CRAN/), then

4 [install Julia](https://julialang.org/downloads/platform/#linux_and_freebsd)

5 activate python's dsvenv (source ./dsvenv/bin/activate), then

a. Enter interactive R (REPL environment)

```R
# install 'IRkernel'
install.packages('IRkernel')
# register the kernel in the current R installation
IRkernel::installspec()
# exit
q()
```

b. Enter interactive Julia (./path-to/julia.1.6.5/bin/julia)

```Julia
# entry pkg mode:
]
add IJulia
# exit pkg mode:
Ctrl-c or <backspace>
```

6 launch jupyterlab server, and that's it!
