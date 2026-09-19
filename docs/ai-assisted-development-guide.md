# AI-Assisted Development Guide — No Vibe Coding

## Purpose

This project will use AI as a development assistant while keeping all four members technically capable of explaining and maintaining the code.

## 1. Correct Workflow

Use:

```
Problem
  ↓
Understand
  ↓
Learn concept
  ↓
Design
  ↓
Ask AI for help
  ↓
Implement
  ↓
Test
  ↓
Debug
  ↓
Explain
  ↓
Commit
```

Do not use:

```
Prompt
  ↓
Generate entire project
  ↓
Paste everything
  ↓
Hope it works
```

## 2. Good Uses of AI

AI is useful for:

- Explaining unfamiliar concepts
- Giving small examples
- Reviewing code
- Finding likely bugs
- Suggesting edge cases
- Generating test cases
- Explaining error messages
- Improving documentation
- Comparing implementation approaches

## 3. Bad Uses of AI

Do not ask AI to:

- Invent campus facts
- Invent room locations
- Invent shortest routes
- Replace algorithm understanding
- Generate the complete application blindly
- Hide errors instead of fixing them
- Claim a feature works without testing it

## 4. Five Questions Before Commit

Every developer must answer:

1. What does this code do?
2. Why does it work?
3. What inputs does it expect?
4. What output does it produce?
5. What happens for invalid input?

If the developer cannot answer these, continue learning before committing.

## 5. Prompt Pattern

A good coding prompt contains:

- Context
- Goal
- Existing code
- Constraints
- Expected behavior
- Error/output
- Request for explanation

Example:

> I am implementing Dijkstra for a weighted campus graph in Python. Explain the algorithm first, then show a small implementation that accepts an adjacency-list graph. Do not use NetworkX in the first version. Include two test cases and explain the time complexity.

This is better than:

> Build my navigation system.

## 6. Debugging Pattern

When code fails, provide:

- Error message
- Relevant code
- Expected behavior
- Actual behavior
- Steps already tried

Ask AI to explain the likely cause before asking for a complete replacement.

## 7. Code Review Pattern

Ask:

> Review this function for correctness, edge cases, readability and testability. Do not rewrite it immediately. First identify the problems and explain why they matter.

Then decide which changes to make.

## 8. Team Knowledge Rule

If AI helped one member implement a feature, that member must explain the feature to at least one other team member.

For important shared interfaces, explain them to the whole team.

## 9. Tools

- ChatGPT or another coding assistant
- VS Code
- GitHub
- GitHub Copilot if the team has access and understands the generated code
- Python tooling
- pytest
- Postman
- Browser developer tools

AI tools are optional helpers. Git, tests and source code remain the project's actual engineering foundation.

## 10. Final Principle

The goal is not:

> "AI wrote our project."

The goal is:

> "We designed, implemented, tested and understood our project, using AI to accelerate learning and development."
