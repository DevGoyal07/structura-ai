# Contributing to Structura.AI

This is a team project for **Group CE24B0**. These notes keep our work organized and make sure everyone's contributions show up properly on GitHub.

## Setup

1. Accept your collaborator invite (Settings → Collaborators on the repo).
2. Clone the repo and set up your environment (see the README).
3. Make sure your local Git identity matches your GitHub account so commits are attributed to you:
   ```bash
   git config user.name "Your Name"
   git config user.email "your-github-email@example.com"
   ```

## Workflow

We use a simple branch-and-PR flow:

```bash
git checkout -b feature/short-description
# ...make changes...
git add .
git commit -m "Clear, descriptive message"
git push origin feature/short-description
```

Then open a Pull Request on GitHub and have at least one teammate review before merging into `main`.

## Commit Messages

Keep them short and meaningful, e.g.:
- `Add CNN inference endpoint`
- `Fix heat map color thresholds`
- `Update dataset curation script`

### Crediting paired work
If two people worked on the same change from one machine, add a co-author so both show on the contributors graph:
```bash
git commit -m "Add heatmap rendering" -m "Co-authored-by: Name <email@example.com>"
```

## Areas of Work

| Area | Notes |
| --- | --- |
| ML / Model | CNN architecture, training, accuracy validation |
| Data | FEA dataset curation, preprocessing |
| Backend | Flask / FastAPI inference serving |
| Frontend | Upload UI, heat map rendering |
| Docs / Outreach | README, demo video, pilot materials |

## Team — Group CE24B0

Abhay P M (CE24B034) · Abhishek Rai (CE24B035) · Devansh Goel (CE24B056) · Dipayan Das Gupta (CE24B059) · Lokesh K (CE24B082) · Param Shah (CE24B097)
