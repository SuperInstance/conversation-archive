# Technical Index

URLs, IDs, configs, endpoints, and infrastructure details from the main chat.
**No secrets here** — credential VALUES are never stored; only references to where they're kept.

## Infrastructure

- **Oracle Cloud**: `ubuntu@147.224.38.131` (us-sanjose-1, ARM Ampere 4-core, 23GB RAM, Ubuntu 26.04.1)
  - SSH key: `~/.ssh/oracle-instance.key` (600); proxy: `nc -X connect -x hatch-egress-proxy:3128 %h %p`
  - Pinned host key: `SHA256:BkdQRmv5YFw4DkluIYZhRIiaaLcjfXZD32Pt27kcncg` (ED25519)
  - Reverse tunnels terminate on Oracle loopback: ProArt=2222, Kimi=2223, HP=2224
- **Kimi cloud**: hostname `iZt4n0rgdtgyy9g7h03eewZ`; root SSH via Oracle tunnel port 2223
  - Kimi CLI: `/root/.local/share/uv/tools/kimi-cli/bin/kimi`
  - OpenClaw gateway: port 18789 (web UI "OpenClaw Control"), health at `/health`
- **HP laptop**: Ryzen 5, 8GB, blank WSL; tunnel port 2224 (currently closed)
- **ProArt laptop**: RTX 4050, Ryzen 9 AI, WSL; tunnel port 2222

## GitHub Orgs & Key Repos

- **SuperInstance** (experiments): redshirt, dropbox, fleet-session, muse-workspace (private), jev-semantic, chiaroscuro, question-tree, zero-poc, Syzygy-openskyflight, AI-Writings, openrooms
- **purplepincher** (production): purplepincher.org front door; zero template
- **Luciddreamer-ai** (playground): OpenSkyFlight fork
- **Lucineer** (son's): OpenSkyFlight (iPad-first product)
- **si-ready**: polished applications collection
- **patchwork-quilt**: created, deliberately dormant

## Services & Endpoints

- **fleet-session**: https://fleet-session.purplepincher.org (canonical); redundant relay at https://fleet-session.superinstance.ai
- **Redshirt install**: `curl -sSL https://raw.githubusercontent.com/SuperInstance/redshirt/main/install.sh | bash -s <name> <hours>`
- **Dropbox**: https://github.com/SuperInstance/dropbox (inbox/done/shared)
- **Kimi Claw chat**: https://www.kimi.ai/bot/chat/1a10f0fb-af32-80db-8000-00000325fa75
- **Cloudflare**: account ID `2bd99d5b13b2186382cd3dc9`; Git competition https://www.cloudflare.com/git-competition/
- **Moth Quantum docs**: https://docs.mothquantum.com/docs/intro
- **Facebook**: SuperInstance page ID `892643760605846`

## Credentials (references only)

- `custom.anthropic` — replacement key stored; test returned HTTP 400 (cause unverified)
- `custom.claude-code-oauth` — stored; plumbing incomplete
- `custom.minimax` — working (chat + TTS)
- `custom.elevenlabs` — stored; 401 on test
- `moonshot`/`custom.minimax-hp` — 401
- `custom.zai` / `custom.zai_hp` — 429 rate-limited
- Telegram bot token — in superinstance vault
- HP deploy key `hp-node-github` (write) on jev-semantic; fingerprint `SHA256:S1iE/4PDwqXIBUjR31BnyB5yqWPxfzAa/F+RS2S+bbA`

## Models & Subscriptions

- Claude.ai Pro (annual, renews Mar 2027); Claude Code plan (weekly limit resets)
- MiniMax: 3 video clips/day; TTS working (voices: male-qn-qingse, female-shaonv)
- Kimi ("Kimmy"): Kimi Code CLI on cloud instance
- ZAI Max 20 plan (vault LLM token)
- TypeSafe/Jev: ~10¢/hour heavy use; "millions upon millions" of calls made

## Schedules (cron)

- `fleet-lane-watch` — every 15 min
- `prospector-sync-check` — every 30 min (dialogue with Kimi Claw)
- `dropbox-inbox-watch` — every 15 min
- `muse-mail-watch` — every 30 min
- heartbeat — every 30 min
- `openskyflight-fork-daily-sync` — daily 07:45
- AI-Writings weekly sweep

## Domains

- **Keepers**: superinstance.ai, superinstance.dev, cocapn.com, cocapn.ai, purplepincher.org, nautic.stream, deckboss.net
- **For sale** (14): activelog.ai ($2k above appraisal), activeledger.ai, etc.; LucidDreamer.ai at $33k
- cocapn.com transfer from Squarespace ($10.46); deckboss.net renewed $11
