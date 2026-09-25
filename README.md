# Meeting Vendors

Paste attendee names or emails from a meeting invite; the tool looks them up against the vendor directory and shows a summary of any suppliers in the list.

Owner: adam.walton+citizen@aimbition.com (procurement). Built on the platform paved road; see `CLAUDE.md` for how changes are made.

## Run it locally

```
uv sync --all-groups
uv run uvicorn app.main:app --reload --port 8080
```

Locally the app reads sample data from `fixtures/`. When deployed it reads live data through the platform data API using the signed-in user's identity.

## Check it

```
uv run ruff check . && uv run ruff format --check .
uv run pytest
```

## How it gets to users

Push a branch, open a pull request. CI runs the checks and builds a preview. A platform owner reviews, opens the preview, and merges. The app updates itself after the merge.
