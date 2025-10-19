---
title: State_Machine
description: 
published: true
date: 2025-10-13T00:15:40.462Z
tags: 
editor: markdown
dateCreated: 2025-10-13T00:15:36.506Z
---

This article will show you how to make state machines several different
ways. It assumes a good understanding of the various components and of
electrics in general. Please see the referenced pages if you need more
info. State machines are usually a college-level concept but I will
attempt to present it in a manner that does not require advanced math or
logic. However, it is still an advanced article and not for noobs.

(Authored by [Stanimus](User:Stanimus "wikilink"))

# Introduction to State Machines

A state machine can control different electric elements at one time and
will change them in a certain order, depending on timing and control
inputs. For more details on state machines, see other sources. Because
of the nature of a state machine, there is a wide variety of ways to
design and implement them. This article will certainly NOT try to cover
them all. I will try to cover the ones that are easiest to implement in
SC electrics. If you have questions or specific needs, you may contact
me (assuming I'm available) and I'll try to help.

-----

Every state machine has three basic stages. The first is the input
encoding. This takes all relevant inputs including a clock or counter
and converts them to a format the actual controller requires. It also
must take into consideration the 'initial conditions' of the machine.
The second stage is the actual controller logic. This takes those inputs
and determines what the next state should be. The last stage is the
decoder and just takes the controller output and converts it to the
signals that go to the components that the machine operates. These would
be the doors, lights, spikes, pistons, furniture or whatever, that you
want to affect with this machine.

When designing state machines, you need to clearly lay out what you want
to happen, in what order and/or in response to which inputs. This plan
is your state machine description and is necessary to be able to design
the controller properly.

# Sequential State Machines

The simplest state machine is timing related only and is controlled by a
clock signal. Of course there must be at least one input to get the
machine started. These are called 'sequential' state machines because
the same things happen in the same order, every time it's started. The
description is usually along the lines of: -When started, activate
output-1 -Wait 1/2 second, activate output-2 -Wait 1/2 second,
deactivate output-1 -Wait 2 seconds, deactivate output-2 -End

There are (at least) two ways to implement a sequential state machine.

One typical example is when controlling a series of pistons. The above
sequence might be used to control two pistons, each one assigned to an
output. The 'start' may be the signal from a pressure plate. Since all
changes are made based on timing alone, there are no other inputs except
the clock. This machine may be implemented several different ways in
Survivalcraft.

One way would be by using a series of variable delay gates. This will
work fine unless you run into difficulties. Then it can be tough to make
changes while keeping track of the delays for all the different parts.
Plus, it could take up a lot of space unnecessarily.

Instead, first we will look at using a Memory Bank as the controller:

## Memory Bank Controller

A timing-only sequential state machine can easily use the bank as the
controller stage. Typically you will have a gated clock running a
counter for the controller input.

### Input Stage

There are three steps for the input stage in this machine. First we need
to start the machine, then we need to let it run, then we need to stop
it. Simple - sort of. When we use a bank as the controller stage, it is
easy to use a counter as the core of the input stage. We can control the
counter in different ways - some more complex than others, not all are
useful with every state description, either.

For the first example, I will use a 'constant clock' input stage. In
this design, a clock is applied to a counter and the output of that
counter is the controller stage input, so everything happens at specific
times and in a specific order. The 'start' signal simply connects the
clock to the counter and lets it start counting from '0'. Each value of
the counter specifies a state of the controller. When the machine is
done counting, the clock is disconnected and the counter is (usually)
reset to '0'.

#### Implementation

To implement this design, we need to control the clock going to the
counter. Since there will be separate start and stop signals, we'll need
a latch. The start signal goes to the 'S' input of the latch and the
stop signal goes to the 'R' input. The latch output then goes to an AND
gate which controls the flow of the clock signal. The cheapest way to do
this is to use a NAND gate in the clock generator. By 'cheap' I mean
that it uses the least number of gate. A clock generator then needs only
the NAND and one Adjustable Delay Gate. However, in this case cheapest
is not best. The circuit does not start up properly this way. Instead,
we'll use a NOT in the clock generator and a separate AND gate to
control the clock.

The clock output is fed to the counter and the counter's output is the
state number. Each different value represents a 'different' state of the
machine. The states may not actually be different - that depends on what
the machine is intended to do. In this example, there will be some 'wait
states' - a sequence of states that are identical and just waiting for a
certain amount of time to pass.

The last section needed will disable the clock (via the SR latch) and
reset the counter (if needed). In this simplest case, we can just let
the counter run through its full count and stop. That way we can use the
overflow signal from the counter as the clock disable. The counter will
automatically be at '0' so we don't need anything more to reset it. The
down side to this is only that the machine can't be restarted before the
full count is complete. In many applications, this is a non-issue. This
is a picture of the final input stage circuit:

<div style="overflow:hidden">

![SM_ex1p1.jpg](SM_ex1p1.jpg "SM_ex1p1.jpg")

</div>

The display is the output which goes to the next stage.

## Controller Stage