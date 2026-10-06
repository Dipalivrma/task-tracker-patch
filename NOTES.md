
## Summary of Changes

I reviewed the Task Tracker frontend, Spring Boot backend, and Oracle reference SQL. I made four focused fixes:

1. Search and Status Filter: Fixed the SQL condition grouping in `TaskRepository.java` and the Oracle reference query. Added parentheses around the title/description search so the search and status filters work correctly together.

2. Unnecessary API Delay: Removed the artificial `Thread.sleep()` delay from `TaskController.java` so the API does not wait unnecessarily before returning results.

3. Request Handling: Updated `useTasks.js` and `api.js` to use `AbortController`. Old API requests can now be cancelled when a new request starts. Loading and error handling were also improved.

4. Pagination: Updated `App.jsx` so the page resets to page 1 whenever the search query or status filter changes.

## What I Did Not Change

I did not make unrelated changes or redesign the application because they were outside the main scope of the exercise.

## Biggest Remaining Risk

Pagination is still handled after retrieving the matching tasks. With a very large number of tasks, database-level pagination would be more efficient.

## Tools / AI Used

I used ChatGPT,Cloud to help review the code, understand the SQL condition issue, and discuss possible fixes. I checked the suggestions against the actual code and applied the changes I understood.
