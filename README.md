# Johny Johny, Yes Papa — Animated Nursery Rhyme

A 54-second, vertical (1080×1920) flat-cartoon animation of the classic
"Johny Johny, Yes Papa" nursery rhyme, produced with the
[OpenMontage](https://github.com/calesthio/openmontage) `character-animation`
pipeline.

## Final Video

`renders/final.mp4` — 1080×1920, 30 fps, H.264 + AAC, 54 s.

## Concept

**"The Pantry Door"** — a calm, warm, caption-readable take on the rhyme
(deliberately the opposite of over-stimulating "edutainment"):

- **Johny** — mischievous toddler in blue overalls, sugar on his nose
- **Papa** — warm, amused father in an apron who always knows
- 8 scenes: title card → call-and-response dialogue → ruffle-hair →
  giggling run-off → end card with a winking sugar cube

## What's in This Repo

| Path | Contents |
|------|----------|
| `renders/final.mp4` | Final rendered video |
| `hyperframes/index.html` | HyperFrames atelier composition (SVG characters + GSAP timeline) |
| `hyperframes/assets/` | Background PNG + mixed audio used by the composition |
| `assets/audio/` | 11 Piper TTS dialogue lines, lullaby music bed, master mix |
| `assets/svg/` | Kitchen background source SVG |
| `artifacts/` | Pipeline artifacts: research brief, proposal, script, character design, rig plan, pose library, scene plan |
| `qa/` | QA snapshot frames + contact sheets |
| `checkpoint_*.json`, `decision_log.json`, `project.json` | Pipeline governance records |

## How It Was Made

- **Pipeline:** OpenMontage `character-animation` (research → proposal →
  script → character_design → rig_plan → scene_plan → assets → compose)
- **Render runtime:** HyperFrames (atelier composition mode), rendered via
  `npx hyperframes render`
- **Voices:** Piper TTS — `en_US-lessac-medium` (Johny), `en_GB-alan-medium` (Papa)
- **Music:** Twinkle-Twinkle lullaby bed synthesized locally with FFmpeg
- **Cost:** $0 (fully local generation)

## Re-rendering

```bash
cd hyperframes
npx hyperframes lint
npx hyperframes snapshot --at 2,7,14,26,32,40,45,50
npx hyperframes render --output ../renders/final.mp4 --fps 30
```

Requires Node 18+ and a free `/tmp` (HyperFrames renders through a
headless browser and uses temp files).