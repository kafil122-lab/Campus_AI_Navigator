# Campus AI Navigator — Team Roles

## Project
**Campus Digital Twin: A 3D Smart Navigation and Information System for College Campus**

This document defines equal technical ownership for the four-member team. The coordinator and vice coordinator roles are organizational responsibilities, not a hierarchy of technical importance.

## Member 1 — Sk. Mohammad Maaz
**Project Coordinator — Campus Data & Core Backend**

Responsibilities:
- Campus buildings, floors, rooms, facilities and connections data model
- Structured campus dataset
- Backend foundation and location APIs
- Data validation and backend integration

## Member 2 — Sk. Mohammad Kafil
**Vice Project Coordinator — Navigation & AI Integration**

Responsibilities:
- Campus graph representation
- Dijkstra shortest-path implementation
- A* pathfinding and algorithm comparison
- Natural-language destination understanding
- AI-to-navigation integration
- Technical coordination across modules

## Member 3 — L. Harsha Vardhan
**Frontend & 3D Digital Twin**

Responsibilities:
- Web interface
- Interactive campus map
- 3D building/floor visualization
- Route visualization
- Frontend-to-backend integration

## Member 4 — A. Nikhil Hasan
**Testing, Integration & Documentation**

Responsibilities:
- API and system testing
- Navigation edge-case testing
- Error handling and validation
- Performance measurements
- Technical documentation and deployment support

## Team rule
Every member must understand the complete system architecture, write code, test their work, document decisions, and explain their contribution during reviews. AI is used as an assistant for learning, implementation, debugging and review—not as a replacement for understanding.

## Core architecture

User → Frontend → Backend API → AI/NLP + Navigation Engine → Campus Data

The navigation engine remains deterministic and testable. AI/NLP interprets natural-language requests and maps them to structured locations; it does not replace the shortest-path algorithm.
