# RoarGuild — developer and AI collaborator rules

**Project creator and creative director:** Babuni.dev.

## Identity and authorship

Preserve the intent: in-world character presence, joyful guild recruitment and community stories—not DPS optimization. Do not attribute the original concept, guild values, or characteristic language to AI. AI research and documented implementation contributions must be separately credited.

Document **human direction**, **AI proposals**, **creative iteration**, **explicit creator decisions**, **changed paths/commits**, and **actual verification** in `docs/DEVLOG.md` and `docs/AI_COLLABORATION.md`. Label historical reconstruction; do not invent dialogue, approvals or user testing.

## Preserve accurate technical boundaries

- Distinguish RoarGuild from `roar`, `roarr`, `ROARRunlimited`, `WorkThatGodBod` and `RoarForever`. Trace lineage only from actual commits.
- The **current version has no GodBod runtime subsystem**. Initial January 2026 history did, but it was subsequently removed.
- Fresh `ROGUDB.emotes[1]` defaults to ROAR; sanitation falls back to ID 1. The source does not absolutely guarantee that an existing valid ID-1 entry can never differ.
- `/rogu roar` explicitly calls `DoEmote("ROAR")`; configured emote pools do not determine this manual command.
- Instance cooldown timestamps advance **before** chance rolls; fallback timestamp advances **on successful fallback only**.
- Reminder after 420s since last successful emote; 73s repeat throttle, only checked on action press.
- `/rogu invite` sends a prewritten message to a numeric channel, which may or may not be General.
- **Roarboard is not guild-authenticated or private.** It uses the normal custom `roarboard` chat channel with `RB1` packets and an independently stored local cache. Do not market it as secure guild-only transport.

## Implementation discipline

1. Inspect `roarguild.lua`, `roarguild.toc`, README, LICENSE, DEVLOG, DECISIONS and ARCHITECTURE before changing behavior.
2. Keep changes small and reviewable. Do not modify executable code incidentally during a docs-only audit.
3. Respect intended WoW 1.12/Lua 5.0 API constraints, and test `UseAction` chaining/load order.
4. Validate any protocol input handling, permissions, sync bursts, replay/deduplication, and retention before claiming Roarboard security or delivery guarantees.
5. Preserve MIT license and author credit; do not publish sensitive player communications or unapproved private logs.
6. For every implementation update, revise README, CHANGELOG, DEVLOG, DECISIONS, DESIGN, CONTENT and ROADMAP as applicable and report real test results.

The October 26, 2026 documentation pass neither approved new functionality nor tested WoW runtime behavior.
