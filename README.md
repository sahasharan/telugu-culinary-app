# Telugu Culinary — Dify Chat Variant

A second version of the Telugu Culinary Streamlit application. It keeps the recipe-browsing workflow and connects the chatbot page to a Dify chat API.

> **Project status:** Student prototype. The chatbot requires a valid Dify application API key and has not been independently load-tested.

## Features

- Browse Telugu recipes by category.
- Search by recipe name, ingredients, or description.
- Filter by difficulty.
- Add recipes and manage favorites.
- Ask cooking-related questions through a Dify-powered chat interface.
- Keep recipe and favorites data in local JSON files.

## Architecture

```text
Streamlit UI ──► Recipe / favorites manager ──► JSON files
      |
      └────────► dify_client.py ──HTTP──► Dify Chat API
```

## Tech stack

- Python, Streamlit, pandas
- requests
- Dify Chat API
- JSON-based local persistence

## Run locally

```bash
python -m venv .venv
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
# macOS / Linux
source .venv/bin/activate

python -m pip install --upgrade pip
pip install -r requirements.txt
```

Set your Dify key as an environment variable before starting the app:

```bash
# Windows PowerShell
$env:DIFY_API_KEY = "YOUR_DIFY_APP_API_KEY"

# macOS / Linux
export DIFY_API_KEY="YOUR_DIFY_APP_API_KEY"
```

Start the application:

```bash
streamlit run main.py
```

## Security

Keep `DIFY_API_KEY` outside source control. Use environment variables locally and your hosting provider's secret manager for deployment. Never paste API keys into `main.py`, `dify_client.py`, Dockerfiles, or README examples.

## Current limitations

- Chat behavior depends on the Dify app's configuration and API availability.
- Recipe and favorites files are local JSON, not a shared multi-user database.
- Add automated tests, request retry handling, and safer user-facing error handling before production use.

## Next improvements

- Add a `.env.example` containing variable names only.
- Add unit tests for recipe search and favorites.
- Preserve Dify conversation IDs for multi-turn context if needed.
- Add screenshots, a demo video, and deployment instructions.
