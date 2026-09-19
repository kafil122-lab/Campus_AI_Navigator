# Member 1 Guide — Campus Data & Core Backend

## Owner

**Sk. Mohammad Maaz**

**Role:** Project Coordinator — Campus Data & Core Backend

The coordinator role is organizational. It does not make this member technically senior to the other members.

## 1. Main Responsibility

Build the reliable source of truth for campus information and expose it through backend APIs.

The backend should answer questions such as:

- What buildings exist?
- What floors exist?
- What rooms/facilities exist?
- Where is a location identified?
- What connections exist between locations?
- What information should the frontend display?

## 2. Why This Work Is Important

The digital twin, navigation engine, AI layer and frontend all depend on correct campus data.

Bad data produces:

- Wrong routes
- Missing locations
- Incorrect floor information
- Broken 3D labels
- Incorrect emergency guidance

Therefore, campus data is not just data entry. It is a core engineering component.

## 3. Work To Do

### Phase A — Define the data model

Start with a schema for:

- Campus
- Block
- Floor
- Location
- Facility
- Connection

Example conceptual location:

```json
{
  "id": "LIB-GF",
  "name": "Library",
  "type": "facility",
  "block": "A",
  "floor": 0
}
```

Do not invent real room numbers or connections. Mark temporary values as demo/synthetic data until the team has verified them from campus source material.

### Phase B — Build the dataset

Collect verified information for:

- Blocks
- Floors
- Classrooms
- Labs
- Library
- Canteen
- Seminar halls
- Staff rooms
- Main entrances
- Stairs
- Lifts
- Emergency exits

Record source/verification status for important campus facts.

### Phase C — Build the backend

Use FastAPI.

Initial endpoints:

- `GET /health`
- `GET /locations`
- `GET /locations/{location_id}`
- `GET /buildings`
- `GET /floors/{building_id}`

Later, coordinate with Member 2 for:

- `GET /route` or `POST /route`

### Phase D — Validation

The backend should reject or safely handle:

- Unknown location IDs
- Missing required fields
- Invalid floor values
- Duplicate IDs
- Broken connections

## 4. How To Work

Use this sequence:

```
Campus information
      ↓
Data schema
      ↓
Small verified dataset
      ↓
Validation
      ↓
Backend model/service
      ↓
API endpoint
      ↓
API test
      ↓
Commit
```

Do not start by entering hundreds of locations. First prove the model with a small verified dataset.

## 5. Tools

### Core

- Python
- FastAPI
- Pydantic
- JSON
- VS Code
- Git/GitHub

### Testing

- pytest
- Postman
- FastAPI Swagger/OpenAPI documentation

### Diagrams

- diagrams.net

### AI assistance

Use ChatGPT to:

- Explain FastAPI/Pydantic concepts
- Review schemas
- Generate small validation examples
- Suggest test cases
- Explain backend errors

Do not ask AI to invent the actual college layout.

## 6. Learning Checklist

Before moving forward, understand:

- JSON objects and arrays
- REST API basics
- HTTP GET/POST
- FastAPI routes
- Pydantic models
- Validation
- Python modules
- Exceptions
- Unit testing

## 7. Expected Deliverables

By the end of the first development phase:

- Campus data schema
- Initial verified dataset
- Backend project structure
- Location APIs
- Validation logic
- API tests
- API documentation

## 8. Coordination Points

Coordinate with:

- **Kafil:** graph input format and route API
- **Harsha:** fields needed by the frontend and 3D model
- **Nikhil:** validation and API test cases

Any shared schema change must be communicated before implementation elsewhere.

## 9. Suggested Commit Sequence

```
docs: define campus data schema
feat: add initial campus dataset
feat: create fastapi backend foundation
feat: add location endpoints
test: validate campus location API
fix: handle invalid location requests
```
