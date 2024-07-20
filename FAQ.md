# Frequently Asked Questions

## Q: How does TinyTroupe differs from other LLM-based multiagent tools?

To our knowledge, most, if not all, of currently used LLM-based multiagent tools are primarily meant for the creation of **applications** or **assistants**. That is to say, the multiagent form is merely a way to get to some final result, and whether those agents are actually human-like is not crucial. TinyTroupe, on the other hand, is meant primarily for the simulation of social systems, in which the agents are the main object of interest, and the core aim is to **understand** some situation of interest, instead of implementing some final **application**. Naturally, a system that helps one understands people is itself an application, but of a very special kind.

You can read mora about it on [Principles and mechanisms](https://github.com/microsoft/TinyTroupe/wiki/Principles-and-mechanisms).

## Q: Can I directly use the simulation outputs for serious things?

**No!** This is a highly experimental project, and as such any of its outputs must be fully validated by a human before actually being used for anything that might have effects on the real world.

## Q: So what's the point?

First of all, simulations can be powerful **imagination enhancers** -- for instance, instead of imagining of a customer would do, using our limited brain power, we can delegate this to TinyTroupe, and cover much wider scenarios in a fraction of the time. Hence, one key application is the generation of insights, which can complement the human thought process.

Secondly, *we might* actually succeed in simulating human-like behavior, and if so that would be a significant scientific achievement. Hence, TinyTroupe is also a research platform, in which we and others can try new approaches to this end, for example trying new prompts, memory mechanisms, or other cognitive structures.

## Q: Why should I use TinyTroupe instead of directly prompting an LLM?

While you could provide a detailed description of what you want to an LLM, it would be a long manual task. TinyTroupe makes it quicker and more convenient, for instance, to:
  - Specify agents in detail, and then reuse them in new situations.
  - Make agents communicate more realistically.
  - Give fine grained control to experimenters on several details of the simulation, while providing good defaults elsewhere.
  - Observe the passage of time.
  - Perform all kinds of auxiliary operations, such as extracting structured data from simulation traces.

In other words, TinyTroupe provides an abstraction layer that is meant to make persona-based multiagent simulation easier.