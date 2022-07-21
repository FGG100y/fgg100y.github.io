---
layout: post
title: "Jupyterlab for DS"
subtitle: "Python, R, and Julia kernels set up"
background: '/img/posts/01.jpg'
---

# New machine && DS working space

JuPyteR: Julia + Python + R all in jupyterlab

1. check the Python came with system
```sh
$ which python3
```
If there is no python3 yet, install one:
```sh
$ sudo apt install python3
```
Note that this would install the latest version of Python.

2. Poetry or Virtualenv (Poetry is way tooooo slow 2021-12)
```sh
# create virtual envs:
python3 -m venv dsvenv
# install jupyterlab:
./dsvenv/bin/python -m pip install jupyterlab
```
Note that this may create a dsvenv without `activate` !
If this is the case, using this instead: [more here](https://stackoverflow.com/questions/26215790/venv-doesnt-create-activate-script-python3)
```sh
python3 -m venv --without-pip dsvenv
```
3. [install R](https://mirrors.tuna.tsinghua.edu.cn/CRAN/), then
    3.1 Enter interactive R (REPL environment)
    ```R
    install.packages('IRkernel')
    ```
4. [install Julia](https://julialang.org/downloads/platform/#linux_and_freebsd)

5. activate dsvenv (source ./dsvenv/bin/activate), then
    5.1 Enter interactive R (REPL environment)
    ```R
    install.packages('IRkernel')
    # to register the kernel in the current R installation
    IRkernel::installspec()
    ```
    5.2 Enter interactive Julia (./path-to/julia.1.6.5/bin/julia)
    ```Julia
    # entry pkg mode:
    ]
    add IJulia
    # exit pkg mode:
    Ctrl-c or <backspace>
    ```
6. launch jupyterlab server, and that's it!
