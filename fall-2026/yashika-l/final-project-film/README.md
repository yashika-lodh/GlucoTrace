# Final Project Pitch Film — Checkable Glucose Insights (working title)

- **Name:** Yashika Lodh
- **Course:** INFO7375, Fall 2026
- **Working title:** Checkable Glucose Insights
- **Target role:** early-career frontend / full-stack engineer (React + TypeScript)
- **Runtime:** [fill in after render, m:ss]
- **Film:** `[fill in file name].mp4`

## What this is
A 2–4 minute pitch for my final project: a web app that will show glucose next to meals, heart rate, and activity, where every AI explanation is checked against the data before it is shown. **Nothing in the app is built yet.** The film says what will exist; sketches are labelled "constructed" on screen.

## What's in this folder
| File | What it is |
|---|---|
| `*.mp4` | The rendered pitch film |
| `PROJECT-BRIEF.md` | The seven answers, plus "exists today" and "will exist" |
| `beat_sheet.json` | Narration and visual plan, one beat per idea |
| `BUILD-PROMPT.md` | The prompts and commands that rebuild the film |
| `SOURCES.md` | What I used, what I made, what Claude contributed, licences |
| `FRICTIONAL.md` | Dated log of what went wrong and what changed |
| `gate-reports/` | The toolkit's quality-gate reports |

## How to rebuild the film
Requires `python3` 3.10+, `ffmpeg`, Node 20+. Full steps are in `BUILD-PROMPT.md`. In short:

```bash
git clone https://github.com/nikbearbrown/brutalist.art
cd brutalist.art
./setup --install
# copy beat_sheet.json into a reel folder outside the toolkit, then:
python3 runtime/scripts/generate_audio_kokoro.py <reel-folder>
./art run   <reel-folder>
./art todo  <reel-folder>
./art final <reel-folder>
```

## Narration
[Pick one and delete the other:] Narrated in my own recorded voice. / Narrated by the toolkit's local Kokoro voice `af_bella`, reading a first-person script I wrote and reviewed.