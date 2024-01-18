---
page-title: "JuliaLang/IJulia.jl: Julia kernel for Jupyter"
url: https://github.com/JuliaLang/IJulia.jl
date: 2024-01-17 22:55:03
tags:
  - sw/lang/julia
purpose:
  - kernel
up:
  - "[[Julia]]"
  - "[[Jupyter notebook]]"
---

[![IJulia logo](https://github.com/JuliaLang/IJulia.jl/raw/master/deps/ijulialogo.png)](https://github.com/JuliaLang/IJulia.jl/blob/master/deps/ijulialogo.png)

[![Build Status](https://camo.githubusercontent.com/f859ce00c2ba846e90f90c07f085db78c5dd21a50a57fc4191c07df5c3d9ca27/68747470733a2f2f6170692e7472617669732d63692e6f72672f4a756c69614c616e672f494a756c69612e6a6c2e737667)](https://travis-ci.org/JuliaLang/IJulia.jl) [![Build status](https://camo.githubusercontent.com/d9aeb96e8b03d407a562361bc3de6e24b86e0a410ad3b91bfbc9442d2235ace2/68747470733a2f2f63692e6170707665796f722e636f6d2f6170692f70726f6a656374732f7374617475732f616177383138796b70647563753675653f7376673d74727565)](https://ci.appveyor.com/project/StevenGJohnson/ijulia-jl) [![](https://camo.githubusercontent.com/ce182a0ee721b9f0d6200d4870f9f95d066b8909acc7ff51a706dfb03a9a3ff7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d737461626c652d626c75652e737667)](https://julialang.github.io/IJulia.jl/stable) [![](https://camo.githubusercontent.com/bffc6e1208bae5741460f92c0c744b1831e930cf143e6f65f55b3a5e44d27688/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d6c61746573742d626c75652e737667)](https://julialang.github.io/IJulia.jl/dev)

## IJulia

**IJulia** is a [Julia-language](http://julialang.org/) backend combined with the [Jupyter](http://jupyter.org/) interactive environment (also used by [IPython](http://ipython.org/)). This combination allows you to interact with the Julia language using Jupyter/IPython's powerful [graphical notebook](http://ipython.org/notebook.html), which combines code, formatted text, math, and multimedia in a single document. IJulia is a Jupyter language kernel and works with a variety of notebook user interfaces. In addition to the classic Jupyter Notebook, IJulia also works with [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/), a Jupyter-based integrated development environment for notebooks and code. The [nteract notebook desktop](https://nteract.io/) supports IJulia with detailed instructions for its [installation with nteract](https://nteract.io/kernels/julia).

(IJulia notebooks can also be re-used in other Julia code via the [NBInclude](https://github.com/stevengj/NBInclude.jl) package.)

## Quick start

Install IJulia from the Julia REPL by pressing `]` to enter pkg mode and entering:

If you already have Python/Jupyter installed on your machine, this process will also install a [kernel specification](https://jupyter-client.readthedocs.io/en/latest/kernels.html#kernelspecs) that tells Jupyter how to launch Julia. You can then launch the notebook server the usual way by running `jupyter notebook` in the terminal.

Alternatively, you can have IJulia create and manage its own Python/Jupyter installation. To do this, type the following in Julia, at the `julia>` prompt:

to launch the IJulia notebook in your browser. The first time you run `notebook()`, it will prompt you for whether it should install Jupyter. Hit enter to have it use the [Conda.jl](https://github.com/Luthaf/Conda.jl) package to install a minimal Python+Jupyter distribution (via [Miniconda](http://conda.pydata.org/docs/install/quick.html)) that is private to Julia (not in your `PATH`).

For more advanced installation options, such as specifying a specific Jupyter installation to use, see the [documentation](https://julialang.github.io/IJulia.jl/stable).