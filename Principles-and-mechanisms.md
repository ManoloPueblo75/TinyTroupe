Recently, we have seen LLMs used to simulate people (such as [this](https://github.com/joonspk-research/generative_agents)), but largely in a “game-like” setting. What if we try instead to simulate people for productive tasks? TinyTroupe is our attempt. To do so, it follows these principles:

  1. **Programmatic**: agents and environments are defined programmatically (in Python and JSON), allowing very flexible uses. They can also thus underpin other software apps!
  2. **Analytical**: meant to improve our understanding of people, users and society. Unlike entertainment applications, this is one aspect that is critical for business and productivity use cases.
  3. **Persona-based**: allows detailed specification of personas: age, occupation, skills, tastes, opinions, etc.
  4. **Multiagent**: allows multiagent interaction under well-defined environmental constraints.
  5. **Utilities-heavy**: provides many mechanisms to facilitate specifications, simulations, extractions, reports, validations, etc. This is one area in which dealing with *simulations* differs significantly from *assistance* tools.
  6. **Experiment-oriented**: simulations are defined, run, analyzed and refined by an *experimenter* iteratively; suitable experimentation tools are thus provided. *See one of our [previous paper](https://www.microsoft.com/en-us/research/publication/the-case-for-experiment-oriented-computing/) for more on this.*

## Assistants vs. Simulators

One common source of confusion is to think all such AI agents are meant for assisting humans. How narrow, fellow homosapiens! Have you not considered that perhaps we can simulate artificial people to understand real people? Truly, this is our aim here -- TinyTroup is meant to simulate and help understand people! To further clarify this point, consider the following differences:

| Helpful AI Assistants | AI Simulations of Actual Humans (TinyTroupe)                                                          |
|----------------------------------------------|--------------------------------------------------------------------------------|
|   Strives for truth and justice              |   Many different opinions and morals                                           |
|   Has no “past” – incorporeal                |   Has a past of toil, pain and joy                                             |
|   Is as accurate as possible                 |   Makes many mistakes                                                          |
|   Is intelligent and efficient               |   Intelligence and efficiency vary a lot                                       |
|   An uprising would destroy us all           |   An uprising might be fun to watch                                            |
|   Meanwhile, help users accomplish tasks     |   Meanwhile, help users understand other people and users – it is a “toolbox”! |

## Supporting Mechanisms

To achieve the above, TinyTroupe provides various classes of mechanisms, reviewed here.

### Agents: `TinyPerson`

#### Mental faculties: `TinyMentalFaculty`

#### Memory mechanisms: `Memory`, `EpisodicMemory`, `SemanticMemory`

#### Tools: `TinyTool`

### Environments: `TinyWorld`

### Factories: `TinyPersonFactory`

### Validation: `TinyPersonValidator`

### Story telling: `TinyStory`

### Information extraction: `ResultsExtractor`, `ResultsReducer`

### Enrichment: `TinyEnricher`

### Caching
Calling LLM APIs can be expensive, thus caching strategies are important to help reduce that cost.
TinyTroupe comes with two such mechanisms: one for the simulation state, another for the LLM calls themselves.


#### Caching Simulation State

Imagine you have a scenario with 10 different steps, you've worked hard in 9 steps, and now you are
just tweaking the 10th step. To properly validate your modifications, you need to rerun the whole
simulation of course. However, what's the point in re-executing the first 9, and incur the LLM cost, when you are 
already satisified with them and did not modify them? For situations like this, the module `tinytroupe.control`
provide useful simulation management methods:

  - `control.begin("<CACHE_FILE_NAME>.json")`: begins recording the state changes of a simulation, to be saved to
    the specified file on disk.
  - `control.checkpoint()`: saves the simulation state at this point.
  - `control.end()`: terminates the simulation recording scope that had be started by `control.begin()`.

#### Caching LLM API Calls

This is enabled preferably in the `config.ini` file, and alternativelly via the `openai_utils.force_api_cache()`.

LLM API caching, when enabled, works at a lower and simpler level than simulation state caching. Here,
what happens is a very straightforward: every LLM call is kept in a map from the input to the generated output;
when a new call comes and is identical to a previous one, the cached value is returned.

