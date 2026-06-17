# Leita Fantasy Golf Twilio

Separate Streamlit codebase for the Leita Fantasy Golf app with the original Golf Challenge text-update system restored.

## What This Reuses

- Current Leita Fantasy Golf Streamlit structure and visual style.
- Draft board, roster cards, standings cards, tournament leaderboard, tournament selector, admin controls, and 5-round snake draft behavior.
- Original Golf Challenge coach photos for Jayme, Spencer, and Peter.
- Original Golf Challenge title thumbnail/icon.
- Original Golf Challenge Twilio text-update concepts: group recipients, test messages, and score-driven alert templates.

## What Is Separate

- The app targets its own GitHub repo: `leita-fantasy-golf-twilio`.
- Shared app state is stored in this repo's `draft_state.json`.
- The existing `leita-fantasy-golf` app/repo is not modified.
- Twilio credentials and phone numbers are not committed into the repo.

## Text Updates

Text updates are configured in the `Text Updates` expander inside the app.

Supported alert types:

- Tee off updates
- Birdie updates
- Bogey updates
- Lead change
- Top 3 golfer change

Twilio credentials must be configured in Streamlit secrets:

```toml
TWILIO_ACCOUNT_SID = "your_twilio_account_sid"
TWILIO_AUTH_TOKEN = "your_twilio_auth_token"
TWILIO_FROM_NUMBER = "+15555555555"

[GITHUB]
TOKEN = "your_github_personal_access_token"
```

Phone numbers are entered in the app UI and saved to `draft_state.json` through the normal GitHub-backed state flow.

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
