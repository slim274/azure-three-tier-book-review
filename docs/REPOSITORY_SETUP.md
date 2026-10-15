# Add this documentation to your Azure Three-Tier GitHub project

This ZIP contains **documentation and screenshots only**, not the upstream Book Review application source. Preserve your original code and its Git history in your local project.

## Recommended repository name

`azure-three-tier-book-review`

## Suggested workflow (Ubuntu)

1. Extract this ZIP into a temporary folder, not directly over your existing project.
2. Back up any existing `README.md`, `docs/`, `diagrams/` and `screenshots/` from the local project.
3. Copy only the updated `README.md`, `docs/`, `diagrams/`, and `screenshots/` into the project folder.
4. Inspect the file changes with `git status --short` and `git diff --check`.
5. Verify secret files are untracked (for example: `git ls-files .env config/config.json '*.pem'`). This is **not a full history/secrets audit**.
6. Confirm your GitHub repository exists and `git remote -v` is correct before committing and pushing.

The supplied application was created by [`pravinmishraaws/book-review-app`](https://github.com/pravinmishraaws/book-review-app); keep this developer credit in the README.
