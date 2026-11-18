# Notes

## Plan
Add `PUT /users/:id` to the users resource, going through `db/store.js` for data access like the existing routes:

1. Add an `updateUser(id, { name, email })` helper to `db/store.js`. It updates the user in place and returns it, or returns `undefined` if the id doesn't exist.
2. Add the `PUT /:id` route in `routes/users.js`. It returns 404 for an unknown user, 400 with a clear message for missing or invalid `name`/`email`, and 200 with the updated user on success.
3. Add this `NOTES.md`.

`tests/update-user.test.js` was not edited; it is how the feature is checked.

The plan created by Claude fulfilled the project brief. The only amendment was to ensure that only one logical change was made per commit.

## Model choice
The Sonnet model was chosen because the planning required careful consideration of the project requirements, and the execution was not straightforward.

## Commit split
The commits were split by asking Claude to only make one logical change per commit. This is to allow the Reviewer to more easily understand what changed and why.

One logical change per commit, with `npm test` run after each:

1. `cf90be2` Add updateUser helper to the in-memory store
2. `a37ef73` Add PUT /users/:id endpoint with input validation
3. Add NOTES.md (this commit)

## Review
The Claude review determined that there are no bugs and that validation was correct for the common cases. The review identified unnecessary brackets in a file which was not changed as it was out of scope.
