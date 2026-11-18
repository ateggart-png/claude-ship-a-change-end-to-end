# Notes

## Plan
Add `PUT /users/:id` to the users resource, going through `db/store.js` for data access like the existing routes:

1. Add an `updateUser(id, { name, email })` helper to `db/store.js`. It updates the user in place and returns it, or returns `undefined` if the id doesn't exist.
2. Add the `PUT /:id` route in `routes/users.js`. It returns 404 for an unknown user, 400 with a clear message for missing or invalid `name`/`email`, and 200 with the updated user on success.
3. Add this `NOTES.md`.

`tests/update-user.test.js` was not edited; it is how the feature is checked.

## Model choice
Sonnet was chosen because it fits both the planning and the execution of this small, well-scoped change.

## Commit split
One logical change per commit, with `npm test` run after each:

1. `cf90be2` Add updateUser helper to the in-memory store
2. `a37ef73` Add PUT /users/:id endpoint with input validation
3. Add NOTES.md (this commit)

## Review
To be completed after the review.
