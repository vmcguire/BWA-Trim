# BWA-Trim

Input gain stage with visual I/O LUFS matching. The 'gain stage all drum tracks to -18 LUFS' button.

**Category C** · **Tier 3** · part of the
[Bandwidth Audio](https://github.com/vmcguire) plugin ecosystem.

---

## What this is

BWA-Trim is the input gain stage every BWA chain starts with. Big I/O LUFS meters side-by-side; a one-click Match button that auto-trims so input LUFS = output LUFS. Built-in correlation meter. Streaming-target overlays so you stage-gain for the destination at the FRONT of the chain, not the end.

Scope-aware: GROUP scope lets one Trim instance set the input target for an entire group (e.g. all drum tracks to -18 LUFS at input).

For the broader story of *what BWA is building and why*, see
[BWA-Architecture](https://github.com/vmcguire/BWA-Architecture) —
specifically:

- [`USER-STORY-MAP.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/USER-STORY-MAP.md)
  — where this plugin sits in the bedroom-producer journey (Stage 7 — MIX).
- [`ECOSYSTEM.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/ECOSYSTEM.md)
  — the full product map and the dual-surface / single-DSP architecture.
- [`docs/MARKET-PAIN-AND-ATTACKS.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/MARKET-PAIN-AND-ATTACKS.md)
  — what this plugin attacks (the pain it solves) and how.

## How this fits with the rest of BWA

BWA-Trim ships on **two surfaces** — same DSP, different UI:

1. **Standalone VST3** — drops into any DAW like a FabFilter / iZotope plugin.
   That's what this repo releases.
2. **Embedded cell inside BWA-Mix** — appears as a per-band / per-group cell
   processor inside BWA-Mix's track grid, sharing BWA-Mix's already-running
   band split and contributing to ecosystem-level cross-plugin features.

Both surfaces consume the **same authoritative DSP module**. Fix a bug once,
fixed everywhere.

## Status

🔴 Not built. Stub repo. Build target: Phase D3.

## Releases

Versioned `.vst3` builds for macOS land in this repo's
[Releases](https://github.com/vmcguire/BWA-Trim/releases). Build from
source if you want — see `CLAUDE.md` for the dev surface (it's not this repo).

## License

Proprietary. Distribution + license terms pending storefront launch — see
[BWA-Architecture/docs/GO-TO-MARKET.md](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/GO-TO-MARKET.md).
