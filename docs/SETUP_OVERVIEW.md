# GuildForge Setup Overview

This document explains how to point your bots and overlays at the GuildForge tools so everything is ready to use.

## 1. Organization / Monorepo

- Create a GitHub organization named **GuildForge** (or use your personal account).
- Push this entire folder as the main repository, or push each package as its own repository under the organization.
- Update the GitHub links in `website/index.html` and the root README once the org exists.

## 2. Pointing the Bots

### Guildscribe & Hunt & Hoard (Twitch Chatbots)
1. Create (or reuse) a Twitch bot account.
2. Generate an OAuth token with the required scopes (chat:read, chat:edit, etc.).
3. Place the token and channel name in the bot’s configuration / `.env` file (see each package’s README).
4. Run the bot process (Node, Python, or whatever runtime you used).
5. Make the bot a moderator in your channel for full functionality.

### Hushwave (Windows Ambient Generator)
1. Build or download the Windows executable.
2. Run it on the streaming PC.
3. Route its audio output into OBS as an Audio Input Capture or via virtual cable if needed.

### Overlays (Chat + Mic Status)
1. Host the overlay HTML/JS pages (GitHub Pages, Cloudflare Pages, Vercel, your own server, or even localhost for testing).
2. In OBS Studio:
   - Add a **Browser Source**.
   - Paste the full URL of the overlay.
   - Set appropriate width & height.
   - Enable “Control audio via OBS” only if the overlay produces sound.
3. Customize via CSS or query parameters as documented in each overlay’s README.

## 3. One-Account Future
When you add a paid tier later, introduce a simple auth layer (e.g. Discord or Twitch login + Stripe) that unlocks Pro features across all tools. Keep the core open-source versions free.

## 4. Checklist Before Going Public

- [ ] Replace all placeholder README content with real setup instructions.
- [ ] Add actual code into each package folder.
- [ ] Update website GitHub links.
- [ ] Claim social handles (@GuildForge or similar).
- [ ] Choose and register a domain (guildforge.dev / .tools / .stream recommended).
- [ ] Push to GitHub and enable GitHub Pages for the website folder if desired.
