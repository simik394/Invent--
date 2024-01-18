---
page-title: "mokeyish/obsidian-code-emitter: An obsidian plugin that allows code blocks executed interactively in sandbox like jupyter notebooks. Supported language rust、kotlin、python、Javascript、TypeScript etc."
url: https://github.com/mokeyish/obsidian-code-emitter
date: "2024-01-18 00:58:31"
tags: obsi/plugin
purpose:
---

## Obsidian Code Emitter

[![GitHub release (latest by date including pre-releases)](https://camo.githubusercontent.com/130ced0b898fe1e8121c0023b4536894d8048307728412929328807f57b001e1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6d6f6b65796973682f6f6273696469616e2d636f64652d656d69747465723f646973706c61795f6e616d653d74616726696e636c7564655f70726572656c6561736573)](https://camo.githubusercontent.com/130ced0b898fe1e8121c0023b4536894d8048307728412929328807f57b001e1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6d6f6b65796973682f6f6273696469616e2d636f64652d656d69747465723f646973706c61795f6e616d653d74616726696e636c7564655f70726572656c6561736573) [![GitHub all releases](https://camo.githubusercontent.com/ca768c0787086d17449d97d24281348dedb62baf0076ab604af7a31028e7512b/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6d6f6b65796973682f6f6273696469616e2d636f64652d656d69747465722f746f74616c3f7374796c653d666c61742d737175617265)](https://camo.githubusercontent.com/ca768c0787086d17449d97d24281348dedb62baf0076ab604af7a31028e7512b/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6d6f6b65796973682f6f6273696469616e2d636f64652d656d69747465722f746f74616c3f7374796c653d666c61742d737175617265)

This plugin allows code blocks executed interactively like jupyter notebooks. It is based on HTTP REST APIs and JS sandbox and Webassembly technology, and has no local environment requirements, so it supports all platforms supported by Obsidian.

Supports all Obsidian supported platforms, includes:

-   Windows
-   MacOS
-   Linux
-   Android
-   IOS

Currently, support languages:

Supported language

Way

Rust

[https://play.rust-lang.org](https://play.rust-lang.org/)

Kotlin

[https://play.kotlinlang.org](https://play.kotlinlang.org/)

V

[https://play.vosca.dev/](https://play.vosca.dev/)

JavaScript

JS Sandbox ([qiankun](https://github.com/umijs/qiankun/blob/master/src/sandbox/index.ts))

TypeScript\[\]

[TypeScript](https://www.typescriptlang.org/) Compiler + JS Sandbox

Wenyan

[Wenyan](https://github.com/wenyan-lang/wenyan) Compiler + JS Sandbox

Python

WebAssembly ([Pyodide](https://github.com/pyodide/pyodide))

Java

[Sololearn](https://www.sololearn.com/)

Go

[Sololearn](https://www.sololearn.com/)

c/c++

[Sololearn](https://www.sololearn.com/)

CSharp

[Sololearn](https://www.sololearn.com/)

Swift

[Sololearn](https://www.sololearn.com/)

R

[Sololearn](https://www.sololearn.com/)

**Note**: Only `Python`、`TypeScript`、`JavaScript` are run locally in sandbox(js / webassembly). Other's will send code to third-party website to eval the results (eg: [https://play.kotlinlang.org](https://play.kotlinlang.org/), [https://play.rust-lang.org](https://play.rust-lang.org/)). Please take care to avoid sending your potentially-sensitive source code.

**Ads**: You might like my other plugins 🤪

-   [Obsidian Enhancing Export](https://github.com/mokeyish/obsidian-enhancing-export)

---

[![.](https://github.com/mokeyish/obsidian-code-emitter/raw/master/screenshots/code-emitter.gif)](https://github.com/mokeyish/obsidian-code-emitter/blob/master/screenshots/code-emitter.gif)[](https://github.com/mokeyish/obsidian-code-emitter/blob/master/screenshots/code-emitter.gif)

## Installation

1.  Search `Code Emitter` in the community plugins of [obsidian](https://obsidian.md/), and install it.

## Examples

### Python

Install numpy through `micropip`. All available packages are list in [here](https://github.com/mokeyish/pyodide-dist/find/master) (search `whl`).

import micropip
await micropip.install('numpy')  
import numpy as np
a \= np.random.rand(3,2)
b \= np.random.rand(2,5)

print(a@b)

### Any languages that support CORS

Here is the example to support Ruby.

const url \= 'https://api2.sololearn.com/v2/codeplayground/v2/compile';

const runCode \= async (code: string, lang: 'cpp' | 'go' | 'c' | 'java' | 'cs' | 'swift' | 'rb') \=> {
  const header \= {
    'User-Agent': 'Obsidian Code Emitter/0.1.0 (If this is not allowed, please let me know)',
    'Accept': 'application/json, text/plain, \*/\*',
    'Accept-Language': 'en-US',
    'Content-Type': 'application/json',
  };
		
  const res \= await fetch(url, {
    'headers': header,
    'body': JSON.stringify({
      'code': code,
      'codeId': null,
      'input': '',
      'language': lang
    }),
    'method': 'POST',
  });
  return (await res.json()) as {
    success: boolean,
    errors: string\[\],
    data: {
      sourceCode: number,
      status: number,
      errorCode: number,
      output: string,
      date: string,
      language: string,
      input: string,
    }
  };
};

const ruby\_code \= \`
puts "Hello World12"
\`;

console.log((await runCode(ruby\_code, 'rb')).data.output);

## License

This plugin sandbox contains codes from [https://github.com/umijs/qiankun](https://github.com/umijs/qiankun/blob/master/src/sandbox/index.ts), which is licensed under

-   MIT license (LICENSE-MIT or [http://opensource.org/licenses/MIT](http://opensource.org/licenses/MIT))

And other codes is licensed under

-   GPL-3.0 license (LICENSE-GPL-3.0 or [https://opensource.org/licenses/GPL-3.0](https://opensource.org/licenses/GPL-3.0))