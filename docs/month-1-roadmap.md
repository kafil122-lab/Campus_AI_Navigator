# Month 1 — Learning and Development Roadmap

## Goal

Build a working technical foundation without vibe coding.

By the end of Month 1, the team should have:

- Structured campus data
- Campus graph
- Dijkstra
- A*
- Backend API
- Basic frontend
- Natural-language destination understanding
- Basic 3D digital twin prototype
- Route visualization
- Emergency-route concept
- Tests
- GitHub workflow
- Documentation

## Daily 1-Hour Method

Every member follows:

- **10 minutes:** learn
- **35 minutes:** build
- **10 minutes:** test
- **5 minutes:** explain what was learned

The explanation step is mandatory. Each member should be able to explain their own code without opening an AI tool.

## Week 1 — Understanding, Data and Graph

### Day 1
Learn:

- Digital twin
- Frontend
- Backend
- API
- Graph
- Navigation
- AI layer

Deliverable: architecture diagram.

### Day 2
Learn Git/GitHub:

- Branch
- Commit
- Push
- Pull
- Pull request
- Merge

Deliverable: understand the team branch workflow.

### Day 3
Define campus data schema.

Deliverable: initial JSON schema/data design.

### Day 4
Learn graph concepts.

Deliverable: hand-drawn or digital campus graph example.

### Day 5
Convert sample campus data into a graph.

Deliverable: graph builder.

### Day 6
Calculate a basic route.

Deliverable: Main Gate → Library style demo using synthetic data.

### Day 7
Review.

Week 1 milestone:

- Data model
- Graph
- Basic route
- Architecture understanding

## Week 2 — Backend and Navigation

### Day 8
Learn HTTP, REST, JSON and API requests.

### Day 9
Build FastAPI endpoints.

Initial endpoints:

- `/health`
- `/locations`
- `/route`

### Day 10
Learn Dijkstra.

### Day 11
Learn A*.

### Day 12
Compare Dijkstra and A*.

Measure:

- Route
- Cost
- Nodes explored
- Execution time

### Day 13
Implement multi-floor connections.

### Day 14
Review and integrate.

Week 2 milestone:

```
Campus data
→ graph
→ Dijkstra/A*
→ backend API
→ tests
```

## Week 3 — Frontend and AI

### Day 15
Learn frontend fundamentals.

### Day 16
Create basic navigation interface.

### Day 17
Connect frontend to backend.

### Day 18
Learn natural-language destination understanding.

### Day 19
Implement deterministic location aliases.

### Day 20
Connect AI/NLP to structured destination resolution.

### Day 21
Test natural-language navigation.

Week 3 milestone:

A user can enter a natural-language request and receive a calculated route.

## Week 4 — 3D, Emergency Guidance and Testing

### Day 22
Design the 3D digital twin.

### Day 23
Implement building/floor selection.

### Day 24
Display location information.

### Day 25
Visualize a calculated route in the 3D scene.

### Day 26
Implement emergency exit guidance using verified campus data and deterministic graph/rules.

### Day 27
Run system and edge-case tests.

### Day 28
Integrate all modules.

### Day 29
Prepare documentation and presentation.

### Day 30
Run the complete demo and record remaining issues.

## Month 1 Definition of Done

The team should be able to demonstrate:

1. A campus dataset.
2. A graph built from that dataset.
3. A shortest route.
4. Dijkstra and A*.
5. A backend API.
6. A basic frontend.
7. Natural-language destination understanding.
8. A basic 3D campus representation.
9. Route visualization.
10. Tests and documented limitations.

## Important Rule

Do not expand the feature list just because an AI tool suggests it.

Finish the core navigation system first. Add advanced AI only when the deterministic foundation is reliable.
