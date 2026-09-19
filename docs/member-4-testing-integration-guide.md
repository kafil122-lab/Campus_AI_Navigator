# Member 4 Guide — Testing, Integration & Documentation

## Owner

**A. Nikhil Hasan**

**Role:** Testing, Integration & Documentation

This is a core engineering role, not a documentation-only role.

## 1. Main Responsibility

Make sure the four technical modules work together correctly.

Responsibilities:

- Unit testing
- API testing
- Navigation edge cases
- Frontend integration testing
- Error handling verification
- Performance measurements
- Documentation
- Integration support

## 2. Why This Work Is Important

A project is not complete because each member's code works separately.

The final system must work as:

```
Frontend
   ↓
Backend
   ↓
AI/NLP
   ↓
Navigation
   ↓
Campus data
```

Testing identifies failures at the boundaries between these modules.

## 3. Testing Levels

### Level 1 — Unit Tests

Test small functions.

Examples:

- Graph creation
- Dijkstra route calculation
- A* route calculation
- Location lookup
- Input validation
- Alias mapping

### Level 2 — API Tests

Test:

- Valid requests
- Invalid location
- Missing parameters
- Empty input
- Unsupported destination
- Backend errors

### Level 3 — Integration Tests

Test complete flows:

```
Search destination
→ API
→ location resolution
→ navigation
→ route response
→ frontend display
```

### Level 4 — System Testing

Test the application as a user would.

Example scenarios:

1. Main Gate → Library
2. Classroom → Lab
3. Ground floor → upper floor
4. Block A → Block B
5. Unknown destination
6. Invalid source
7. No connected route

Use only verified or clearly marked synthetic test data.

## 4. Navigation Test Cases

At minimum test:

- Start equals destination
- Direct connection
- Multiple possible routes
- No route
- Invalid node
- Multi-floor route
- Stair connection
- Lift connection
- Large graph
- Same route through Dijkstra and A* where expected

## 5. Performance Testing

Measure:

- Response time
- Route calculation time
- Number of explored nodes
- API response success/failure
- Frontend loading time later

Do not claim performance improvements without measurements.

## 6. Bug Reporting

Every significant bug should contain:

- Title
- Steps to reproduce
- Expected result
- Actual result
- Environment
- Relevant screenshot/log
- Severity
- Status

## 7. Integration Process

Before merging a feature into `dev`:

1. Pull the latest `dev`.
2. Run existing tests.
3. Test the new feature.
4. Check API/data compatibility.
5. Open a PR.
6. Review the changed files.
7. Run tests again.
8. Merge only when the integration is stable.

## 8. Tools

### Testing

- pytest
- Postman
- Browser developer tools

### Code quality

- Python formatter/linter such as Ruff
- GitHub Actions later
- Git diff / GitHub PR review

### Documentation

- Markdown
- diagrams.net
- GitHub Issues

### AI assistance

Use ChatGPT to:

- Generate test case ideas
- Explain failing tests
- Review edge cases
- Improve documentation
- Help interpret logs

Always run and inspect generated tests before trusting them.

## 9. Expected Deliverables

- Unit test suite
- API test suite
- Integration test cases
- Navigation edge-case tests
- Test results
- Bug reports
- Performance measurements
- Integration checklist
- Final technical documentation

## 10. Suggested Commit Sequence

```
docs: define testing strategy
test: add backend validation tests
test: add navigation edge cases
test: add api integration tests
test: add multi-floor navigation cases
docs: add test results
docs: add integration checklist
ci: add automated test workflow
```
