# Claude Code PR Review Agent

Automated PR review agent that analyzes any GitHub pull request and produces a structured Markdown review with summary, risks, suggestions, and confidence score.

## Two Ways to Use

### Option 1: GitHub Action (Recommended)
1. Copy `.github/workflows/pr-review.yml` to your repo
2. Add `ANTHROPIC_API_KEY` to your repo's GitHub Secrets
3. Reviews run automatically on every PR

### Option 2: CLI Script
```bash
# Prerequisites
# Set your GitHub token
export GH_TOKEN=your_github_token

# Set Claude API key (optional — falls back to heuristic)
export ANTHROPIC_API_KEY=your_claude_api_key

# Review any PR
bash pr-review.sh --pr https://github.com/owner/repo/pull/123
```

## Output Format
```markdown
## Summary
[2-3 sentence overview]

## Identified Risks
- Risk 1: ...

## Improvement Suggestions
- Suggestion 1: ...

## Confidence Score
High / Medium / Low
```

## Tested On
- [claude-builders-bounty#800](https://github.com/claude-builders-bounty/claude-builders-bounty/pull/800) — CLAUDE.md template
- [claude-builders-bounty#802](https://github.com/claude-builders-bounty/claude-builders-bounty/pull/802) — n8n workflow
