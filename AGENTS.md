# AGENTS.md — AI Agent Context

This file tells AI coding agents (Claude Code, Codex, Gemini, etc.)
everything they need to know to work on this project.

## Project
A static web app deployed via Coolify on a self-hosted Linode VM.
Auto-deploys on every push to `main`.

## Stack
- **Frontend**: Plain HTML/CSS/JS (single `index.html`)
- **Build**: Nixpacks (auto-detected — no config needed)
- **Deploy**: Coolify (self-hosted PaaS) → Linode VM
- **SSL**: Let's Encrypt (auto-provisioned by Coolify)
- **Repo**: GitHub, connected via GitHub App

## How to deploy
```bash
# Make your change, then:
git add .
git commit -m "describe what changed"
git push origin main
# Coolify picks it up automatically — live in ~60 seconds
```

## Project structure
```
index.html      # main page (edit this)
AGENTS.md       # this file — AI agent context
CLAUDE.md       # Claude Code specific context (symlink to AGENTS.md)
nixpacks.toml   # optional Nixpacks overrides
```

## Rules for AI agents
1. Keep the single-file structure unless the user explicitly asks to split.
2. Never commit secrets — use Coolify's environment variable UI instead.
3. The deploy branch is `main`. PRs go to feature branches.
4. After any change, verify with `git status` before committing.
