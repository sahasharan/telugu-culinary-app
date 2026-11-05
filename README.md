# Telugu Culinary

A Telugu cuisine discovery and cooking assistant built with **Python** and **Streamlit**. Explore recipes, search by ingredients, save favorites, and ask cooking-related questions through a chatbot powered by the **Dify Chat API**.

> **Project status:** Student-built prototype. The chatbot requires a configured Dify application and API key. This project has not been independently load-tested for production use.

## Features

- Browse Telugu recipes by category.
- Search recipes by name, ingredients, or description.
- Filter recipes by difficulty.
- Add recipes and manage favorites.
- Ask cooking-related questions through the Dify-powered chat interface.
- Store recipe and favorites data locally in JSON files.

## How it works

The Streamlit interface connects to the recipe and favorites manager, which reads and writes local JSON data. Chat requests are handled by `dify_client.py`, which communicates with the Dify Chat API.

```text
                 ┌──────────────────────────┐
                 │       Streamlit UI       │
                 └────────────┬─────────────┘
                              │
                 ┌────────────┴─────────────┐
                 │                          │
       ┌─────────▼─────────┐      ┌─────────▼─────────┐
       │ Recipe & favorites│      │   dify_client.py  │
       │     manager       │      │                   │
       └─────────┬─────────┘      └─────────┬─────────┘
                 │                          │
          ┌──────▼──────┐           ┌────────▼────────┐
          │  JSON files │           │  Dify Chat API  │
          └─────────────┘           └─────────────────┘
```

## Tech stack

- **Language:** Python
- **App framework:** Streamlit
- **Data handling:** pandas
- **HTTP requests:** requests
- **AI chat integration:** Dify Chat API
- **Local storage:** JSON

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/sahasharan/telugu-culinary-app2.git
cd telugu-culinary-app2
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS / Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Configure the Dify API key

Set your Dify application API key as an environment variable.

Windows PowerShell:

```powershell
$env:DIFY_API_KEY = "YOUR_DIFY_APP_API_KEY"
```

macOS / Linux:

```bash
export DIFY_API_KEY="YOUR_DIFY_APP_API_KEY"
```

### 5. Run the application

```bash
streamlit run main.py
```

## Security

- Never commit API keys or other credentials.
- Keep `DIFY_API_KEY` in an environment variable or your deployment platform's secret manager.
- Do not hard-code secrets in Python files or documentation.

## Current limitations

- Chat functionality depends on the Dify application's configuration and API availability.
- Recipe and favorites data are stored in local JSON files; they are not shared across users or devices.
- The project is a prototype and needs additional testing and production hardening.

## Potential improvements

- Add automated tests for recipe search and favorites.
- Add request timeouts, retry handling, and clearer chatbot error messages.
- Support persistent multi-turn chat using Dify conversation IDs.
- Add screenshots, a demo, and deployment instructions.

---

Built as a project exploring Telugu cuisine, recipe discovery, and AI-assisted cooking.
