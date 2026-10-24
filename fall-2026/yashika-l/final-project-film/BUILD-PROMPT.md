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
./art --list           # check whether a show-tell skill exists
```

## 2. Create the reel folder (outside the toolkit and outside the repo)
```bash
mkdir -p ~/Documents/info7375-film/youtube/glucotrace-pitch
cp ~/GlucoTrace/fall-2026/yashika-l/final-project-film/beat_sheet.json ~/Documents/info7375-film/youtube/glucotrace-pitch/
cp ~/GlucoTrace/fall-2026/yashika-l/final-project-film/PEDAGOGY.md ~/Documents/info7375-film/youtube/glucotrace-pitch/
```
Then align `beat_sheet.json` field names with `examples/ai-explainer/claude-debunked/beat_sheet.json` in the toolkit.

## 3. Prompt given to Claude Code (run inside ~/Documents/brutalist.art)
> Using skills/make/show-tell (or skills/make/ai-explainer if show-tell is not present), build the reel at ~/Documents/info7375-film/youtube/glucotrace-pitch from its beat_sheet.json. Keep my narration word for word. Narrate in first person as Yashika. Do not use the Liam persona, the "in for Bear" line, the @NikBearBrown chip, or the instructor's name or credit line anywhere, including bookends and outro. One simple drawn picture per beat, minimal on-screen text. Every beat labelled "constructed" must show the word CONSTRUCTED on screen. Do not invent metrics, users, screenshots, or product UI beyond the sketches described. Do not show a Claude response unless I supply a real one with its date. If a beat cannot be made, render it as a labelled slate and tell me what is needed.

[Paste any follow-up prompts you actually used here, with times.]

## 4. Gate P (narration review)
Read every narration line in `beat_sheet.json`, check it against the honesty rule, and sign `VERDICT: PASS` in `PEDAGOGY.md` in the reel folder.

## 5. Audio, render, fill-in, final
```bash
cd ~/Documents/brutalist.art
REEL=~/Documents/info7375-film/youtube/glucotrace-pitch
python3 runtime/scripts/generate_audio_kokoro.py $REEL   # audio sets the timing
./art run   $REEL     # review cut
./art todo  $REEL     # what still needs filling
./art final $REEL     # clean master
```
Narration: [delete one] my own recorded voice — [describe exactly how the audio files were replaced] / Kokoro `af_bella` reading my first-person script.

## 6. Quality gates
Run the gates listed in the chosen skill's `--help` and in `CLAUDE-CODE-VISUAL-QC-CHECK.md`. Re-render anything that fails the render-integrity check.

[Paste the exact gate commands you ran.]

## 7. Copy results into the submission folder
```bash
SUB=~/GlucoTrace/fall-2026/yashika-l/final-project-film
mkdir -p $SUB/gate-reports
cp $REEL/beat_sheet.json $REEL/PEDAGOGY.md $SUB/
cp $REEL/*-cut.mp4 $SUB/
# copy each gate report the toolkit produced into $SUB/gate-reports/
```