---
page-title: "SkepticMystic/graph-analysis: Analyse the structure of your Obsidian graph using various analysis techniques"
url: https://github.com/SkepticMystic/graph-analysis
date: "2024-01-18 00:51:58"
tags: obsi/plugin
purpose:
---

## Graph Analysis

Graph analysis adds the **analysis view** to Obsidian which implements a set of algorithms that computes useful relations between the notes in your vault! Our flagship algorithm is the **Co-citations** panel, that we describe as a *2nd order backlinks panel*.

The Graph Analysis view shows a table of note names and numbers, each representing the value of some graph analysis algorithm on that note in relation to the current note.

e.g.

-   `[[A]] is 0.9 Similar to [[B]]`
-   `[[A]] has a 0.6 chance of being connected to [[B]]`
-   `[[A]] is co-cited with [[B]] 6 times`

## Analysis Types

Graph Analysis currently has 4 different analysis types:

1.  Similarity
2.  Link Prediction
3.  Co-Citations
4.  Community Detection

Each implement different algorithms with different purposes.

### Co-Citations

Co-Citations counts the number of time two notes are cited together in the same note and gives extra weight when the two notes are cited close together.

Think of co-citations as a **2nd-order backlinks** panel: Instead of showing *where* something is cited, it shows *why*, or with *whom* or *what* it is cited!

For example, if `[[C]]` has `[[A]] and [[B]]` in its content, then `[[A]]` and `[[B]]` will each have a co-citation of one.

Each note with co-citations > 0 is given a drop down menu. Inside each drop down, you can see which note co-cites those two notes, and the sentence in which they are co-cited (if in the same sentence), otherwise just the sentence with the other link.

[![](https://camo.githubusercontent.com/cf6d3be756aaa42397d449c87f4b961d618c7e271741ec59c6c32c5bfbfe3dd0/68747470733a2f2f692e696d6775722e636f6d2f397973704f6b4e2e706e67)](https://camo.githubusercontent.com/cf6d3be756aaa42397d449c87f4b961d618c7e271741ec59c6c32c5bfbfe3dd0/68747470733a2f2f692e696d6775722e636f6d2f397973704f6b4e2e706e67)

#### Example use case with daily notes

An example why this is useful is given by @HEmile:

> I use a lot of daily notes, in which I journal and write about the news of the day. This makes the backlinks panel a bit boring: It only shows on what dates I wrote about some note. The Co-Citations algorithm shows me much more! For example, the `Joe Biden` note shows me I usually write about Biden together with `Donald Trump`. But if I want to know what I wrote about the relations between Joe Biden and `China`, I can just look in the co-citations panel and expand the relation to see the story!

[![](https://camo.githubusercontent.com/0d2cfb65dc26702990036fff8072fae79bd4903d32814f2a33586a97b19b7711/68747470733a2f2f692e696d6775722e636f6d2f7564506b7556332e706e67)](https://camo.githubusercontent.com/0d2cfb65dc26702990036fff8072fae79bd4903d32814f2a33586a97b19b7711/68747470733a2f2f692e696d6775722e636f6d2f7564506b7556332e706e67)

#### Video Tutorial

This video gives a longer and in depth overview for why Co-Citations is so useful! [![Watch the video](https://camo.githubusercontent.com/728bf10bbfcb5f0f3f0245ef62c501f536ee7a505b7a7ce7ef29915f11641af7/68747470733a2f2f79742d656d6265642e6865726f6b756170702e636f6d2f656d6265643f763d724b364a56447247455241)](https://youtu.be/rK6JVDrGERA)

### Similarity

Similarity is a measure of how similar two notes are based on their connectedness in the graph (ie. note content is not considered). Currently, only the Jaccard Similarity measure is implemented.

#### Jaccard Similarity

**Formula**:

[![image](https://user-images.githubusercontent.com/70717676/139872572-93504295-6d29-4722-bdb1-3fbeb7bc22ec.png)](https://user-images.githubusercontent.com/70717676/139872572-93504295-6d29-4722-bdb1-3fbeb7bc22ec.png)

[Source](https://neo4j.com/docs/graph-data-science/current/alpha-algorithms/jaccard/#alpha-algorithms-similarity-jaccard-context)

Where

-   `|x|` is the number of neighbours the node `x` has (links going in or out).
-   `|x & y|` is the number of neighbours that both `x` and `y` have in common

### Link Prediction

Link Prediction is a measure of the probability that two notes should be connected based on their other connections in the graph. The implemented Link Prediction algorithms are Adamic Adar and Common Neighbours.

#### Adamic Adar

**Formula**:

[![image](https://user-images.githubusercontent.com/70717676/139873180-c870e072-843c-42a9-83fc-87205b408754.png)](https://user-images.githubusercontent.com/70717676/139873180-c870e072-843c-42a9-83fc-87205b408754.png)

[Source](https://neo4j.com/docs/graph-data-science/current/alpha-algorithms/adamic-adar/)

Where:

-   `N(x)` is the number of neighbours of `x`

#### Common Neighbours

**Formula**:

[![image](https://user-images.githubusercontent.com/70717676/139873406-d0542335-3b8c-4d08-8a5b-4510408ebd4e.png)](https://user-images.githubusercontent.com/70717676/139873406-d0542335-3b8c-4d08-8a5b-4510408ebd4e.png)

[Source](https://neo4j.com/docs/graph-data-science/current/alpha-algorithms/common-neighbors/)

Where:

-   `N(x)` is the numbers of neighbours of `x`

### Community Detection

These algorithms try to find groups of similar notes.

#### Label Propagation

Start by giving each node a unique label (its own name). Then, look at each node's neighbours, and change it's label to the most common among it's neighbours. Repeat this process `iterations` number of times.

At the end, show the nodes grouped by the last label they had.

#### Clustering Coefficient

Gives the ratio of the number of *triangles* the `u` is a part of, to the number of triangles it possibly *could have* been a part of:

[![image](https://user-images.githubusercontent.com/70717676/140610147-0a05201f-d9c7-4c0c-b423-6bbeeb81253b.png)](https://user-images.githubusercontent.com/70717676/140610147-0a05201f-d9c7-4c0c-b423-6bbeeb81253b.png)

## Utility Classes

Each row in the graph analysis tables (or co-citations dropdowns) has a class: `analysis-linked` or `analysis-not-linked`, indicating if the current note is linked to the note in that row. This gives you the ability to style a table row based on whether it's connectedness.

For example, you can make linked notes have a lower opacity:

tr.analysis-linked {
  opacity: 0.3;
}

[![image](https://user-images.githubusercontent.com/70717676/139862955-75284ff5-0ced-4548-bf6e-caa353a16fe0.png)](https://user-images.githubusercontent.com/70717676/139862955-75284ff5-0ced-4548-bf6e-caa353a16fe0.png)

You could even go so far as to hide linked rows completely:

tr.analysis-linked {
  display: none;
}

## Settings

In the analysis view, you have the option to choose between different `Analysis Types`, and different `Algorithms` within those types. You can set the default analysis type in the plugin settings.

There is also the option to hide `Infinity` and `Zero` values.

[![image](https://user-images.githubusercontent.com/70717676/138652879-d8b0e4a7-d70a-44e8-ba3c-67e04f6a8edd.png)](https://user-images.githubusercontent.com/70717676/138652879-d8b0e4a7-d70a-44e8-ba3c-67e04f6a8edd.png)

## Documentation on Algorithms

You can read more about the implemented algorithms, or let us know which you want us to add, over [here](https://neo4j.com/docs/graph-data-science/current/algorithms/) 👀. Information on co-citations can mostly be found on [Wikipedia](https://en.wikipedia.org/wiki/Co-citation). In particular, we implement a variation of [Co-citatition Proximity Analysis](https://en.wikipedia.org/wiki/Co-citation_Proximity_Analysis).

## Buy Us a Coffee

SkepticMystic: [![ko-fi](https://camo.githubusercontent.com/ce32b4940b9ebf361cfd346ba0582815846406854cd2f701c11a85cb21eaa939/68747470733a2f2f6b6f2d66692e636f6d2f696d672f676974687562627574746f6e5f736d2e737667)](https://ko-fi.com/G2G454TZF)

Emile: [![ko-fi](https://camo.githubusercontent.com/ce32b4940b9ebf361cfd346ba0582815846406854cd2f701c11a85cb21eaa939/68747470733a2f2f6b6f2d66692e636f6d2f696d672f676974687562627574746f6e5f736d2e737667)](https://ko-fi.com/Emile)