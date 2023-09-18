---
title: Projects
layout: default
permalink: tools.html
top-navbar: true
forsyde-shallow-url:	https://forsyde.github.io/forsyde-shallow
forsyde-atom-url:		https://forsyde.github.io/forsyde-atom
forsyde-systemc-url:	https://forsyde.github.io/ForSyDe-SystemC
forsyde-gpac-url:		https://github.com/forsyde/reactive-gpac
desyde-url:				https://github.com/forsyde/DeSyDe
idesyde-url:			https://forsyde.github.io/IDeSyDe
forsyde-io-url:         https://forsyde.github.io/forsyde-io/
f2sdf3-url:				https://github.com/forsyde/f2sdf3
forsyde-deep-url:		https://forsyde.github.io/forsyde-deep
f2cc-url:				https://github.com/forsyde/f2cc
forsyde-latex-url:		https://forsyde.github.io/forsyde-latex
f2dot-url:				https://github.com/forsyde/f2dot/wiki
forsyde-eclipse-url:	https://github.com/forsyde/ForSyDe-Eclipse
---

# The ForSyDe Ecosystem

While built to support our [publications](publications.html), the ForSyDe tools create an ecosystem which is aligned to our vision of correct-by-construction system design. These are continuously developed and distributed as [open-source](https://en.wikipedia.org/wiki/Open-source_software) projects, and our developer and user base is growing. This page presents some of the highlighted tools, in activity and alphabetical orders, along the main activities in the [design flow](https://forsyde.github.io/#our-vision) they are involved in.


## [ForSyDe-Atom]({{ page.forsyde-atom-url }})

> *Activities*: **Modeling, Simulation**

<a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; 
<a href="https://github.com/forsyde/f2dot"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[ForSyDe-Atom]({{ page.forsyde-atom-url }}) is a spin-off from [ForSyDe-Shallow]({{ page.forsyde-shallow-url }}) which further explores the power of functional programming as a system design paradigm. Apart from timing behavior, it enables designers to capture other extra-functional properties (e.g. structured parallelism, control behavior) by enforcing a design methodology of systems as [*interacting layers*](https://forsyde.github.io/forsyde-latex/assets/svg/example-pictures-layered.svg). <!-- Each layer is an environment which captures the semantics of an extra-functional concern as a set of indivisible building blocks called *atoms*. Furthermore, it provides libraries of common building blocks in cyber-physical system design blocks, described as compositional *patterns* of atoms. -->
Like its parent project, it is implemented as a shallow-embedded domain specific language (EDSL) in the functional programming language [Haskell](https://www.haskell.org/) and is shipped as a set of Haskell [libraries](https://github.com/forsyde/forsyde-atom) and [examples](https://github.com/forsyde/forsyde-atom-examples).


## [ForSyDe-IO]({{ page.forsyde-io-url }})

> *Activities*: **Modeling, Design Space Exploration, Synthesis**

<!-- ![Python test build](https://github.com/forsyde/forsyde-io/actions/workflows/test-builds-python.yml/badge.svg) -->
![Java test build](https://github.com/forsyde/forsyde-io/actions/workflows/test-builds-java.yml/badge.svg)
<!-- [![PyPi ForSyDe IO](https://badgen.net/pypi/v/forsyde-io-python?icon=pypi)](https://pypi.org/project/forsyde-io-python/) -->
[![JitPack](https://jitpack.io/v/forsyde/forsyde-io.svg)](https://jitpack.io/#forsyde/forsyde-io)
[![GitHub ForSyDe IO](https://badgen.net/github/release/forsyde/forsyde-io?icon=github)](https://github.com/forsyde/forsyde-io/releases)
<a href="https://github.com/forsyde/forsyde-io"><img src="/assets/images/active.svg" alt="Development status"></a> 

[ForSyDe-IO]({{ page.forsyde-io-url }}) is ForSyDe's system-level exchangeable model specification and its supporting libraries.

## [ForSyDe-LaTeX]({{ page.forsyde-latex-url }})

> *Activities*: **Visualization**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-latex"><img src="https://travis-ci.org/forsyde/forsyde-latex.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/forsyde-latex"><img src="/assets/images/active.svg" alt="Development status"></a> 

[ForSyDe-LaTeX]({{ page.forsyde-latex-url }}) is a collection of (La)TeX/TikZ/PGF style packages that were developed as an effort to standardize symbols and graphical primitives in documents related to the ForSyDe methodology. It is mainly used to draw [visual depictions](https://forsyde.github.io/forsyde-latex/assets/svg/example-forsyde-tikz.svg) of the ForSyDe process networks and to [plot data](https://forsyde.github.io/forsyde-latex/assets/svg/example-forsyde-plot.svg) dumped by ForSyDe signals. 


## [ForSyDe-Shallow]({{ page.forsyde-shallow-url }})

> *Activities*: **Modeling, Simulation**

<a href="https://travis-ci.org/forsyde/forsyde-shallow"><img src="https://travis-ci.org/forsyde/forsyde-shallow.svg?branch=master" alt="Build status"></a>&emsp; 
<a href="https://github.com/forsyde/forsyde-shallow"><img src="/assets/images/active.svg" alt="Development status"></a> 

[ForSyDe-Shallow]({{ page.forsyde-shallow-url }}) is a formal framework for modeling and simulating heterogeneous and cyber-physical systems as networks of MoC-bound processes. It is implemented as a shallow-embedded domain specific language (EDSL) in the functional programming language [Haskell](https://www.haskell.org/) and is shipped as a set of Haskell [libraries](https://github.com/forsyde/forsyde-shallow) and [examples](https://github.com/forsyde/forsyde-shallow-examples).


## [ForSyDe-SystemC]({{ page.forsyde-systemc-url }})

> *Activities*: **Modeling, Simulation**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/ForSyDe-SystemC"><img src="/assets/images/active.svg" alt="Development status"></a> 

[ForSyDe-SystemC]({{ page.forsyde-systemc-url }}) is another modeling framework for heterogeneous systems based on the theory of MoCs. Apart from using the host language for simulation purpose, it uses the concept of *introspection* to dump structural data into an intermediate representation which can be fed to DSE and synthesis tools. It is implemented as a shallow-embedded domain specific language (EDSL) in the IEEE standard language [SystemC](http://www.accellera.org/downloads/standards/systemc) and is shipped as a set of C++ [header libraries](https://github.com/forsyde/ForSyDe-Systemc) and [demonstrators](https://github.com/forsyde/forsyde-systemc-demonstrators).

Currently the [ForSyDe-SystemC]({{ page.forsyde-systemc-url }}) framework and associated tools are developed under the supervision of [Seyed-Hosein Attarzadeh-Niaki](http://facultymembers.sbu.ac.ir/attarzadeh/) at Shahid Beheshti University, Iran. Information on the ForSyDe web site may be lagging behind current development, so please check Hosein's [homepage](http://facultymembers.sbu.ac.ir/attarzadeh/) for the latest news.


## [IDeSyDe]({{ page.idesyde-url }})

> *Activities*: **Design Space Exploration**

![Building executables](https://github.com/forsyde/IDeSyDe/actions/workflows/test-build.yml/badge.svg)
![Solving known case studies](https://github.com/forsyde/IDeSyDe/actions/workflows/test-case-studies.yml/badge.svg)
[![GitHub IDeSyDe](https://badgen.net/github/release/forsyde/IDeSyDe?icon=github)](https://github.com/forsyde/IDeSyDe/releases)
<a href="https://github.com/forsyde/IDeSyDe"><img src="/assets/images/active.svg" alt="Development status"></a> 

[IDeSyDe]({{ page.idesyde-url }}) is design space exploration (DSE) framework centered around the design space identification approach.
<!-- The default distribution is a collection of standalone binaries and Java archives enabling exploration of [ForSyDe IO]({{ page.forsyde-io-url}}) models. -->

## [DeSyDe]({{ page.desyde-url }})

> *Activities*: **Design Space Exploration**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/DeSyDe"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[DeSyDe]({{ page.desyde-url }}) is the previous design space exploration (DSE) tool in the ForSyDe ecosystem, based on constraint programming techniqes. It takes a set of *application models* (e.g. [SDF3 graphs](http://www.es.ele.tue.nl/sdf3/), periodic tasks), a *platform model* (e.g. TDMA-bus or TDN-NoC based multiprocessor systems), a set of *constraints* and *optimization criteria* (e.g. throughput, area, monetary cost, power consumption), and explores the full design space generated to find an optimal or satisfying mapping. It is implemented as a C++ project using [GeCode](http://www.gecode.org/) as the main CP solver, and is shipped as a [binary application](https://github.com/forsyde/DeSyDe).


## [f2dot]({{ page.f2dot-url }})

> *Activities*: **Visualization**

<!-- <a href="https://travis-ci.org/forsyde/f2dot"><img src="https://travis-ci.org/forsyde/f2dot.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/f2dot"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[f2dot]({{ page.f2dot-url }}) is a visualization tool for plotting [DOT](https://en.wikipedia.org/wiki/DOT_(graph_description_language)) graphs from the XML intermediate representation of [ForSyDe-SystemC]({{ page.forsyde-systemc-url }}) and [SDF3](http://www.es.ele.tue.nl/sdf3/). It is implemented as a Python project and is shipped as a [binary application](https://github.com/forsyde/f2dot).


## [f2sdf3]({{ page.f2sdf3-url }})

> *Activities*: **Modeling**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/f2sdf3"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[f2sdf3]({{ page.f2sdf3-url }}) is an XSLT script for transforming the intermediate representations dumped by [ForSyDe-SystemC]({{ page.forsyde-systemc-url }}) into [SDF3 graphs](http://www.es.ele.tue.nl/sdf3/) representations, to be further fed to [DeSyDe]({{ page.desyde-url }}). Once the functionality is embedded into [DeSyDe]({{ page.desyde-url }}), this project will be discontinued.


## [f2cc]({{ page.f2cc-url }})

> *Activities*: **Synthesis**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/f2cc"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[f2cc]({{ page.f2cc-url }}) is a synthesis tool for GPGPUs. It takes an *application model* (intermediate representation of a ForSyDe process network dumped by [ForSyDe-SystemC]({{ page.forsyde-systemc-url }})), it identifies parallel sections, performs a *heuristic mapping* based on a platform model, and synthesizes either CUDA or sequential C code. It is implemented as a C++ project and is shipped as a [binary application](https://github.com/forsyde/f2cc).



## [ForSyDe-Deep]({{ page.forsyde-deep-url }})

> *Activities*: **Modeling, Simulation, Synthesis**

<a href="https://travis-ci.org/forsyde/forsyde-deep"><img src="https://travis-ci.org/forsyde/forsyde-deep.svg?branch=master" alt="Build status"></a>&emsp;
<a href="https://github.com/forsyde/forsyde-deep"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[ForSyDe-Deep]({{ page.forsyde-deep-url }}) is the deep-embedded counterpart of [ForSyDe-Shallow]({{ page.forsyde-shallow-url }}). It uses Haskell's type system to represent process networks as netlists which can be parsed and either simulated or compiled. It currently synthesizes a subset of the synchronous MoC into VHDL code and deploys it on an FPGA board. It is shipped as a set of Haskell [libraries](https://github.com/forsyde/forsyde-deep) for modeling.

## [ForSyDe-Eclipse]({{ page.forsyde-eclipse-url }})

> *Activities*: **Modeling, Visualization, Synthesis**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-eclipse"><img src="https://travis-ci.org/forsyde/forsyde-eclipse.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/ForSyDe-Eclipse"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[ForSyDe-Eclipse]({{ page.forsyde-eclipse-url }}) uses the model-driven engineering solutions provided by the Eclipse Modeling Framework (EMF) such as graphical modeling, model transformation and code generation to implement and facilitate ForSyDe modeling and design flows.


## [Reactive GPAC]({{ page.forsyde-gpac-url }})

> *Activities*: **Modeling, Simulation**

<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/reactive-gpac"><img src="/assets/images/on-hold.svg" alt="Development status"></a> 

[Reactive GPAC]({{ page.forsyde-gpac-url }}) is the newest addition to the ForSyDe ecosystem. Inspired from [functional reactive programming](https://en.wikipedia.org/wiki/Functional_reactive_programming), it approaches system design from a different perspective than the previous frameworks. Focusing mainly on continuous time systems, it describes a General Purpose Analog Computer (GPAC) as a set of basic blocks capable of deriving commonly used analog systems. 

