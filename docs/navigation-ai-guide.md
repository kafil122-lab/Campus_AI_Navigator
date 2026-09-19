# Navigation & AI Development Guide

**Branch:** `feature/navigation-ai`  
**Owner:** Sk. Mohammad Kafil  
**Role:** Vice Project Coordinator — Navigation & AI Integration

## 1. Purpose of this branch

This branch builds the intelligence that turns campus locations into usable routes and later understands natural-language navigation requests.

The most important design rule is:

**AI interprets the request; the deterministic navigation engine calculates the route.**

For example:

**"How do I get from the main gate to the library?"**

should become:

`source = MAIN_GATE`  
`destination = LIBRARY`

Then Dijkstra or A* calculates the actual route.

Do not ask an LLM to invent the route.

## 2. Work to complete

### Navigation engine
Build:
- campus graph representation;
- nodes for navigable locations;
- weighted edges for connections;
- Dijkstra shortest path;
- A* pathfinding;
- path reconstruction;
- distance/cost calculation;
- multi-floor transitions;
- unreachable-route handling.

### Algorithm study
Understand before implementing:
- Graphs
- Weighted graphs
- Priority queues
- Dijkstra
- Heuristics
- A*
- Time/space complexity

For A* understand:

**f(n) = g(n) + h(n)**

where:
- `g(n)` = cost already travelled;
- `h(n)` = estimated remaining cost;
- `f(n)` = total estimated cost.

Compare Dijkstra and A* using measurable values such as route cost, execution time, and nodes explored.

### AI/NLP layer
Build in stages:

1. Exact location matching.
2. Alias matching.
3. Normalized natural-language phrases.
4. Structured intent extraction.
5. Optional LLM-assisted interpretation.
6. Validation before sending the result to navigation.

Examples of aliases:
- "library" → `LIBRARY`
- "central library" → `LIBRARY`
- "computer lab" → the verified corresponding lab ID

Never create aliases for locations that have not been verified.

## 3. How to do the work

### Step 1 — Build the graph
Convert backend location/connection data into a graph.

### Step 2 — Implement Dijkstra yourself
Use a small graph first. Understand the priority queue and predecessor/path reconstruction before relying on a library abstraction.

### Step 3 — Add A*
Implement a heuristic appropriate to the campus representation. If the campus has no trustworthy coordinates yet, use a clearly defined graph-based heuristic or defer heuristic routing until suitable positional data exists.

### Step 4 — Test algorithms
Create repeatable tests for:
- direct routes;
- multi-step routes;
- same-floor routes;
- multi-floor routes;
- unreachable destinations;
- unknown locations;
- source = destination.

### Step 5 — Add natural-language understanding
Start with deterministic normalization and aliases. Add an AI/LLM layer only after deterministic routing works.

### Step 6 — Connect AI to navigation
The AI layer should output structured data, for example:

```json
{
  "source": "MAIN_GATE",
  "destination": "LIBRARY"
}
```

The navigation engine then calculates the route.

### Step 7 — Return an explainable result
The backend should be able to return the route as structured steps so the frontend can visualize it.

## 4. Tools to use

**Required**
- Python
- VS Code
- Git + GitHub
- NetworkX — graph experimentation/validation
- pytest — algorithm tests
- FastAPI — integration with backend

**Useful**
- Python `heapq` — understand/implement priority-queue based Dijkstra
- Postman/Insomnia — test navigation API
- Jupyter Notebook — small algorithm experiments
- An approved LLM/API later — natural-language interpretation only

Do not make the LLM the source of truth for campus topology or shortest paths.

## 5. AI-assisted coding rules

Use AI to:
- explain algorithms;
- review graph design;
- generate small test cases;
- help debug;
- compare implementation approaches;
- review NLP normalization.

For every AI-generated algorithm, trace at least one route manually and explain the important variables and stopping conditions.

## 6. Definition of done

The branch should eventually provide:
- reliable graph construction;
- Dijkstra;
- A*;
- algorithm comparison;
- multi-floor support;
- clear error handling;
- deterministic tests;
- structured route output;
- natural-language destination mapping;
- documented boundary between AI and deterministic routing.

## 7. Commit style

```
feat: build campus graph
feat: implement dijkstra routing
feat: add astar pathfinding
test: compare dijkstra and A*
feat: add location alias matching
feat: integrate natural language destination parsing
```

Keep algorithm changes separate from unrelated frontend work.
