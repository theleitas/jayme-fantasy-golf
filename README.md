# Jayme Fantasy Golf

Separate Streamlit codebase for the Jayme Fantasy Golf app.

## What This Reuses

- Current Jayme Fantasy Golf Streamlit structure and visual style.
- Draft board, roster cards, standings cards, tournament leaderboard, tournament selector, admin controls, and 10-round snake draft behavior.
- Original Golf Challenge coach photos for Jayme, Spencer, and Peter.
- Original Golf Challenge title thumbnail/icon.

## What Is Separate

- The app targets its own GitHub repo: `jayme-fantasy-golf`.
- Shared app state is stored in this repo's `draft_state.json`.
- The existing `leita-fantasy-golf` app/repo is not modified.

## Secrets

The app saves shared state back to GitHub, so a GitHub token must be configured in Streamlit secrets:

```toml
GITHUB_TOKEN = "your_github_personal_access_token"
```

The app also accepts `[GITHUB] TOKEN = "..."`, `GH_TOKEN`, and lowercase `github_token`.

## Run

```bash
streamlit run app.py
```

## Files

- `app.py`: Streamlit app.
- `draft_state.json`: starter state for Jayme, Spencer, and Peter.
- `titlethumb.png`: title image and app/share icon source.
- `thumb.png`: original Golf Challenge thumbnail asset.
- `jayme-pic.png`, `spencer-pic.png`, `peter-pic.png`: original coach photos.
- `.streamlit/secrets.toml.example`: local/deployment secrets template.
