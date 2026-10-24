# BUILD-PROMPT — how to rebuild the GlucoTrace pitch film

Toolkit: Brutalist (https://github.com/nikbearbrown/brutalist.art), free local pipeline only. No paid generation, no API keys, no upload.

**Paths used**
- Toolkit: `~/Documents/brutalist.art`
- Reel (where the film is built): `~/Documents/info7375-film/youtube/glucotrace-pitch`
- Submission folder: `~/GlucoTrace/fall-2026/yashika-l/final-project-film`

## 1. Install the toolkit
```bash
cd ~/Documents
git clone https://github.com/nikbearbrown/brutalist.art
cd brutalist.art
./setup --install      # Python + Remotion deps, Kokoro voice model
./art smoke            # renders a tiny test video end to end to prove rendering works
./art --list           # list the skills
```

## 2. Create the reel folder (outside the toolkit and outside the repo)
```bash
mkdir -p ~/Documents/info7375-film/youtube/glucotrace-pitch
cp ~/GlucoTrace/fall-2026/yashika-l/final-project-film/beat_sheet.json ~/Documents/info7375-film/youtube/glucotrace-pitch/
cp ~/GlucoTrace/fall-2026/yashika-l/final-project-film/PEDAGOGY.md ~/Documents/info7375-film/youtube/glucotrace-pitch/
cp ~/GlucoTrace/fall-2026/yashika-l/final-project-film/FACTCHECK.md ~/Documents/info7375-film/youtube/glucotrace-pitch/
```
The beat_sheet.json in this folder is the final, toolkit-formatted version, so a rebuild can skip prompts 1–3 below.

## 3. Prompts given to Claude Code (in ~/Documents/brutalist.art), in order

**Prompt 1 — format the beat sheet**
> Compare ~/Documents/info7375-film/youtube/glucotrace-pitch/beat_sheet.json with examples/ai-explainer/claude-debunked/beat_sheet.json. Rename and restructure my file's fields so it matches the example's format and the skill's SKILL.md. Do not change any narration text, visual descriptions, or on-screen text. Keep every "CONSTRUCTED" label. Show me a list of every field you renamed or added before saving.

**Prompt 2 — save, bookends, show steps, scenes, voice**
> Yes, save it. Then: (1) Don't add the Claude chat-window opening, overview, summary, Your Turn, or closing title card. Keep B00 and B10 as my opening and closing. (2) Don't use Liam, "in for Bear", @NikBearBrown, or any instructor name or credit line anywhere. My course assignment forbids these, so deviate from the skill's bookend rules here. If the build refuses without them, stop and tell me exactly which check fails. (3) Write shot.show steps for each beat from my existing visual descriptions only, with no new text or content, and show them to me before saving. (4) Stay with ai-explainer and choose scenes with ./art scenes. (5) Keep af_bella.

**Prompt 3 — cues, bookend exemption, Manim scenes, Gate F paperwork**
> 1. Save the shot.show steps, but move B09's cues so each item is crossed out as it is named: stethoscope at "It won't diagnose", crystal ball at "predict glucose", prescription pad at "give medical advice". Keep B04 as is.
> 2. Add "bookend_exempt": ["cold-open", "bvdt", "bhtf"] to the metadata. For the OUTRO: can the handle be changed? If yes, add a ClaudeTitleOutro beat with no narration, showing "GlucoTrace" and "Yashika Lodh", with no @NikBearBrown or instructor credit. If the handle can't be changed, don't add it; tell me and I'll log the failing check.
> 3. Draw each beat as a simple Manim scene in the Claude colours from my visual descriptions only. Keep them minimal: simple line drawings, no new text beyond my on-screen text, and CONSTRUCTED visible on B03, B07 and B10. Don't use the five-box pipeline scene for B05; draw my three boxes.
> 4. For Gate F, draft SHOTLIST.md and PROMPTS.md from the beat sheet and this session. For FACTCHECK.md, list every factual claim in the narration with the source I should check, and leave the verdict column blank for me to fill in.
> Show me what you'll change before running ./art run.

**Prompt 4 — title and empty openings**
> Before running: (1) Change metadata.title to "GlucoTrace — Final Project Pitch" and B00's on-screen text to "GlucoTrace (working title) — a pitch". Don't change any narration. (2) Move B08's first cue to "It's meant to show" so the two columns appear from the start. For B07, make the meal-card sketch appear at "A hiring manager will open the link". (3) Keep no logos. (4) Leave the caption spacing unless GATE T flags it. Wait for my go-ahead after I sign FACTCHECK.md and PEDAGOGY.md.

**Prompt 5 — title spacing**
> Yes, tighten the spacing in "GlucoTrace" on B00 now so it reads as one word, without changing the wording or font. Re-render the B00 preview and check it. Leave the "not built" caption as is.

**Prompt 6 — fact-check fixes**
> Two changes from my fact check: (1) In B01, change "you usually can't see what the explanation is based on" to "it's often hard to see what the explanation is based on", and update that beat's shot.show cue to match the new words. (2) Change B02's on-screen text to "Oura + Stelo · Stelo by Dexcom app"; don't change B02's narration. Make no other changes, and show me the diff.

**Prompt 7 — start the build**
> Signed. Go ahead with both steps.

(Claude Code then fixed safe-area layout failures from GATE B on B03, B04, B07, B09 and B10 and re-ran ./art run until all gates passed. No wording changed.)

**Prompt 8 — last fix and final master**
> Yes, move B08's "Learning" cue to "Verification, evaluation and health data" and re-render B08. Leave B05 as is. Change metadata.slug to "glucotrace-pitch" so the output files use the GlucoTrace name. Then run ./art final. When it's done, tell me: the final file name, path, size, and runtime; the GATE T result; which files are the gate reports and where they are; and which fonts the scenes used and where their licence files are.

## 4. Gate P and Gate F (my sign-offs)
Read every narration line in `beat_sheet.json` and signed `VERDICT: PASS` in `PEDAGOGY.md`. Checked every claim in `FACTCHECK.md` against its source and signed the Gate F line.

## 5. Audio, review build, final master
```bash
cd ~/Documents/brutalist.art
REEL=~/Documents/info7375-film/youtube/glucotrace-pitch
python3 runtime/scripts/generate_audio_kokoro.py $REEL   # Kokoro af_bella; audio sets the timing
./art run   $REEL     # review cut with beat labels: glucotrace-pitch-slate.mp4
./art final $REEL     # clean master
```
Narration: Kokoro `af_bella` reading my first-person script.
`./art final` writes the master to `~/Documents/brutalist.art/renders/glucotrace-pitch.mp4`.

## 6. Quality gates
`./art run` runs GATE A (scenes run), W (contrast and margins), B (layout / safe area), L (beat mix), F (paperwork) and V (frame check). `./art final` adds GATE T (type check). All passed.

The bookend check is separate and was run by hand:
```bash
python3 runtime/scripts/bookend_check.py ~/Documents/info7375-film/youtube/glucotrace-pitch
```
It reports one expected failure (OUTRO), explained in FRICTIONAL.md.

## 7. Copy results into the submission folder
```bash
REEL=~/Documents/info7375-film/youtube/glucotrace-pitch
SUB=~/GlucoTrace/fall-2026/yashika-l/final-project-film
mkdir -p $SUB/gate-reports
cp ~/Documents/brutalist.art/renders/glucotrace-pitch.mp4 $SUB/
cp $REEL/beat_sheet.json $REEL/PEDAGOGY.md $REEL/FACTCHECK.md $SUB/
cp $REEL/TYPECHECK.md $REEL/layout_audit.md $REEL/layout_audit.json $REEL/build-state.json $REEL/SHOTLIST.md $REEL/PROMPTS.md $SUB/gate-reports/
cp $REEL/_qc/REPORT.md $SUB/gate-reports/frame_check_REPORT.md
cp $REEL/_qc/contact_sheet.png $SUB/gate-reports/
cd ~/Documents/brutalist.art
python3 runtime/scripts/bookend_check.py $REEL > $SUB/gate-reports/bookend_check.txt 2>&1
```