# Member 2 Guide — Navigation & AI Integration

## Owner

**Sk. Mohammad Kafil**

**Role:** Vice Project Coordinator — Navigation & AI Integration

The vice coordinator role is organizational and coordination-focused. It is not a hierarchy over other members.

## 1. Main Responsibility

Build the navigation intelligence of the project.

This includes:

- Campus graph
- Dijkstra shortest path
- A* pathfinding
- Algorithm comparison
- Multi-floor routing
- Natural-language destination understanding
- AI-to-navigation integration

## 2. Why This Work Is Important

The project is not simply a 3D model.

A useful digital twin should be able to answer:

> How do I get from location A to location B?

The route must be calculated by a deterministic navigation engine so that the result can be tested and reproduced.

AI should help understand the user's request, not randomly generate the route.

## 3. Core Architecture

```
User request
   ↓
Natural-language understanding
   ↓
Structured source + destination
   ↓
Navigation engine
   ↓
Campus graph
   ↓
Dijkstra / A*
   ↓
Route
   ↓
Route explanation / frontend visualization
```

Example:

```
"How do I go from the main gate to the library?"
                 ↓
source = MAIN_GATE
destination = LIBRARY
                 ↓
Dijkstra/A*
                 ↓
[MAIN_GATE, BLOCK_A_ENTRANCE, ... , LIBRARY]
```

## 4. Phase A — Learn Graphs

Understand:

- Vertex/node
- Edge
- Weight
- Path
- Connected graph
- Weighted graph
- Adjacency list

Represent locations as graph nodes.

Represent walkable connections as edges.

Possible edge weights:

- Walking distance
- Estimated walking time
- Accessibility cost

Do not mix these meanings without documenting the choice.

## 5. Phase B — Dijkstra

First implement and understand Dijkstra before depending on a library.

Learn:

```
distance[start] = 0
all other distances = infinity

Repeatedly choose the nearest unvisited node
and relax its outgoing edges.
```

Then compare your understanding with a tested implementation using NetworkX.

Record:

- Route
- Total cost
- Nodes explored
- Execution time

## 6. Phase C — A*

Learn:

```
f(n) = g(n) + h(n)
```

Where:

- `g(n)` = cost from start to current node
- `h(n)` = estimated cost from current node to destination
- `f(n)` = total estimated cost

For A*, the heuristic must be chosen carefully.

For the first prototype, document a simple admissible heuristic appropriate to the graph representation. Do not claim A* is faster for every campus route without measurement.

## 7. Phase D — Multi-Floor Navigation

Model:

- Stair connections
- Lift connections
- Floor transitions
- Block transitions

Example:

```
A-101
  ↓ stairs
A-201
  ↓ corridor
A-205
```

A stair or lift should be represented as a connection in the graph, not as an AI-generated instruction.

## 8. Phase E — Natural-Language Destination Understanding

Start with deterministic aliases.

Examples:

```
"library" → LIBRARY
"central library" → LIBRARY
"computer lab" → COMPUTER_LAB
"CSE lab" → COMPUTER_LAB
```

Only after this works should the team add an AI/NLP layer.

The AI layer should produce structured output such as:

```json
{
  "source": "MAIN_GATE",
  "destination": "LIBRARY"
}
```

The navigation engine then validates these IDs and calculates the route.

## 9. AI Safety / Reliability Rule

Never allow an LLM to directly invent:

- Campus rooms
- Floor numbers
- Connections
- Emergency exits
- Distances
- Shortest routes

The model can interpret language, but verified campus data and deterministic algorithms must remain the source of truth.

## 10. Tools

### Programming

- Python
- NetworkX
- FastAPI
- pytest
- VS Code

### Algorithm visualization

- diagrams.net
- Python logging/measurement scripts

### API testing

- Postman
- FastAPI Swagger/OpenAPI

### AI development

- ChatGPT for explanations, implementation review, debugging and test generation
- Optional local model tools later if the team has a reason to run NLP locally

## 11. Evaluation

Do not only show that a route exists.

Measure:

| Metric | Dijkstra | A* |
|---|---:|---:|
| Route found | Yes/No | Yes/No |
| Route cost | value | value |
| Nodes explored | value | value |
| Execution time | value | value |

Use several graph sizes or route pairs when evaluating performance.

## 12. Expected Deliverables

- Graph representation
- Dijkstra implementation
- A* implementation
- Multi-floor connection model
- Algorithm comparison
- Destination alias system
- Natural-language parser/integration
- Navigation API integration
- Navigation tests

## 13. Suggested Commit Sequence

```
docs: define navigation architecture
feat: create campus graph builder
feat: implement dijkstra navigation
test: add dijkstra route cases
feat: implement a-star navigation
test: compare dijkstra and a-star
feat: add multi-floor routing
feat: add destination aliases
feat: integrate natural-language destination parsing
test: add navigation edge cases
```
