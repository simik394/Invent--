---
page-title: "latex-lsp/texlab: An implementation of the Language Server Protocol for LaTeX"
url: https://github.com/latex-lsp/texlab
date: "2024-06-21 03:55:53"
tags: [A/sw/plugin/lsp, F/prod/homepage, C/, P/pwf]
about: ["[[NeoVim]]","[[latex]]"]
aliases: 
- 
by: 
length: 2438
dir: 
---

[![CI](https://github.com/latex-lsp/texlab/workflows/CI/badge.svg)](https://github.com/latex-lsp/texlab/actions) [![Wiki](https://camo.githubusercontent.com/75236a41cea4421cca696706e1defc6ad4058b443977e4be931692eeb23878ef/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646f63732d57696b692d73756363657373)](https://github.com/latex-lsp/texlab/wiki) [![GitHub release](https://camo.githubusercontent.com/3b2febfdf0e7dc87fd7e7e1efbf12e3a699ee32df59d346888ff292c0c16a717/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f72656c656173652f6c617465782d6c73702f7465786c61623f6c6162656c3d676974687562)](https://github.com/latex-lsp/texlab/releases) [![CTAN](https://camo.githubusercontent.com/84383145fe6e10ac1ec31a4a53b04b142478680bb38e9bf6642df0a0d7616c3a/68747470733a2f2f696d672e736869656c64732e696f2f6374616e2f762f7465786c6162)](https://ctan.org/pkg/texlab)

## TexLab

[](https://github.com/latex-lsp/texlab#texlab)

A cross-platform implementation of the [Language Server Protocol](https://microsoft.github.io/language-server-protocol) providing rich cross-editing support for the [LaTeX](https://www.latex-project.org/) typesetting system. The server may be used with [any editor that implements the Language Server Protocol](https://microsoft.github.io/language-server-protocol/implementors/tools/).

[![Demo](https://github.com/latex-lsp/texlab/raw/master/images/demo.gif)](https://github.com/latex-lsp/texlab/blob/master/images/demo.gif)

## Getting Started

[](https://github.com/latex-lsp/texlab#getting-started)

If your editor extension like does not install the TexLab server automatically, you will need to install it manually. We provide [precompiled binaries](https://github.com/latex-lsp/texlab/releases) for Windows, Linux and macOS. Alternatively, you can build TexLab from source or install it using your package manager. For a list of supported package managers, you can take a look at [Repology](https://repology.org/project/texlab/versions):

[![Packaging status](https://camo.githubusercontent.com/016ed8e0dd9f8a51ffaed4f8054fa42f8397e77ba85093cbf813ae163ea3c92f/68747470733a2f2f7265706f6c6f67792e6f72672f62616467652f766572746963616c2d616c6c7265706f732f7465786c61622e737667)](https://repology.org/project/texlab/versions)

### Requirements

[](https://github.com/latex-lsp/texlab#requirements)

A [TeX distribution](https://www.latex-project.org/get/#tex-distributions) is *not* strictly required to use the server but TexLab cannot compile your documents without one. TexLab supports compiling using [Tectonic](https://tectonic-typesetting.github.io/). For an example configuration, please see [here](https://github.com/latex-lsp/texlab/wiki/Tectonic).

On Windows, you may need to install [Microsoft Visual C++ Redistributable for Visual Studio 2015](https://www.microsoft.com/en-US/download/details.aspx?id=48145).

### Building from Source

[](https://github.com/latex-lsp/texlab#building-from-source)

You will need to install the following dependencies to compile the server:

-   A recent, stable version of [Rust](https://rustup.rs/)

Then run the following command in the project folder:

Avoid installing `texlab` from [crates.io](https://crates.io/crates/texlab) because we don't publish new versions of the server to the registry, anymore. Instead, you can use

cargo install --git https://github.com/latex-lsp/texlab --locked --tag <insert version here\>

## Usage

[](https://github.com/latex-lsp/texlab#usage)

After installing an editor extension, you can simply start editing LaTeX files. All editing features work out-of-the-box over all files in the currently opened workspace. There is no need for magic comments like `%!TEX root` and TexLab should figure out the dependencies of a file on its own. Note that you may need to set the `texlab.rootDirectory` option for some multi-folder projects.

TexLab features a variety of options which can be used to configure features like building or forward search.

See the [Wiki](https://github.com/latex-lsp/texlab/wiki) for more information.

## Development

[](https://github.com/latex-lsp/texlab#development)

You can create a debug build by building the server without the `--release` flag. The resulting build can be used with the [Visual Studio Code extension](https://github.com/latex-lsp/texlab-vscode) by adding the absolute path of the `target/debug` folder to your `PATH` environment variable.

TexLab has an extensive test suite of unit and integration tests. You can run them by executing

in the project folder.

## Contributing

[](https://github.com/latex-lsp/texlab#contributing)

See [CONTRIBUTING.md](https://github.com/latex-lsp/texlab/blob/master/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Maintainers

[](https://github.com/latex-lsp/texlab#maintainers)

-   Patrick Förster ([patrick.foerster@outlook.de](mailto:patrick.foerster@outlook.de))

## License

[](https://github.com/latex-lsp/texlab#license)

[GPL-3.0](https://choosealicense.com/licenses/gpl-3.0/)