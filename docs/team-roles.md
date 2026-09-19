# Campus AI Navigator — Brief Team Roles

## Project
**Campus Digital Twin: A 3D Smart Navigation and Information System for College Campus**

Four members share equal technical ownership. Coordinator and vice-coordinator are organizational roles, not technical hierarchy.

| Member | Branch | Primary Role |
|---|---|---|
| Sk. Mohammad Maaz | `feature/backend-data` | Campus Data & Core Backend |
| Sk. Mohammad Kafil | `feature/navigation-ai` | Navigation & AI Integration |
| L. Harsha Vardhan | `feature/frontend-3d` | Frontend & 3D Digital Twin |
| A. Nikhil Hasan | `feature/testing-integration` | Testing, Integration & Documentation |

## Development Structure

`main` = stable/release branch  
`dev` = team integration branch  
`feature/*` = individual technical work

Feature branches should be developed, tested, committed, and reviewed before being merged into `dev`. Stable milestones can later move from `dev` to `main`.

## Team Principle

Every member must learn their own module, understand the complete architecture, write and test code, document important decisions, and be able to explain the work during reviews and viva.

AI tools may assist with learning, design, implementation, debugging, and review. No generated code should be accepted without understanding and testing it.

## Core Architecture

**User → Frontend → Backend API → Navigation/AI Services → Campus Data**

The navigation engine remains deterministic and testable. AI/NLP interprets user requests and maps them to structured campus locations; it does not replace the pathfinding algorithm.
