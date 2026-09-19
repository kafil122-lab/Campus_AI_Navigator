# Member 3 Guide — Frontend & 3D Digital Twin

## Owner

**L. Harsha Vardhan**

**Role:** Frontend & 3D Digital Twin

## 1. Main Responsibility

Build the visual interface through which users explore the campus and see routes.

The work includes:

- Web interface
- Campus map
- Building/floor selection
- 3D digital twin
- Location information
- Route visualization
- Backend integration

## 2. Why This Work Is Important

The backend and algorithms can be correct but still be difficult to use.

The frontend turns the technical system into a usable campus navigation application.

The 3D digital twin should communicate:

- Where the user is
- What buildings exist
- Which floor is selected
- Where the destination is
- What route should be followed

## 3. Development Order

Do not begin with a complicated 3D scene.

Build in this order:

```
Basic webpage
   ↓
Location search
   ↓
Backend connection
   ↓
2D/simple campus visualization
   ↓
Building/floor interaction
   ↓
3D digital twin
   ↓
3D route visualization
```

This allows the team to test functionality before visual complexity.

## 4. Frontend Features

Initial interface:

- Search box
- Source selection
- Destination selection
- Building/floor selector
- Location information panel
- Route result
- Error message area

Later:

- Interactive 3D buildings
- Floor visibility
- Highlighted destination
- Route line
- Navigation steps
- Emergency exit display

## 5. 3D Digital Twin

Use a consistent coordinate system.

Each important location should have a mapping between:

- Backend location ID
- Building
- Floor
- 3D coordinates
- Display name

Example:

```
LIBRARY
→ Block A
→ Ground Floor
→ x/y/z coordinates
```

The frontend should not independently invent location IDs. Use the backend/campus dataset as the source of truth.

## 6. 3D Tools

Recommended:

- Three.js
- JavaScript
- HTML/CSS
- React if the team decides to use React
- Blender for preparing reusable 3D assets

Start with simple geometry.

For example:

- Box → building
- Smaller boxes → rooms
- Lines → corridors/routes
- Different vertical levels → floors

Photorealistic graphics are not the goal. Accurate navigation and clear interaction are more important.

## 7. Backend Integration

The frontend should call APIs rather than duplicate backend logic.

Example flow:

```
User selects destination
       ↓
Frontend sends request
       ↓
Backend navigation API
       ↓
Route returned
       ↓
Frontend draws route
```

If the API returns an error, display a useful message instead of silently failing.

## 8. Tools

### Development

- VS Code
- HTML/CSS/JavaScript
- React, if selected
- Three.js

### 3D

- Blender
- Three.js
- glTF/GLB for web-ready assets when appropriate

### Testing

- Browser developer tools
- Postman for API verification
- Manual UI testing

### Planning

- diagrams.net
- Figma can be used for UI wireframes if available

### AI assistance

Use ChatGPT to:

- Explain frontend concepts
- Explain Three.js
- Generate small components
- Debug UI errors
- Review API integration
- Suggest accessibility improvements

Do not ask AI to generate the entire frontend blindly.

## 9. Expected Deliverables

- Basic responsive web interface
- Location search
- Backend integration
- Building/floor selection
- 3D campus prototype
- Location information panel
- Route visualization
- Error states
- Frontend tests/manual test checklist

## 10. Suggested Commit Sequence

```
docs: define frontend architecture
feat: create navigation interface
feat: connect frontend to location API
feat: add building and floor selection
feat: create initial 3d campus scene
feat: map campus locations to 3d coordinates
feat: visualize navigation route
test: verify frontend navigation states
```
