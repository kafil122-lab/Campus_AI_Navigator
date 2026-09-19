# Testing & Integration Development Guide

**Branch:** `feature/testing-integration`  
**Owner:** A. Nikhil Hasan  
**Role:** Testing, Integration & Documentation

## 1. Purpose of this branch

This branch makes sure the four technical modules can work together reliably.

Testing is not "checking at the end." It is an engineering module responsible for finding incorrect assumptions, broken contracts, edge cases, regressions, and integration failures.

## 2. Work to complete

### Test strategy
Test at multiple levels:
- unit tests;
- API tests;
- navigation tests;
- integration tests;
- frontend integration checks;
- end-to-end scenarios;
- regression tests.

### Important navigation cases
Verify:
- valid route;
- direct route;
- multi-step route;
- multi-floor route;
- source = destination;
- unknown source;
- unknown destination;
- unreachable destination;
- invalid connection;
- invalid request format.

### Backend/API cases
Verify:
- successful responses;
- validation errors;
- missing fields;
- invalid IDs;
- malformed data;
- stable response structure.

### Integration cases
Test the actual flow:

**Frontend → API → AI/NLP interpretation → Navigation Engine → Campus Data → API response → Frontend visualization**

Do not test modules only in isolation.

## 3. How to do the work

### Step 1 — Define acceptance criteria
For every feature, write what must be true for it to be considered complete.

### Step 2 — Build tests beside development
Do not wait for the final week to start testing.

### Step 3 — Create representative test data
Use small, deterministic campus graphs for algorithm tests and clearly labelled campus demo data for integration tests.

### Step 4 — Record failures
When something fails, document:
- input;
- expected result;
- actual result;
- suspected module;
- reproduction steps;
- fix;
- regression test added.

### Step 5 — Integration verification
After a feature branch is merged into `dev`, verify that existing functionality still works.

### Step 6 — Documentation
Maintain:
- test strategy;
- API testing notes;
- known limitations;
- setup instructions;
- integration checklist;
- final test results.

## 4. Tools to use

**Required**
- Git + GitHub
- VS Code
- pytest
- FastAPI test client
- Browser developer tools

**Useful**
- Postman or Insomnia — API/manual testing
- GitHub Pull Requests — review and integration
- GitHub Actions — automated tests when the project is ready
- Playwright — browser/end-to-end testing if the frontend becomes stable enough to justify it

GitHub Actions workflows can automate builds and tests from repository events. citeturn0search4

## 5. Integration workflow

Use this flow:

```
feature branch
     ↓
local tests
     ↓
commit
     ↓
Pull Request → dev
     ↓
review + integration tests
     ↓
merge to dev
     ↓
stable milestone
     ↓
Pull Request → main
```

GitHub describes pull requests as the mechanism for proposing, reviewing, and merging branch changes, with checks and review happening before merge. citeturn0search3turn0search9

## 6. AI-assisted testing rules

Use AI to:
- generate possible edge cases;
- explain failing test output;
- suggest test cases;
- review missing coverage;
- help write small test utilities.

The final expected result must come from the project's requirements and actual behavior, not from an AI guess.

## 7. Definition of done

A feature should not be considered integrated until:
- its tests pass;
- its API contract is understood;
- error cases are checked;
- no existing feature is unintentionally broken;
- documentation is updated;
- the owner can explain what was tested and what remains untested.

## 8. Commit style

```
test: add navigation edge cases
test: validate backend API responses
test: add integration scenarios
docs: add testing strategy
test: add regression coverage
ci: run automated tests on pull requests
```

Keep test/documentation commits focused and traceable to the feature they support.
