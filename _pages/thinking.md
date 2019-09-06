= Modeling and Thinking in ForSyDe =
This mini-tutorial provides the readers with a flavor of how to think about and model systems in !ForSyDe using a small example.
The tutorial is tried to be abstract but modeling details and possible implementation code is provided wherever needed to provide a more realistic feeling of how different concepts are put together in action.

== Description of a Bit Error Rate Logger ==
Our running example is a simple logger system in a digital transceiver system which consists of a module that compares the last bit error rate (BER) measured during the previous cycle with a predefined threshold.
The following figure shows a scenario where 10 bits are transmitted out of which 3 are faulty after receiving.
Hence, the BER is 0.3
{{{
#!div style="text-align: center"
{{{#!graphviz
digraph {
    
    T [shape=record, label="0|<sb0> 0|1|0|<sb1> 1|0|1|0|<sb2> 1|1"];
    R [shape=record, label="0|<rb0> 1|1|0|<rb1> 0|0|1|0|<rb2> 0|1"];
    T -> R [headport=w tailport=w label="Transmit"];
    T:sb0 -> R:rb0 [style=dashed color=red];
    T:sb1 -> R:rb1 [style=dashed color=red];
    T:sb2 -> R:rb2 [style=dashed color=red];
}
}}}
}}}
If the error rate is higher than the threshold, the system increments a counter indicating the number of faulty cycles. 
The current value of the counter (faulty cycles) is sent to the next module for further processing.


== Abstract Functional Models ==
ForSyDe starts with abstract and functional modeling of systems.
- An ''abstract'' model leaves out all implementation details which has nothing to do with correct behavior of a system.
  These details are usually introduced through the design flow.
  For example, in a non-real-time system model, we might not want to know the execution time of each process in the fina implementation.
- A ''functional'' model here means a model in which no platform-specific information is included, whether information about the platform is abstract or detailed.
  For example, it is not yet decided that a process is going to be implemented as a software running on a CPU, MPSoC, or even synthesized as hardware.
  The communication protocol standards are also out of the scope of interest in functional models.
It is worth noting that the implementation details and platform-specific information can later be added to the models.
ForSyDe is able to capture models in different levels of abstraction.

In the above BER example, it is not yet determined whether the BER counter module is going to be implemented in hardware or software; nor is its communication protocol interface.

== System Structure ==
The first, important step in developing ForSyDe models is to represent the system structure as a process network.
A ForSyDe process network is a set of processes that communicate and synchronize ''only'' using signals.
Signals are uni-directional communication media which act like FIFO buffers with blocking read and write.
A possible ForSyDe network which can represent the above (sub-)system description is represented in the following figure:
{{{
#!div style="text-align: center"
{{{#!graphviz
digraph {
    rankdir=LR;
    node [shape=box style=rounded ]
    ber_source1 -> ber_counter1 [label=ber ]
    ber_counter1 -> err_log1 [label=err_count ]
}
}}}
}}}

== Semantics as Models of Computation ==
The specification of a system model structured like the process network of the above example, is not yet complete and can be associated with different execution semantics.
With the same process network a designer might have an analog electronic system in mind where a dense model of time is appropriate while another designer would like express a digital system where execution happens in discrete time steps.
One designer may need to express a synchronous system where all processes are executed together on clock ticks, while the other needs to express only the causal dependencies between the processes as a dataflow graph and leave the exact scheduling to the later stages of the design flow.

''[ModelsOfComputation Models of computation (MoCs)]'' serve the purpose of introducing precise execution semantics to a system model.
!MoCs define how the processes are executed and synchronized together in different time abstractions.
Originally four main !MoCs are defined for ForSyDe:
1. **Untimed (UT) MoC**, where usually only the causal dependencies between the processes are captured and the exact execution time of the system elements are not defined. Most of the dataflow !MoCs such as synchronous dataflow (SDF), cyclo-static dataflow (CSDF), dynamic dataflow (DDF) are special cases of this MoC.
1. **Synchronous (SY) MoC**, where the lifetime of system is divided into a set of instances or clock ticks. The execution of processes and their communication is assumed to be virtually infinitely fast. The foundations of digital hardware design and synchronous languages such as Esterel and Lustre are based on the synchronous MoC.
1. **Discrete-Time (DT) MoC**, which is used to express a less abstract time model, where there is closer relation to the physical time. Discrete-event systems are related to the DT MoC. Classical real-time specifications are best described using this MoC.
1. **Continuous-Time (CT) MoC**, which has a dense model of time and is appropriate for equation-based system specification. Analog hardware is best captured using the CT MoC.

While these !MoCshave a formal foundation with precise semantics, they are extended, refined, and implemented in different ways based on requirements of the context in which they are being used.

In our BER logger system, there might be timing requirements on the system.
For example, the error log needs to be updated every 5^ms^.
The designer might decide that this timing is not part of the correct functional behavior of the system and hence, express the system with a more abstract time model and express the timing requirement as a design constraint for the design flow which refines and implements this model.
We can choose to use the SY MoC for the system specification where all processes are executed together on each clock tick.
As a result, the 5^ms^ design constraint means that the designer needs to implement the system in such way that the clock ticks every 5^ms^.

== Process Constructors ==
In many similar modeling frameworks, the designer is free to write the code for each process of a system model  in any way she desires, of course with the following restriction: in addition to performing the local computation based on the available inputs, each process must comply with the rules of the MoC to which it belongs.
There are different disadvantages associated with this approach:
- We rely on the designer to respect the rules of the MoC associated with each process. She always needs to remember that for example in the `ber_counter1` process above tokens need to be read from the input buffers before performing the computation and none of the results should not be written to the output buffer before all the computations are finished. Violating these constraints might have severe effects. For example it can result to correct simulation results while the design flow fails with implementing the system correctly.
- The model has a lot of [WikiPedia:Boilerplate_code boilerplate] code. The code which implements actor firing and communication and synchronization among the actors need to be repeated in many places.
- Some of the important properties are not captured explicitly which means that the constructed models are either not suitable for certain analysis methods or sophisticated tools need to be developed in order to extract these properties. In the same  example, the `ber_counter1` process includes an internal state which is the number of counted errors. Such a state is dealt in a special way when synthesizing hardware (a hardware register is generated) or software (considerations when generating code for parallel machines). But if the state is coded manually by the user, it is hard or impossible to imply it in the general case.

ForSyDe addresses this problem using its distinguishing concept of ''process constructors''.
Process constructor are ''skeletons'' or ''templates'' which the designer must choose from a library and customize it in order to construct processes.
This customization is done by passing a set of ''functions'' or ''values'' to the process constructor.

As an example, ForSyDe defines a process constructor named `mooreSY` which is used to implement a Moore machine in the synchronous model of computation of ForSyDe.
It requires the user to pass three parameters to it in order to create a process:
- the next state function which takes the current state and the current input, and produces the next output;
- the output decoding function, which takes the current state and returns the output of the process in each cycle; and
- an initial state, which the state value at the beginning of the execution.
{{{
#!div style="text-align: center"
{{{#!graphviz
digraph {
    rankdir=LR;compound=true;
    node [shape=box style=rounded ]
    subgraph cluster1{
        rankdir=TB;
        {ns_func -> od_func [style=invis]}
        init_val;
        color=black;
        shape=box;
        style=rounded;
        label="mooreSY";
    }
    source -> ns_func [lhead=cluster1]
    od_func -> sink [ltail=cluster1]
    source [style=invis]
    sink [style=invis]
}
}}}
}}}

{{{
#!div style="text-align: center"
{{{#!graphviz
digraph {
    rankdir=LR;
    node [shape=box style=rounded ]
    subgraph cluster1{
        rankdir=TB;
        ns_func -> state
        state -> ns_func [headport=w tailport=e]
        state -> od_func
        color=black;
        style=dashed;
        label="a Moore machine";
    }
    source -> ns_func
    od_func -> sink
    source [style=invis]
    sink [style=invis]
}
}}}
}}}
Thus, the process constructor can be seen as a [WikiPedia:Higher-order_function higher-order function] which might take functions as input and return a process (which in turn can be seen as a function over the history of input/output signals) as its result.

We can use the `mooreSY` process constructor to construct the `ber_counter1` process of our example in the following way:
the next-state function compares the first input (BER) with a threshold and decides to increment the second input (current state) or not.
The output-decoding function in this example is simply the identity function and the initial state is 0, indicating no detected errors at the beginning of system operation.

{{{
ber_ns_func (input_val, current_state)=
  if input_val>threshold then
    return current_state+1
  else
    return current_state
}}}

{{{
ber_od_func (current_state)=
  return current_state
}}}

{{{
ber_counter1 = mooreSY(ber_ns_func, ber_od_func, 0)
}}}

The constructed `ber_counter1` process complies with the rules of the SY MoC and correctly implements the semantics of a Moore machine.

== Building Process Networks ==

== Domain Interfaces and Heterogeneous Systems ==

== Transfomations ==
