---
title: Projects
layout: default
permalink: tools.html
top-navbar: true
forsyde-shallow-url: https://github.com/forsyde/forsyde-shallow
forsyde-atom-url: https://github.com/forsyde/forsyde-atom
forsyde-systemc-url: https://github.com/forsyde/ForSyDe-SystemC
forsyde-gpac-url: https://github.com/forsyde/reactive-gpac
desyde-url: https://github.com/forsyde/DeSyDe
f2sdf3-url: https://github.com/forsyde/f2sdf3
forsyde-deep-url: https://github.com/forsyde/forsyde-deep
f2cc-url: https://github.com/forsyde/f2cc
forsyde-latex-url: https://forsyde.github.io/forsyde-latex
f2dot-url: https://github.com/forsyde/f2dot
forsyde-eclipse-url: https://github.com/forsyde/ForSyDe-Eclipse
---

# The ForSyDe Ecosystem

While built to support our [publications](publications.html), the ForSyDe tools create an ecosystem which is aligned to our vision of correct-by-construction system design. These are continuously developed and distributed as [open-source](https://en.wikipedia.org/wiki/Open-source_software) projects, and our developer and user base is growing. This page presents some of the highlighted tools, grouped by their main purpose. 

## Modeling & Simulation

<h4><p>
<a href="{{ page.forsyde-shallow-url }}">ForSyDe-Shallow</a>&emsp;
<a href="https://travis-ci.org/forsyde/forsyde-shallow"><img src="https://travis-ci.org/forsyde/forsyde-shallow.svg?branch=master" alt="Build status"></a>&emsp; 
<a href="https://github.com/forsyde/forsyde-shallow"><img src="/assets/images/active.svg" alt="Deveopment status"></a> 
</p></h4>

[ForSyDe-Shallow]({{ page.forsyde-shallow-url }}) is a formal framework for modeling and simulating heterogeneous and cyber-physical systems as networks of MoC-bound processes. It is implemented as a shallow-embedded domain speciffic language (EDSL) in the functional programming language [Haskell](https://www.haskell.org/) and is shipped as a set of Haskell [libraries](https://github.com/forsyde/forsyde-shallow) and [examples](https://github.com/forsyde/forsyde-shallow-examples).


<h4><p>
<a  href="{{ page.forsyde-atom-url }}">ForSyDe-Atom</a>&emsp;
<a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; 
<a href="https://github.com/forsyde/forsyde-atom"><img src="/assets/images/active.svg" alt="Deveopment status"></a> 
</p></h4>

[ForSyDe-Atom]({{ page.forsyde-atom-url }}) is a spin-off from [ForSyDe-Shallow]({{ page.forsyde-shallow-url }}) which further explores the power of functional programming as a system design paradigm. Apart from timing behavior, it enables designers to capture other extra-functional properties (e.g. structured parallelism, control behavior) by enforcing a design methodology of systems as [*interacting layers*](https://forsyde.github.io/forsyde-latex/assets/svg/example-pictures-layered.svg). <!-- Each layer is an environment which captures the semantics of an extra-functional concern as a set of indivisible building blocks called *atoms*. Furthermore, it provides libraries of common building blocks in cyber-physical system design blocks, described as compositional *patterns* of atoms. -->
Like its parent project, it is implemented as a shallow-embedded domain speciffic language (EDSL) in the functional programming language [Haskell](https://www.haskell.org/) and is shipped as a set of Haskell [libraries](https://github.com/forsyde/forsyde-atom) and [examples](https://github.com/forsyde/forsyde-atom-examples).


<h4><p>
<a  href="{{ page.forsyde-systemc-url }}">ForSyDe-SystemC</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/ForSyDe-SystemC"><img src="/assets/images/on-hold.svg" alt="Deveopment status"></a> 
</p></h4>

[ForSyDe-SystemC]({{ page.forsyde-systemc-url }}) is another modeling framework for heterogeneous systems based on the theory of MoCs. Apart from using the host language for simulation purpose, it uses the concept of *introspection* to dump structural data into an intermediate representation which can be fed to DSE and synthesis tools. It is implemented as a shallow-embedded domain speciffic language (EDSL) in the IEEE standard language [SystemC](http://www.accellera.org/downloads/standards/systemc) and is shipped as a set of C++ [header libraries](https://github.com/forsyde/ForSyDe-Systemc) and [demonstrators](https://github.com/forsyde/forsyde-systemc-demonstrators).

<h4><p>
<a  href="{{ page.forsyde-gpac-url }}">Reactive GPAC</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/reactive-gpac"><img src="/assets/images/active.svg" alt="Deveopment status"></a> 
</p></h4>

[Reactive GPAC]({{ page.forsyde-gpac-url }}) is the newest addition to the ForSyDe ecosystem. Inspired from [functional reactive programming](https://en.wikipedia.org/wiki/Functional_reactive_programming), it approaches system design from a different perspective than the previous frameworks. Focusing mainly on continuous time systems, it describes a General Purpose Analog Computer (GPAC) as a set of basic blocks capable of deriving commonly used analog systems. 

## Transformation & Design Space Exploration

<h4><p>
<a  href="{{ page.desyde-url }}">DeSyDe</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/DeSyDe"><img src="/assets/images/active.svg" alt="Deveopment status"></a> 
</p></h4>

[DeSyDe]({{ page.desyde-url }}) is the main design space exploration (DSE) tool in the ForSyDe ecosystem, based on constraint programming techniqes. It takes a set of *application models* (e.g. [SDF3 graphs](http://www.es.ele.tue.nl/sdf3/), periodic tasks), a *platform model* (e.g. TDMA-bus or TDN-NoC based multiprocessor systems), a set of *constraints* and *optimization criteria* (e.g. throughput, area, monetary cost, power consumption), and explores the full design space generated to find an optimal or satisfying mapping. It is implemented as a C++ project using [GeCode](http://www.gecode.org/) as the main CP solver, and is shipped as a [binary application](https://github.com/forsyde/DeSyDe).

<h4><p>
<a  href="{{ page.f2sdf3-url }}">f2sdf3</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/f2sdf3"><img src="/assets/images/on-hold.svg" alt="Deveopment status"></a> 
</p></h4>

[f2sdf3]({{ page.f2sdf3-url }}) is an XSLT script for transforming the intermediate representations dumped by [ForSyDe-SystemC]({{ page.forsyde-systemc-url }}) into [SDF3 graphs](http://www.es.ele.tue.nl/sdf3/) representations, to be further fed to [DeSyDe]({{ page.desyde-url }}). Once the functionality is embedded into [DeSyDe]({{ page.desyde-url }}), this project will be discontinued.

## Synthesis & Compilation

<h4><p>
<a  href="{{ page.forsyde-deep-url }}">ForSyDe-Deep</a>&emsp;
<a href="https://travis-ci.org/forsyde/forsyde-deep"><img src="https://travis-ci.org/forsyde/forsyde-deep.svg?branch=master" alt="Build status"></a>&emsp;
<a href="https://github.com/forsyde/forsyde-deep"><img src="/assets/images/active.svg" alt="Deveopment status"></a> 
</p></h4>


<h4><p>
<a  href="{{ page.f2cc-url }}">f2cc</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-atom"><img src="https://travis-ci.org/forsyde/forsyde-atom.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/f2cc"><img src="/assets/images/on-hold.svg" alt="Deveopment status"></a> 
</p></h4>

## Visualization & User Interface


<h4><p>
<a  href="{{ page.forsyde-latex-url }}">ForSyDe-LaTeX</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-latex"><img src="https://travis-ci.org/forsyde/forsyde-latex.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/forsyde-latex"><img src="/assets/images/active.svg" alt="Deveopment status"></a> 
</p></h4>

<h4><p>
<a  href="{{ page.f2dot-url }}">f2dot</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/f2dot"><img src="https://travis-ci.org/forsyde/f2dot.svg?branch=master" alt="Build status"></a>&emsp;  -->
<a href="https://github.com/forsyde/f2dot"><img src="/assets/images/on-hold.svg" alt="Deveopment status"></a> 
</p></h4>


<h4><p>
<a  href="{{ page.forsyde-eclipse-url }}">ForSyDe-Eclipse</a>&emsp;
<!-- <a href="https://travis-ci.org/forsyde/forsyde-eclipse"><img src="https://travis-ci.org/forsyde/forsyde-eclipse.svg?branch=master" alt="Build status"></a>&emsp; --> 
<a href="https://github.com/forsyde/ForSyDe-Eclipse"><img src="/assets/images/on-hold.svg" alt="Deveopment status"></a> 
</p></h4>
