# Frontend & 3D Digital Twin Development Guide

**Branch:** `feature/frontend-3d`  
**Owner:** L. Harsha Vardhan  
**Role:** Frontend & 3D Digital Twin

## 1. Purpose of this branch

This branch turns the backend and navigation capabilities into an understandable interactive campus experience.

The goal is not just to display a 3D model. A useful Digital Twin should connect:
- campus locations;
- search;
- floor/block selection;
- location information;
- route visualization;
- emergency-route visualization;
- backend data.

## 2. Work to complete

### Interface
Build screens/components for:
- campus landing view;
- search/destination input;
- block selection;
- floor selection;
- location details;
- route result;
- navigation instructions;
- emergency exit guidance.

### 3D Digital Twin
Represent the campus as:
- blocks;
- floors;
- rooms/areas;
- important facilities;
- stairs/lifts;
- entrances/exits.

The model should be navigable and organized so individual floors or blocks can be selected.

### Route visualization
When the backend returns a route:
- identify the relevant block/floor;
- highlight the route;
- show transitions between floors;
- show readable navigation steps;
- keep the route synchronized with the selected destination.

## 3. How to do the work

### Step 1 — Build a 2D functional UI first
Before 3D, make sure the user can:
1. select/search a destination;
2. request a route;
3. receive a route from the backend;
4. understand the result.

### Step 2 — Connect the API
Define the exact request/response contract with the backend and navigation branches.

Do not hard-code routes in the frontend.

### Step 3 — Add the 3D scene
Start with a simplified block/floor model. Use verified campus dimensions/layout information when available.

### Step 4 — Add interaction
Implement:
- block selection;
- floor selection;
- location selection;
- camera movement;
- route highlighting.

### Step 5 — Add information panels
Clicking a known facility should show its verified name, type, floor, and useful description.

### Step 6 — Integrate route output
The frontend should consume structured backend route data rather than calculate shortest paths itself.

## 4. Tools to use

**Recommended**
- VS Code
- Git + GitHub
- React
- Vite
- JavaScript/TypeScript
- Three.js
- React Three Fiber if the team chooses React-based 3D
- HTML/CSS for layout and accessibility

**Useful**
- Blender — create/clean 3D assets when necessary
- Browser developer tools — inspect requests and rendering
- Figma — optional UI planning

Do not spend the first weeks making a beautiful 3D model while the API contract is unknown. Functional navigation comes first.

## 5. Data accuracy rule

The campus is a real place, so visual and location information must be traceable to supplied/verified campus material.

Until the team has verified campus information:
- use demo labels;
- clearly mark synthetic data;
- do not claim an invented room is actually present;
- do not invent emergency exits.

## 6. AI-assisted development rules

Use AI to:
- explain React/Three.js concepts;
- generate small UI components;
- debug rendering/API issues;
- suggest component structure;
- review accessibility and state management.

Do not paste a complete generated frontend without understanding the component tree, state, API calls, and rendering flow.

## 7. Definition of done

A feature is complete when:
- it works with the real backend contract;
- loading/error states exist;
- the UI does not rely on hard-coded route results;
- 3D interaction is understandable;
- location information is traceable;
- route visualization corresponds to backend output;
- the owner can explain the implementation.

## 8. Commit style

```
feat: create campus navigation interface
feat: connect frontend to location API
feat: add block and floor selection
feat: create 3d campus scene
feat: visualize navigation route
test: handle frontend API errors
```

Keep 3D asset work and application logic organized so they can be reviewed separately.
