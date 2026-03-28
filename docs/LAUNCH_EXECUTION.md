# Launch Execution Checklist

## Day 1 - GitHub

- Verify no leaked secrets in source tree.
- Run tests per repository before pushing.
- Confirm `.env.example` exists and contains no real credentials.
- Push each project repo on `main`.
- Add topics/tags to all repos.

## Day 2 - Deploy

### MedicaidGuard (Cloud Run)

```bash
cd ~/repos/medicaidguard-deploy
bash scripts/deploy_cloudrun.sh
```

### FraudShield (Cloud Run)

```bash
cd ~/repos/fraudshield-rag
# Ensure env vars are set for OPENAI/ANTHROPIC and Qdrant mode.
```

### Fraud Agent Monitor (Streamlit Cloud)

- Deploy `dashboard/app.py` from `fraud-agent-monitor`.
- Add `OPENAI_API_KEY` and `LANGSMITH_API_KEY` in Streamlit secrets.

### Fraud LLM (HuggingFace Spaces)

- Push `inference/app.py` and `inference/requirements.txt` to the Space repo.
- Attach/load adapter/model artifact in Space config.

## Day 3 - Profile + Applications

- Update LinkedIn and portfolio site with live URLs.
- Add portfolio hub link in applications.
- Tailor cover letter by role and attach relevant project link.
