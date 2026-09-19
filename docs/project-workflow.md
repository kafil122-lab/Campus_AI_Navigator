# Campus AI Navigator — Team Development Workflow

## 1. Project Purpose

**Official project title:** Campus Digital Twin: A 3D Smart Navigation and Information System for College Campus

The project combines four technical areas:

1. Campus data and backend services
2. Navigation algorithms
3. Web frontend and 3D digital twin
4. Testing, integration and documentation

The approved project requirements remain the foundation. AI is an enhancement layer for natural-language location understanding and route explanation; it must not replace deterministic navigation.

## 2. Branch Structure

```
main
  ^
  | stable releases
  |
dev
  | integration branch
  +-- feature/backend-data
  +-- feature/navigation-ai
  +-- feature/frontend-3d
  +-- feature/testing-integration
```

### Branch responsibilities

- `main`: stable, demo-ready code only.
- `dev`: combined development version used for integration.
- `feature/backend-data`: Maaz's backend/data work.
- `feature/navigation-ai`: Kafil's navigation/AI work.
- `feature/frontend-3d`: Harsha's frontend/3D work.
- `feature/testing-integration`: Nikhil's testing/integration work.

Do not develop directly on `main`.

## 3. Normal Work Cycle

```
Task
  ↓
Understand the requirement
  ↓
Learn the required concept
  ↓
Design before coding
  ↓
Implement a small change
  ↓
Run tests / manual checks
  ↓
Explain the code to another member
  ↓
Commit
  ↓
Push feature branch
  ↓
Pull Request → dev
  ↓
Review + test
  ↓
Merge to dev
  ↓
Stable milestone → main
```

## 4. Commit Rules

Use small, meaningful commits.

Examples:

- `docs: add campus data schema guide`
- `feat: implement location service`
- `feat: add dijkstra navigation`
- `feat: add natural language destination parser`
- `test: add multi-floor route cases`
- `fix: handle unknown destination`

Avoid messages such as `update`, `changes`, `final`, or `working code`.

## 5. Pull Request Rules

Feature branches should normally target `dev`, not `main`.

A PR should contain:

- What was changed
- Why it was changed
- How it was tested
- Known limitations
- Screenshots or API examples when useful

Reviewers should check correctness, readability, tests and whether the change belongs to the correct module.

## 6. Keeping Branches Synchronized

Before starting substantial work, update the feature branch from the latest `dev`.

The important idea is:

```
dev → feature branch → work → PR → dev
```

If another member's work changes an interface your branch depends on, coordinate before changing your own design.

## 7. Definition of Done

A task is not complete merely because the code runs.

A task is done when:

- The requirement is understood.
- The implementation works.
- Tests or meaningful manual checks exist.
- Error cases are considered.
- The code is documented where necessary.
- The responsible member can explain the implementation.
- The change is committed with a meaningful message.
- The feature branch is ready for review.

## 8. AI-Assisted Development Rule

AI can help with:

- Explaining concepts
- Suggesting implementation approaches
- Generating small code examples
- Debugging
- Writing tests
- Reviewing code
- Improving documentation

AI must not be used as:

- A replacement for understanding
- A source of unverified campus facts
- A reason to paste an entire generated project blindly
- A replacement for algorithm knowledge

Before accepting AI-generated code, the member must be able to answer:

1. What does this code do?
2. Why was this approach selected?
3. What are its inputs?
4. What are its outputs?
5. What happens when the input is invalid?

## 9. Core Development Tools

### Required

- Git
- GitHub
- VS Code
- Python
- FastAPI
- NetworkX
- pytest
- JSON

### Frontend / 3D

- HTML/CSS/JavaScript fundamentals
- React later if the team chooses it
- Three.js for browser 3D
- Blender for preparing 3D assets

### Testing / API

- pytest
- Postman or an equivalent API client
- Browser developer tools

### Planning / diagrams

- draw.io / diagrams.net
- GitHub Issues and Projects

### AI assistance

- ChatGPT or another approved coding assistant
- Use AI for explanation, small implementations, debugging and review
- Keep the final design understandable by the team

## 10. Communication Rule

When one member changes an API, data format or shared interface, document the change and inform the affected members before they build on an outdated assumption.

## 11. Integration Principle

The team should integrate continuously rather than waiting until the final week.

Recommended order:

1. Campus data
2. Graph representation
3. Dijkstra
4. A*
5. Backend API
6. Basic frontend
7. 3D digital twin
8. Natural-language destination understanding
9. Emergency-route logic
10. Testing and evaluation

This order prevents the AI or 3D layer from hiding problems in the navigation foundation.
