# Final Project Pitch Film — GlucoTrace (working title)

- **Name:** Yashika Lodh
- **Course:** INFO7375, Fall 2026
- **Working title:** GlucoTrace
- **Target role:** early-career frontend / full-stack engineer (React + TypeScript)
- **Runtime:** 2:26
- **Film:** `glucotrace-pitch.mp4` (3840×2160, 24 fps)

## What this is
A pitch for my final project: a web app that will show glucose next to meals, heart rate, and activity, where every AI explanation is checked against the data before it is shown. **Nothing in the app is built yet.** The film says what will exist; sketches are labelled "CONSTRUCTED" on screen.

## What's in this folder
| File | What it is |
|---|---|
| `glucotrace-pitch.mp4` | The rendered pitch film |
| `PROJECT-BRIEF.md` | The seven answers, plus "exists today" and "will exist" |
| `beat_sheet.json` | Narration and visual plan, one beat per idea (final version from the toolkit) |
| `BUILD-PROMPT.md` | The prompts and commands that rebuild the film |
| `SOURCES.md` | What I used, what I made, what Claude contributed, licences |
| `FRICTIONAL.md` | Dated log of what went wrong and what changed |
| `FACTCHECK.md` | Every factual claim in the film, its source, and my verdict (Gate F) |
| `PEDAGOGY.md` | My narration review sign-off (Gate P) |
| `gate-reports/` | The toolkit's quality-gate reports (type check, frame check, layout, bookend check, build record, shot list, prompts) |

## How to rebuild the film
Requires `python3` 3.10+, `ffmpeg`, and Node 20+. Full steps and every prompt are in `BUILD-PROMPT.md`. In short:

```bash
git clone https://github.com/nikbearbrown/brutalist.art ~/Documents/brutalist.art
cd ~/Documents/brutalist.art
./setup --install
# put beat_sheet.json, PEDAGOGY.md and FACTCHECK.md in ~/Documents/info7375-film/youtube/glucotrace-pitch, then:
REEL=~/Documents/info7375-film/youtube/glucotrace-pitch
python3 runtime/scripts/generate_audio_kokoro.py $REEL
./art run   $REEL
./art final $REEL
```

## Narration
Narrated by the toolkit's local Kokoro voice `af_bella`, reading a first-person script I wrote and reviewed. It is a synthetic voice, not a recording of me.

## Known gate result
`bookend_check.py` reports one failure (no Claude title outro). The toolkit's outro hard-codes the instructor's channel handle, which the assignment forbids, so I left it out on purpose. See FRICTIONAL.md.