---
page-title: "oowekyala/citegraph: A citation network explorer"
url: https://github.com/oowekyala/citegraph
date: "2024-01-18 02:26:41"
tags: 
purpose: 
uses: file.bibtex
---
## Citegraph

Generates easily readable citation graphs. This uses the contents of a bibtex file to determine what you're interested in.

This uses the semanticscholar API to fetch references for articles. Since the API is rate-limited and requests are very slow, request results are cached locally, and the exploration algorithm is engineered to make every request count. This is done by computing a degree of interest (DOI) for each known paper, and fetching only the papers we think will improve the graph the most. See [here](https://github.com/oowekyala/citegraph/blob/master/src/citegraph/explore.py#L10) for an explanation of the DOI calculation.

### Installation

-   Make sure you have Python 3.6+
-   Also make sure you have [Graphviz](https://www.graphviz.org/download/) on your path
-   Download or clone this repo

$ git clone https://github.com/oowekyala/citegraph.git && cd citegraph

-   Make sure you have all the required Python packages:

$ python3 -m pip install -r DEPENDENCIES

-   Add the `bin` directory to you PATH, or just use `bin/citegraph`

### Usage

Find out the ID of an interesting paper on [semanticscholar.org](https://www.semanticscholar.org/), see for example the highlighted section of this picture:

[![Paper ID example](https://github.com/oowekyala/citegraph/raw/master/examples/semantic_paper_id_ex.png)](https://github.com/oowekyala/citegraph/blob/master/examples/semantic_paper_id_ex.png)

Remove spaces, and you can pass that ID directly to `citegraph`:

$ bin/citegraph CorpusID:125964925
\[1 / 80 / 145\] (DOI 0.0) Fractal calculus and its geometrical explanation 
\[2 / 80 / 145\] (DOI 1.25) Fractal approach to heat transfer in silkworm cocoon hierarchy 
...
\[80 / 80 / 5602\] (DOI 1.428) Bubble Electrospinning for Mass Production of Nanofibers 
Hit max size threshold
Rendering...
Rendered to graph.pdf

Here's what the graph would look like (using a max `--size` of 20 for readability):

[![Graph example](https://github.com/oowekyala/citegraph/raw/master/examples/graph.svg)](https://github.com/oowekyala/citegraph/blob/master/examples/graph.svg)

Use `citegraph --help` to find out about all the options.

### Exploration parameters

By default the exploration algorithm is biased towards exploring downward links. To also explore the papers that cite your root papers, you can use the option `--also-up`.

Compare for example the two following graphs (root paper in pink):

-   Default:

[![Laarman default](https://github.com/oowekyala/citegraph/raw/master/examples/laarman_only_down.svg)](https://github.com/oowekyala/citegraph/blob/master/examples/laarman_only_down.svg)

-   With `--also-up`:

[![Laarman up and down](https://github.com/oowekyala/citegraph/raw/master/examples/laarman_up_and_down.svg)](https://github.com/oowekyala/citegraph/blob/master/examples/laarman_up_and_down.svg)

### Layout and export formats

Export formats are selected using the `--format` (`-f`) option.

The following formats are suitable for importing the graph into an external graph visualisation tool:

-   `gexf`: for [Gephi](https://gephi.org/)
-   `dot`: for [Graphviz](https://graphviz.gitlab.io/)

Citegraph can also call Graphviz directly to perform graph layout and rendering to another format, for example PDF, PNG, or SVG. The default export format is PDF, see the available ones with `--help`.

### Customizing graph appearance

You can specify how individual nodes are styled with a yaml file. For example:

tags:
    read: # an identifier for the tag
        attrs: # DOT attributes:     https://graphviz.gitlab.io/doc/info/attrs.html
            style: bold
        members: # enumerate explicit members using keys of the bibtex file
            - someBibKey
            - another
    
    knuth\_articles: # another tag
        attrs: 
            style: filled
            fillcolor: lightyellow
        
        # Select using an arbitrary python expression
        # The bibtex entry is in scope as 'paper'
        selector: 'any("Knuth" in author.last\_names for author in paper.authors)'