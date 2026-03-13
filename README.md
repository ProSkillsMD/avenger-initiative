# 🛡️ Avenger Initiative

> Encrypted GitHub backup & restore for any [OpenClaw](https://openclaw.ai) agent system.

[![ProSkills.md](https://img.shields.io/badge/ProSkills.md-listed-brightgreen)](https://proskills.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## What It Does

Avenger Initiative backs up your entire OpenClaw system to a private GitHub repo every night — configs, agent memories, SOUL files, custom skills, cron jobs — everything needed to restore from zero.

**Security model:**
- `openclaw.json` (API keys, bot tokens) → **AES-256 encrypted**
- Everything else (SOUL.md, MEMORY.md) → plaintext in private repo
- Key stored locally, **never committed to git**

## Retention Policy

| Branch | Pattern | Retention |
|--------|---------|-----------|
| Daily | `backup/daily/YYYY-MM-DD` | 7 days |
| Weekly | `backup/weekly/YYYY-WNN` | 8 weeks |
| Monthly | `backup/monthly/YYYY-MM` | 12 months |

## Quick Start

1. Install via [ProSkills.md](https://proskills.md/skills/avenger-initiative) or manually copy to `~/.openclaw/workspace/skills/avenger-initiative/`
2. Say **"setup avenger"** to your OpenClaw agent
3. Follow the guided setup (vault repo URL + encryption key)
4. First backup runs immediately, daily cron installed automatically

## Manual Setup

```bash
bash ~/.openclaw/workspace/skills/avenger-initiative/scripts/setup.sh \
  --repo https://github.com/yourname/your-vault
```

## Restore from Backup

```bash
bash ~/.openclaw/workspace/skills/avenger-initiative/scripts/restore.sh
openclaw gateway restart
```

## License

MIT © [ProSkillsMD](https://github.com/ProSkillsMD)
