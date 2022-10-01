---
layout: default
title: ForSyDe
description: Formal System Design Homepage
isHome: true
---

<p align="center">
	<img width="350px" src="/assets/images/forsyde-logo.svg">
</p>

# Overview

ForSyDe is a methodology with a formal basis for modeling and design of heterogeneous systems-on-chip and cyber-physical systems that has been developed with the following objectives:

 * System design must start at a high level of abstraction. The designer shall focus on functionality, and low-level implementation details shall not be an issue at the design stage;
 * Design methodology must give a solid base for the incorporation of formal methods. This means that verification must be a first class citizen _from the start_;
 * Abstraction gap between specification and implementation must be bridged by formal refinement techniques.


These goals are achieved in practice through an ecosystem of [tools](tools) which are developed in line with scientific [publications](publications.html).
News about ForSyDe realted research and development can be seen in the [news](news) webpage as well as in the [GitHub organization page](https://github.com/forsyde).
 
## Our Name

ForSyDe is officially an acronym for **For**mal **Sy**stem **De**sign.

ForSyDe also resembles with the word _foresight_. According to the [Merriam-Webster](https://www.merriam-webster.com/dictionary/foresight) dictionary

> **foresight** noun  
> fore·​sight ; \ˈfȯr-ˌsīt\
>
> Definition of _foresight_ 
>
> 1. an act or the power of foreseeing : prescience   
>    _Through foresight she could tell what the outcome would be._
>
> 2. provident care : prudence  
>    _had the foresight to invest his money wisely_
>
> 3. an act of looking forward  
>    also : a view forward

This definition captures the essence of our vision: formal design should pave a clear way towards a correct implementation. Through a formal model a designer can thus _foresee_ the desired system realization. This is also the story behind our logo.
	
## Our Vision

ForSyDe envisions a correct-by-construction design flow by combining:

 * Modelling framework based on theory of models of computation;
 * Predictable platforms providing guarantees for extra functional properties.

The design flow can be sketched as below:

<p align="center">
	<img src="/assets/images/forsyde-design-flow.svg">
</p>

The key components of the design flow are:

 * **Formally analysable application** models based on a formal foundation to enable formal analysis and reasoning;
 * **Predictable platforms** providing service guarantees;
 * **Analysis methods** enabling powerful design tools;
 * **Design entry language** based on the formal foundation enabling
   - Simulation of the application model;
   - Automatic abstraction of formal analysable model.

# Tools

Visit the [Tools](tools) page for our current portfolio of tools supporting this design process and links to further documentation, and our [GitHub organization page](https://github.com/forsyde) for a list with all projects published under the ForSyDe umbrella. Among them we highlight:

* [ForSyDe-Shallow](forsyde-shallow): a shallow-EDSL capturing the main modeling concepts of ForSyDe.
* [ForSyDe-Deep](forsyde-deep): a deep-embedded EDSL which can synthesize a subset of ForSyDe models down to VHDL.
* [ForSyDe-Atom](forsyde-atom): a shallow-EDSL which extends the ForSyDe modeling scope with concepts like "layers" and "atoms".
* [ForSyDe-SystemC](ForSyDe-SystemC): is the SystemC embedding of ForSyDe, which uses the host language for both simulation, structure parsing and C code extraction.
* [DeSyDe](https://github.com/forsyde/DeSyDe) the previous design space exploration tool in the ForSyDe design flow. It is based on constraint programming and provides certificates of feasibility and optimality for a a design.
* [DeSyDe](https://github.com/forsyde/IDeSyDe) the current design space exploration tool in ForSyDe design flow. It is based on the concept of design space identification in order to systematically combine and extend different design space exploration scenarios without loss of efficiency.
