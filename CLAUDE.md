# CLAUDE.md — Claude Code Context

<!-- This project uses AGENTS.md as the canonical AI context file.
     CLAUDE.md adds Claude Code-specific workflow notes. -->

## See AGENTS.md for full project context.

## Claude Code workflow for this project

### One-shot deploy
```bash
# Claude Code can run this after making changes:
git add -A && git commit -m "<description>" && git push origin main
```

### Environment variables
Set secrets in **Coolify UI → Project → App → Environment Variables**.
Never hardcode them in source files.

### Useful commands
```bash
git log --oneline -10      # recent deploys
git diff HEAD~1            # what changed in last deploy
```

## Boundaries
- You can edit `index.html` and any source files freely.
- Do NOT modify `.git/`, Coolify config, or server-side files.
- Infrastructure changes (firewall, Docker, Coolify settings) go through
  the human — don't attempt them via SSH.
