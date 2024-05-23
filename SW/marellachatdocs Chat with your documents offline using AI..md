---
page-title: "marella/chatdocs: Chat with your documents offline using AI."
url: https://github.com/marella/chatdocs
date: "2024-04-08 20:44:03"
tags: 
- A/sw
- F/homepage
- C/
- P/
about: "[[RAG]]"
aliases: 
- cba0cead-21fd-47b2-8014-2ed9dfb492a3
- marella/chatdocs: Chat with your documents offline using AI.
by: 
length: 3531
dir: 
---

Chat with your documents offline using AI. No data leaves your system. Internet connection is only required to install the tool and download the AI models. It is based on [PrivateGPT](https://github.com/imartinez/privateGPT) but has more features.

[![Web UI](https://github.com/marella/chatdocs/raw/main/docs/demo.png)](https://github.com/marella/chatdocs/raw/main/docs/demo.png)

**Contents**

-   [Features](https://github.com/marella/chatdocs#features)
-   [Installation](https://github.com/marella/chatdocs#installation)
-   [Usage](https://github.com/marella/chatdocs#usage)
-   [Configuration](https://github.com/marella/chatdocs#configuration)
-   [GPU](https://github.com/marella/chatdocs#gpu)

## Features

[](https://github.com/marella/chatdocs#features)

-   Supports GGML/GGUF models via [CTransformers](https://github.com/marella/ctransformers)
-   Supports 🤗 Transformers models
-   Supports GPTQ models
-   Web UI
-   GPU support
-   Highly configurable via `chatdocs.yml`

**Show supported document types**  

Extension

Format

`.csv`

CSV

`.docx`, `.doc`

Word Document

`.enex`

EverNote

`.eml`

Email

`.epub`

EPub

`.html`

HTML

`.md`

Markdown

`.msg`

Outlook Message

`.odt`

Open Document Text

`.pdf`

Portable Document Format (PDF)

`.pptx`, `.ppt`

PowerPoint Document

`.txt`

Text file (UTF-8)

## Installation

[](https://github.com/marella/chatdocs#installation)

Install the tool using:

Download the AI models using:

Now it can be run offline without internet connection.

## Usage

[](https://github.com/marella/chatdocs#usage)

Add a directory containing documents to chat with using:

chatdocs add /path/to/documents

> The processed documents will be stored in `db` directory by default.

Chat with your documents using:

Open [http://localhost:5000](http://localhost:5000/) in your browser to access the web UI.

It also has a nice command-line interface:

**Show preview**

[![Demo](https://github.com/marella/chatdocs/raw/main/docs/cli.png)](https://github.com/marella/chatdocs/raw/main/docs/cli.png)

## Configuration

[](https://github.com/marella/chatdocs#configuration)

All the configuration options can be changed using the `chatdocs.yml` config file. Create a `chatdocs.yml` file in some directory and run all commands from that directory. For reference, see the default [`chatdocs.yml`](https://github.com/marella/chatdocs/blob/main/chatdocs/data/chatdocs.yml) file.

You don't have to copy the entire file, just add the config options you want to change as it will be merged with the default config. For example, see [`tests/fixtures/chatdocs.yml`](https://github.com/marella/chatdocs/blob/main/tests/fixtures/chatdocs.yml) which changes only some of the config options.

### Embeddings

[](https://github.com/marella/chatdocs#embeddings)

To change the embeddings model, add and change the following in your `chatdocs.yml`:

embeddings:
  model: hkunlp/instructor-large

> **Note:** When you change the embeddings model, delete the `db` directory and add documents again.

### CTransformers

[](https://github.com/marella/chatdocs#ctransformers)

To change the CTransformers (GGML/GGUF) model, add and change the following in your `chatdocs.yml`:

ctransformers:
  model: TheBloke/Wizard-Vicuna-7B-Uncensored-GGML
  model\_file: Wizard-Vicuna-7B-Uncensored.ggmlv3.q4\_0.bin
  model\_type: llama

> **Note:** When you add a new model for the first time, run `chatdocs download` to download the model before using it.

You can also use an existing local model file:

ctransformers:
  model: /path/to/ggml-model.bin
  model\_type: llama

### 🤗 Transformers

[](https://github.com/marella/chatdocs#-transformers)

To use 🤗 Transformers models, add the following to your `chatdocs.yml`:

To change the 🤗 Transformers model, add and change the following in your `chatdocs.yml`:

huggingface:
  model: TheBloke/Wizard-Vicuna-7B-Uncensored-HF

> **Note:** When you add a new model for the first time, run `chatdocs download` to download the model before using it.

To use GPTQ models with 🤗 Transformers, install the necessary packages using:

pip install chatdocs\[gptq\]

## GPU

[](https://github.com/marella/chatdocs#gpu)

### Embeddings

[](https://github.com/marella/chatdocs#embeddings-1)

To enable GPU (CUDA) support for the embeddings model, add the following to your `chatdocs.yml`:

embeddings:
  model\_kwargs:
    device: cuda

You may have to reinstall PyTorch with CUDA enabled by following the instructions [here](https://pytorch.org/get-started/locally/).

### CTransformers

[](https://github.com/marella/chatdocs#ctransformers-1)

To enable GPU (CUDA) support for the CTransformers (GGML/GGUF) model, add the following to your `chatdocs.yml`:

ctransformers:
  config:
    gpu\_layers: 50

You may have to install the CUDA libraries using:

pip install ctransformers\[cuda\]

### 🤗 Transformers

[](https://github.com/marella/chatdocs#-transformers-1)

To enable GPU (CUDA) support for the 🤗 Transformers model, add the following to your `chatdocs.yml`:

You may have to reinstall PyTorch with CUDA enabled by following the instructions [here](https://pytorch.org/get-started/locally/).

## License

[](https://github.com/marella/chatdocs#license)

[MIT](https://github.com/marella/chatdocs/blob/main/LICENSE)