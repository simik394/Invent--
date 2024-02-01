---
page-title: "Pluto.jl — interactive Julia programming environment"
url: https://plutojl.org/
date: "2024-01-17 23:08:49"
tags: A/sw/lang/julia/IDE
purpose:
---

 [![](https://plutojl.org/assets/favicon.svg) Pluto.jl](https://plutojl.org/)

Reactivity

## Interactivity as a fundamental principle

Just like a spreadsheet, Pluto understands variable links between code cells, and will re-run a cell when a dependency changes.

## Reactivity means interactivity

Your programming environment becomes interactive by splitting your code into multiple cells! Changing one cell **instantly shows effects** on all other cells, giving you a fast and fun way to experiment with your model.

In this example, changing the parameter `A` and running the first cell will directly re-evaluate the second cell and display the new plot.

![interactivity screencap](https://user-images.githubusercontent.com/6933510/80637344-24ac0180-8a5f-11ea-82dd-813dbceca9c9.gif) [Learn more](https://plutojl.org/docs/)

## Sliders, buttons and more!

Pluto lets you *bind* a Julia variable to an GUI element. Moving a slider from 0 to 100 will actually change one of your variables from `0` to `100`! Combined with reactivity, this is a very powerful tool!

![@bind macro screencap](https://user-images.githubusercontent.com/6933510/134825003-bd72ef08-677b-42fa-a655-e842868b10f6.gif)

It's that simple to make your Julia code come to life! That's because reactivity and widget interactivity are the same concept! Less to learn, more to discover.

The package [PlutoUI.jl](https://github.com/fonsp/PlutoUI.jl) contains lots of common widgets like sliders, textfields and buttons. Need something different? PlutoUI.jl was made by us, but anyone can create their own special widgets! We give you full control over HTML, CSS and JS, with powerful API to connect a web component to Julia.

[Learn more](https://plutojl.org/docs/)

Reproducibility

## Pluto notebooks are reproducible *by default*

From package management to execution order, Pluto goes to great lengths to make sure that someone else will be able to run your notebook when you're done!

## Built-in package manager

Pluto uses code analysis to understand which packages are being used in a notebook, and it **automatically manages a package environment** for your notebook. You no longer need to install packages, you can directly import any registered package like `Plots` or `DataFrames` and use it.

[Learn more](https://github.com/fonsp/Pluto.jl/wiki/%F0%9F%8E%81-Package-management) ![package manager screencap](https://user-images.githubusercontent.com/6933510/134823403-fbb79d7f-dd3e-4712-b5d5-b48ad0770f13.gif) 

## Workspace variables

Pluto offers an environment where changed code takes effect instantly and where deleted code leaves no trace. Unlike Jupyter or Matlab, there is **no mutable workspace**, but rather, an important guarantee:

> ***At any instant**, the program state is **completely described** by the code you see.*

No hidden state, no hidden bugs.

[Learn more](https://github.com/fonsp/Pluto.jl/wiki/%F0%9F%8E%81-Package-management)

Julia programming

## A fresh approach to scientific computing

Pluto is an environment to work with the [Julia programming language](https://julialang.org/). Easy to use like Python, fast like C. *(We think it's the future!)*

### Fast

Julia was designed from the beginning for [high performance](https://julialang.org/benchmarks/). Julia programs compile to efficient native code for [multiple platforms](https://julialang.org/downloads/#currently_supported_platforms) via LLVM.

### Dynamic

Julia is [dynamically typed](https://docs.julialang.org/en/v1/manual/types/), feels like a scripting language, and has good support for [interactive](https://docs.julialang.org/en/v1/stdlib/REPL/) use.

### Reproducible

[Reproducible environments](https://julialang.github.io/Pkg.jl/v1/environments/) make it possible to recreate the same Julia environment every time, across platforms, with [pre-built binaries](https://binarybuilder.org/).

### Composable

Julia uses [multiple dispatch](https://docs.julialang.org/en/v1/manual/methods/) as a paradigm, making it easy to express many object-oriented and [functional](https://docs.julialang.org/en/v1/manual/functions/) programming patterns. The talk on the [Unreasonable Effectiveness of Multiple Dispatch](https://www.youtube.com/watch?v=kc9HwsxE1OY) explains why it works so well.

### General

Julia provides [asynchronous I/O](https://docs.julialang.org/en/v1/manual/networking-and-streams/), [metaprogramming](https://docs.julialang.org/en/v1/manual/metaprogramming/), [debugging](https://github.com/JuliaDebug/Debugger.jl), [logging](https://docs.julialang.org/en/v1/stdlib/Logging/), [profiling](https://docs.julialang.org/en/v1/manual/profile/), a [package manager](https://docs.julialang.org/en/v1/stdlib/Pkg/index.html), and more. One can build entire [Applications and Microservices](https://www.youtube.com/watch?v=uLhXgt_gKJc) in Julia.

### Open source

Julia is an open source project with over 1,000 contributors. It is made available under the [MIT license](https://github.com/JuliaLang/julia/blob/master/LICENSE.md). The [source code](https://github.com/JuliaLang/julia) is available on GitHub.

Education

## A programming environment designed for *learning and teaching*

We designed Pluto to teach our own course: [Computational Thinking at MIT](https://computationalthinking.mit.edu/). The result is a programming environment that prioritizes beginners over advanced users!

## *Computational Thinking* at MIT

Pluto was developed alongside the free online course [Introduction to Computational Thinking](https://computationalthinking.mit.edu/) at MIT, with the goal of creating a programming environment that is powerful, helpful and interactive, without being too intimidating for students and teachers.

Are you interested in using Pluto for your class? Here are some presentations by people who are using it already: [the MIT team](https://www.youtube.com/watch?v=LFRI3s0DE-o), [Gerhard Dorn](https://www.youtube.com/watch?v=6Qs5EXDpZBI), [Daniel Molina](https://www.youtube.com/watch?v=NrIxgnFXslg), [Henki W. Ashadi](https://youtu.be/GnEKgW23PvY?t=586) and [Max Köhler](https://www.youtube.com/watch?v=8H5KgSIWsWQ).

[Learn more](https://github.com/fonsp/Pluto.jl/wiki/%F0%9F%8E%81-Package-management) ([video](https://www.youtube.com/watch?v=rpB6zQNsbQU)) Grant Sanderson ([3Blue1Brown](https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw)) using Pluto's interactivity to teach [Computational Thinking at MIT](https://computationalthinking.mit.edu/)!

Let's go!

## Let's install Pluto!

Pluto can be installed and updated using Julia's package manager.

## Step 1: Install Julia 1.10.0

Go to [https://julialang.org/downloads](https://julialang.org/downloads) and download the *current stable release*.

## Step 2: Run Julia

After installing, **make sure that you can run Julia**. On some systems, this means searching for the “Julia 1.10” program installed on your computer; in others, it means running the command `julia` in a terminal.

Make sure that you can execute `1 + 1`.

![screenshot of the Julia REPL with 1+1 executed](https://user-images.githubusercontent.com/6933510/207901547-230f77fc-004e-493b-a779-a0178979f145.png)## Step 3: Install Pluto

In the Julia terminal, type:

```
import Pkg; Pkg.add("Pluto")
```

This will use Julia's package manager to install the Pluto package.

*This might take a couple of minutes, so you can go get yourself a cup of tea!*

[Video instructions](https://computationalthinking.mit.edu/Fall22/installation/) ![screenshot of the Julia REPL running the command import Pkg; Pkg.add("Pluto")](https://user-images.githubusercontent.com/6933510/207904289-7776fce2-acb4-4777-a89f-c6dac62293c8.png) 

## Step 4: Run Pluto

In the Julia terminal, type:

```
import Pluto; Pluto.run()
```

Pluto will automatically open your browser when it's ready. 🎉