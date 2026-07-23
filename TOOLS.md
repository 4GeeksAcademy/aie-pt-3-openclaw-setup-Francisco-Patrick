# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup: camera names and locations, SSH hosts and aliases, preferred TTS voices, speaker/room names, device nicknames, anything environment-specific.

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.

## mcporter + Composio MCP

**Config path:** `/root/config/mcporter.json` (NOT the default `./config/mcporter.json` or `~/.mcporter/mcporter.json`)

**Always pass:** `--config /root/config/mcporter.json` on every `mcporter` call.

**JSON payload best practices:**
- For complex/long payloads, write JSON to a temp file first, then use: `mcporter call composio.TOOL --config /root/config/mcporter.json --args "$(cat /tmp/payload.json)"`
- NEVER inline large markdown or multi-line strings directly in shell — shell escaping will destroy them.
- Keep JSON payloads clean: no trailing commas, proper escaping of quotes.

**Composio workflow pattern:**
1. `COMPOSIO_SEARCH_TOOLS` → discover tools, get session_id
2. `COMPOSIO_MANAGE_CONNECTIONS` → initiate auth if needed
3. `COMPOSIO_WAIT_FOR_CONNECTIONS` → poll until active
4. `COMPOSIO_MULTI_EXECUTE_TOOL` → execute tools

**Always pass `session_id` from step 1 in all subsequent calls.**

## Related

- [Agent workspace](/concepts/agent-workspace)
