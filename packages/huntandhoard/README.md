# GuildForge Hunt & Hoard

**Idle, no-end RPG game** powered by a Twitch chatbot, run under the bot persona **TheWanderingClerk** — a guild receptionist/clerk.

Part of the **GuildForge** suite.
*Tools for the guild. Power for the stream.*

## Overview

Hunt & Hoard turns your chat into a persistent idle RPG — viewers hunt, gather, and build their hoard over time with no forced ending. It's a completely separate bot and Twitch account from GuildScribe, so commands never collide.

## Architecture

A deliberate split setup, chosen to avoid any self-hosting or paid Val Town tier:

- **Val Town** (free tier) — handles storage and broadcaster onboarding
- **GitHub Actions** (scheduled workflow, free/unmetered runner minutes) — runs the live Twitch chat connection

Uses Twitch's **Helix API + EventSub WebSocket** (not legacy IRC), with its own registered Twitch application (separate Client ID/Secret) to support one-click broadcaster OAuth onboarding.

## Module map

| File | Role |
|------|------|
| `bot.ts` | Bot entry point |
| `commands.ts` | Chat command handling |
| `game.ts` | Core game loop / progression logic |
| `data.ts` | Static game data |
| `helix.ts` | Twitch Helix API client |
| `twitch.ts` | Twitch connection handling |
| `permissions.ts` | Mod/broadcaster permission checks |
| `quests.ts` | Quest/hunt mechanics |
| `storeClient.ts` | Val Town storage client |
| `.github/workflows/bot.yml` | GitHub Actions scheduled workflow that runs the live bot |

## Commands guide

A player-facing commands guide, styled as a guild parchment, is hosted at `huntandhoardbot.val.run/commands` and linked from the bot's `!help` reply.

## Setup

1. Register a Twitch application for TheWanderingClerk (separate Client ID/Secret from any other bot).
2. Configure the Val Town project for storage + broadcaster onboarding.
3. Set up the GitHub Actions workflow (`.github/workflows/bot.yml`) with the required secrets for the live connection.
4. Point broadcasters at the Val Town onboarding flow to connect their channel via OAuth.

## License
MIT — see the root [LICENSE](../../LICENSE).
