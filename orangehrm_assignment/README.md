# OrangeHRM UI + API Automation Assignment

This project is organized around the assignment requirements: Playwright/POM UI automation, complementary manual testing, GitHub workflow documentation, and Postman/Newman API automation.

## UI scenarios
- Invalid login and error-message verification.
- PIM: add randomly generated employee, search and verify it, then logout.
- Admin: search a username, verify the matching row, edit role/status, save, refresh, and verify persistence.
- Leave: apply for specific dates, verify Pending Approval, cancel, and verify the updated status.

## API scenarios
- GET `/users`: validate HTTP 200, user data, and `id`, `name`, `email`.
- Extract one user id.
- Build `/users/{id}` from that id.
- PUT dynamically generated `name`, `email`, and `company.name`; validate returned id and non-empty phone.

## Suggested structure
```text
/
├── ui-tests/pages/
├── ui-tests/tests/
├── api-tests/
├── manual-tests/
├── reports/
├── README.md
└── package.json
```

## UI execution
```bash
npm install
npx playwright install
npx playwright test ui-tests/tests/q1-invalid-login.spec.ts
npx playwright test ui-tests/tests/q2-add-employee.spec.ts
npx playwright test ui-tests/tests/q3-admin-user.spec.ts
npx playwright test ui-tests/tests/q4-leave.spec.ts
npx playwright test ui-tests/tests
npx playwright show-report
```
Keep credentials in environment variables rather than source code.

## API execution
```bash
npm install -g newman
newman run api-tests/orangehrm_assignment_api.postman_collection.json
```

## Manual testing
`manual-tests/manual_test_cases.xlsx` contains 11 complementary cases covering validation, boundaries, session behavior, authorization, and exploratory scenarios. Record an actual bug only after it is observed, with the real screenshot.





