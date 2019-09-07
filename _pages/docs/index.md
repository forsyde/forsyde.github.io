---
title: Documentation
layout: default
permalink: docs/index.html
top-navbar: true
---

On this page we tried gathering many of the ForSyDe documents (e.g. technical reports,
tutorials, API documentations) scattered across the internet and grouping them by
relevant topics. The purpose is to point to and help the interested reader to reach
whatever information she might need without much hassle. As a general rule, here you
find tool-oriented documentation. For associated scientific publications, please check
our [Publications](/publications) page.

# Design of Systems

Here we point to documentations on tools and frameworks for design-related activities,
such as modeling, simulation, testing, etc.

### General

These documents present a general view of ForSyDe modeling and/or go through multiple
design frameworks and compares them.

* [**The ForSyDe
  chapter**](https://link.springer.com/content/pdf/10.1007%2F978-94-017-7267-9_5.pdf)
  in the ["Handbook of Hardware/Software
  Codesign"](https://link.springer.com/referencework/10.1007%2F978-94-017-7267-9) (
  [doi](https://doi.org/10.1007/978-94-017-7267-9_5) \|
  [pdf-url](https://link.springer.com/content/pdf/10.1007%2F978-94-017-7267-9_5.pdf)
  \| [ref](publications.html#SanJan2017a) \| [bib](publications_bib.html#SanJan2017a)
  ) is a slightly outdated but highly relevant introduction to ForSyDe modeling using
  different models of computation (MoC). It covers (a bit of) the basic ForSyDe
  principles, modeling, simulation, hardware synthesis and visualization and it
  introduces the [ForSyDe-Shallow](/forsyde-shallow), [ForSyDe-Deep](/forsyde-deep)
  and [ForSyDe-SystemC](/ForSyDe-SystemC) frameworks.

* [**Design of Sensor Signal Processing with ForSyDe**](aesa-radar) (
  [pdf](aesa-radar/aesa-report.pdf) \| [html](aesa-radar) \|
  [doi](https://doi.org/10.13140/RG.2.2.21573.81126) ) is a detailed technical report
  which teaches more advanced modeling techniques by going step-by-step through
  modeling, executing, formulating properties, testing, refining, (partially)
  synthesizing and co-simulating a radar signal processing system. It is a living
  document built in a [literate programming
  style](https://en.wikipedia.org/wiki/Literate_programming) from [this source
  project](https://github.com/forsyde/aesa-radar) and as modeling frameworks it uses
  [ForSyDe-Atom](/forsyde-atom), [ForSyDe-Shallow](/forsyde-shallow) and
  [ForSyDe-Deep](forsyde-deep).

* [**Ingo Sander's PhD
  Thesis**](https://www.diva-portal.org/smash/get/diva2:9340/FULLTEXT01.pdf) (
  [urn](http://urn.kb.se/resolve?urn=urn%3Anbn%3Ase%3Akth%3Adiva-3525) \|
  [pdf](https://www.diva-portal.org/smash/get/diva2:9340/FULLTEXT01.pdf) ) contains
  the original ideas behind the ForSyDe methodology. Although ForSyDe as an ecosystem
  evolved much during the last two decades, the thesis still reads well as a "manual"
  on process constructor-based modeling concepts, especially chapter 2 (Background)
  which contains a tutorial on Haskell[^1] for the new users. The examples presented in
  the thesis are given in [ForSyDe-Shallow](/forsyde-shallow/).

### ForSyDe-Shallow

These documents use [ForSyDe-Shallow](/forsyde-shallow/) as base framework. 

* The ForSyDe-Shallow [**Getting Started Tutorial**](/forsyde-shallow/getting_started)
  introduces basic modeling concepts such as signals, processes and process
  constructors and guides through modeling and simulating a simple counter system.

* The [**Examples Repository**](https://github.com/forsyde/forsyde-shallow-examples)
  contains a couple of tutorial examples, where the best documentation is the source
  code itself. Check the repository's `README` file for how to generate the code
  documentation.
  
* An [**Equalizer
  Example**](https://github.com/forsyde/forsyde-shallow-examples/blob/master/files/docs/DocumentationEqualizer.pdf),
  extracted from Ingo Sander's PhD Thesis, shows how to use ForSyDe-Shallow in order
  to design and simulate an equalizer system.

* A (rather old) [**example on how to model an ASK transceiver
  system**](https://github.com/forsyde/forsyde-shallow-examples/blob/master/files/docs/DocumentationTransceiver.pdf)
  which has been re-compiled for the newest ForSyDe-Shallow library version. Except
  for the installation instructions, the document remains highly relevant.

* The online [**API documentation**](http://hackage.haskell.org/package/forsyde-shallow) for the ForSyDe-Shallow library is indispensable
  once you start using the framework.

### ForSyDe-Atom

These documents use [ForSyDe-Atom](/forsyde-atom/) as base framework.

* The [**ForSyDe-Atom User Manual**](/forsyde-atom/assets/manual.pdf) is a living
  document written in [literate programming
  style](https://en.wikipedia.org/wiki/Literate_programming) which bundles together a
  couple of detailed [tutorials and use
  cases](https://github.com/forsyde/forsyde-atom-examples) along with the [library API
  documentation](/forsyde-atom/api/).
  
* The [**API documentation**](/forsyde-atom/api/) is written very much in a "manual"
  style and gives details about library design decisions, formulations, specific uses
  and test cases. 

### ForSyDe-SystemC

These documents use [ForSyDe-SystemC](/ForSyDe-SystemC/) as base framework. 

* The [**SY MoC Tutorial**](/ForSyDe-SystemC/sy-tutorial) is a small example of
  modeling a synchronous process network in ForSyDe-SystemC.

* The [**SDF MoC Tutorial**](/ForSyDe-SystemC/sdf-tutorial) is an example of up/down
  sampler modeled in the synchronous data flow MoC in ForSyDe-SystemC.

* The [**CT MoC Tutorial**](https://forsyde.github.io/ForSyDe-SystemC/ct-tutorial) is
  an example of a low-pass filter modeled in the continuous time MoC in
  ForSyDe-SystemC.

* The [**API documentation**](/ForSyDe-SystemC/api/) was generated with Doxygen.

# Design Space Exploration

These documents refer to the [DeSyDe](https://github.com/forsyde/DeSyDe) design space
exploration tool.

* The [**Getting Started with
  DeSyDe**](https://github.com/forsyde/DeSyDe/blob/v0.3.0-dsd/docs/tutorial.md)
  tutorial guides the reader how to write the DeSyDe XML input files for specifying
  the applications, constraints and platform models in order to enable design space
  exploration.
  
* The [**examples folder**](https://github.com/forsyde/DeSyDe) in the DeSyDe source
  repository contain a few examples and case studies used for different papers.

# Synthesis

* The [**Getting Started with ForSyDe-Deep**](/forsyde-deep/getting_started) tutorial
  goes through designing and synthesizing to FPGA a simple counter example from a
  [ForSyDe-Deep](/forsyde-deep/) synchronous model.
  
* A [**more advanced tutoial**](/forsyde-deep/forsyde-deep-tutorial) goes through more
  advanced uses of [ForSyDe-Deep](/forsyde-deep/), such as internal structure visualization,
  co-simulation and generation for different backends, as well as a dedicated tutorial
  on using [fixed-size vectors](/forsyde-deep/forsyde-deep-tutorial#appendices).

* [**The ForSyDe
  chapter**](https://link.springer.com/content/pdf/10.1007%2F978-94-017-7267-9_5.pdf)
  in the ["Handbook of Hardware/Software
  Codesign"](https://link.springer.com/referencework/10.1007%2F978-94-017-7267-9) (
  [doi](https://doi.org/10.1007/978-94-017-7267-9_5) \|
  [pdf-url](https://link.springer.com/content/pdf/10.1007%2F978-94-017-7267-9_5.pdf)
  \| [ref](publications.html#SanJan2017a) \| [bib](publications_bib.html#SanJan2017a)
  ) contains a section on using [ForSyDe-Deep](/forsyde-deep/).

* [**Design of Sensor Signal Processing with ForSyDe**](aesa-radar) (
  [pdf](aesa-radar/aesa-report.pdf) \| [html](aesa-radar) \|
  [doi](https://doi.org/10.13140/RG.2.2.21573.81126) ) has a chapter dedicated to
  refining and synthesizing ForSyDe models using [ForSyDe-Deep](/forsyde-deep/).

* [**f2cc usage tutorial**](https://github.com/forsyde/f2cc/wiki) presents the main
  ideas and usage of the ForSyDe-to-CUDA C tool.

# Plotting and Visualization

* The [**ForSyDe-LaTeX User Manual**](/forsyde-latex/assets/pdf/refman.pdf) documents
  our in-house [ForSyDe-LaTeX](/forsyde-latex/) package used for drawing graphs,
  plots, formulas and general-purpose figures used in ForSyDe documents.
  
* The [**f2dot tutorial**](https://github.com/forsyde/f2dot/wiki/Tutorial) shows how
  to use the [f2dot](https://github.com/forsyde/f2dot/wiki) tool to plot ForSyDe-XML
  and [SDF3](http://www.es.ele.tue.nl/sdf3/) application files.
  
* The Getting Started chapter in [**ForSyDe-Atom User
  Manual**](/forsyde-atom/assets/manual.pdf) has a hands-on section on how to plot
  ForSyDe-Atom signals using either [ForSyDe-LaTeX](/forsyde-latex/) or the
  [gnuplot](http://www.gnuplot.info/) engine.

#### Footnotes

[^1]: Haskell is the host language behind [ForSyDe-Shallow](/forsyde-shallow) and [ForSyDe-Deep](forsyde-deep), [ForSyDe-Atom](/forsyde-atom) and [Reactive-GPAC](https://github.com/forsyde/reactive-gpac)
