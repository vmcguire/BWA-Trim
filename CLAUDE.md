# BWA-Trim — read before doing anything

> ⚠️ **This is a release-mirror repo, not the dev surface.**
> Do all work in the monorepo: **`~/Developer/bwa-fx-ecosystem/BWA-Trim/`**
> (there is **no** `plugins/` folder — that path is obsolete). Releases land
> here via `git subtree push` from the monorepo; a commit made directly here
> that the monorepo lacks is a bug to reconcile, not a feature.
>
> **Why:** every BWA plugin ships two surfaces — standalone VST3 **and**
> embedded BWA-Mix cell — off **one** `dsp/` module. Single-source DSP is
> locked (`ECOSYSTEM.md` Principle 3). The monorepo is the only dev surface.

## What this plugin is

- **Category:** C (Spectral DSP Processor, Dual-Surface (pre-split))
- **Tech tree tier:** Tier 3
- **Role:** Pre-split input gain stage with LUFS matching.
- **Pain attacked:** Big I/O LUFS meter + one-click Match button. Streaming-target overlays at the input stage.
- **Scope verdict:** GROUP — 'Gain-stage all drum tracks to -18 LUFS at input'
- **Band tier behavior:** Trim is broadband; not band-tier-gated.

Full row in
[`MARKET-PAIN-AND-ATTACKS.md`](https://github.com/vmcguire/BWA-Architecture/blob/main/docs/MARKET-PAIN-AND-ATTACKS.md)
— search for `BWA-Trim`.

## Before you write code — the canonical guides (single source of truth)

> These are maintained in **one place** so they stay correct as the ecosystem
> changes. This file deliberately holds only what is specific to BWA-Trim; every
> general rule — required reading, what to reuse, what to publish, the
> anti-patterns, the done-checklist, the release ritual — lives in the docs
> below. Do not re-derive a rule that isn't here; look it up there.

Read in order (all under `~/Developer/BWA-Architecture/`):

1. **`docs/LLM-ONBOARDING.md`** — thesis, 6-category taxonomy, locked decisions, anti-patterns. **Read first.**
2. **`docs/REUSE-MAP.md`** — what already exists and where. Reuse, never rebuild (band split, meters, Metal, widgets, brand theme, constants).
3. **`docs/PLUGIN-AUTHORING.md`** — the build drill: dev surface, dual-surface contract, **what you must publish for other workers**, the done-checklist, the release ritual.
4. **`docs/MARKET-PAIN-AND-ATTACKS.md`** — the row for **BWA-Trim**; internalize the pain + attack before any DSP.

(On GitHub: browse these under `vmcguire/BWA-Architecture/docs/`.)

## Release ritual

From the monorepo `~/Developer/bwa-fx-ecosystem/`, after the release commit on `main`:

```bash
git subtree push --prefix=BWA-Trim git@github.com:vmcguire/BWA-Trim.git main
```

Then cut a GitHub Release in this mirror and attach the notarized `BWA-Trim.vst3`.
See `docs/PLUGIN-AUTHORING.md §7` for the full ritual.
