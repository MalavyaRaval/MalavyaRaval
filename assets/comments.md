# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

### 🚦 Rate Limit Protocol

When approaching or exceeding API limits:

1. **Proactive Efficiency:** Always use `read` with `offset`/`limit` or `memory_get` with `from`/`lines` instead of full file reads to minimize token footprint per turn.
2. **Reactive Backoff:** If a 429 error occurs:
   - Immediately pause execution for 60 seconds (use shell `sleep 60` if needed).
   - Trim conversation context (clear older, non-essential history).
   - Retry the request only once.
3. **Context Hygiene:** Periodically `trash` or archive stale memory files/logs to avoid bloat.

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.
