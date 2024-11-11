LLM-based agents and multiagent systems are becoming popular ways of structuring applications. Understandably, current multiagent programming libraries and frameworks focus on problem-solving (e.g., programming) and assistive AI (e.g., chatbots or copilots). TinyTroupe, however, is a multiagent simulation library that focuses on simulation and experimentation, to support imagination enhancement and business insights. This brings unique benefits and requirements, which do not come naturally to existing problem-solving/assistive approaches. Below we compare (rather roughly) TinyTroupe with other LLM-based multiagent tools along some important dimensions:



| Aspect         | TinyTroupe                                   | [Autogen](https://microsoft.github.io/autogen)                                      | [Crew AI](https://docs.crewai.com/)
|----------------|----------------------------------------------|----------------------------------------------|----------------------------------------------|
| **Programmatic** | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| **Agent persona** | :heavy_check_mark: Highly detailed | :heavy_check_mark: Short system message | :heavy_check_mark: Short background story |
| **Composable cognitive capabilities** | :heavy_check_mark: mental faculties via `Faculty`| :x: | :x: |
| **Fine-grained cognitive control** | :heavy_check_mark: `TinyAgent` methods like `.think()`, `.internalize_goal()`, etc. | :x: | :x: |
| **Agent population sampling** | :heavy_check_mark: `TinyPersonFactory` | :x: | :x: |
| **Agent validation** | :heavy_check_mark: `TinyPersonValidation` | :x: | :x: | 
| **Environments** | :heavy_check_mark: `TinyWorld`| :heavy_check_mark: Teams | :heavy_check_mark: Crews |
| **Message or interaction protocols** |:x: | :heavy_check_mark: | :heavy_check_mark: Processes |
| **Explicit tasks** |:x: | :heavy_check_mark: | :x: |
| **Agent persistence** | :heavy_check_mark: JSON specifications | :x: | :heavy_check_mark: JSON specifications; pickle |
| **Simulated tools** | :heavy_check_mark: e.g., `TinyWordProcessor` | :x: | :x: |
| **Real-world tools** | :x: (not *yet*) | :heavy_check_mark: | :heavy_check_mark: |
| **Code execution** | :x: | :heavy_check_mark: | :heavy_check_mark: |
| **Simulated time** | :heavy_check_mark: (e.g., granularity of minutes, hours, days, etc.)| :x: | :x: |
| **Simulation steering** | :heavy_check_mark: story-telling via `TinyStory` | :x: | :x: |
| **Human input** | :heavy_check_mark:| :heavy_check_mark:| :heavy_check_mark:|
| **Grounding data support** | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| **Structured information extraction** | `TinyResultsExtractor` and `TinyResultsReducer` | :x: | :x: |
| **Synthtetic data exports** (e.g., Word files) | :heavy_check_mark: `TinyArtifactExporter` | :x: | :heavy_check_mark: Pydantic models |
| **Content enrichment** | :heavy_check_mark: `TinyEnricher` | :x: | :x: |
| **Simulation-optimized caching** | :heavy_check_mark: | :x: | :x: |

As the field matures and the boundaries between simulation and problem-solving/assistive AI blur, it is possible -- maybe probable -- that these two overall stances will converge over time (e.g., via common higher-level abstractions). We hope to both learn from others and contribute original elements to this convergence.

***Note:** The above is a rough and incomplete comparison. It might also contain inacuracies due to both our own ignorance and the fast-paced evolution of the area. We'll update, complete and correct it if needed over time.*