# SHOTLIST — glucotrace-pitch
# Typed work order per beat. DRAFT 2026-10-24 — durations are estimates until audio is generated.

Skill: ai-explainer (Claude palette). Voice: Kokoro `af_bella`, first person as Yashika.
Film title: "GlucoTrace — Final Project Pitch".
Every beat is a Manim line drawing in `scenes.py`, drawn from the beat's `shot.visual_intent` only;
on-screen words are only `shot.on_screen_text` plus labels the visual description names.
Each `shot.show` event lands when its `at` phrase is spoken (phrase position × audio length).

Deliberate deviations from the skill (course assignment forbids persona/credit lines):
- No Claude cold open, hesitant-writer overview, verdict page, Your Turn or title outro.
  B00 is the opening, B10 the closing. `bookend_exempt: ["cold-open", "bvdt", "bhtf"]`.
- No outro beat: `ClaudeTitleOutro` hard-codes `@NikBearBrown` (no handle prop), so
  `bookend_check.py` will still report `OUTRO (BOUT): no ClaudeTitleOutro beat`.
- No Liam, "in for Bear", @NikBearBrown, instructor name or credit line anywhere.
- No logos on B02 (Oura, Dexcom) or B05 (Claude): visuals are drawn from the descriptions only.

## Body

B00 · B00_Title · ~13s
  source: manim → manim/B00.mp4
  draws: title text; hand-drawn glucose curve; terracotta checkmark on a peak
  text: "GlucoTrace (working title) — a pitch"
  status: RENDERABLE (preview checked)

B01 · B01_Problem · ~14s
  source: manim → manim/B01.mp4
  draws: two phones far apart (glucose line / heart); speech bubble with terracotta "?"
  text: none
  status: RENDERABLE (preview checked)

B02 · B02_Existing · ~19s
  source: manim → manim/B02.mp4
  draws: two closed boxes, device icon inside each, terracotta padlock on each
  text: "Oura + Stelo" · "Dexcom app" (on_screen_text split at "·", one under each box)
  status: RENDERABLE (preview checked)

B03 · B03_Idea · ~11s · CONSTRUCTED
  source: manim → manim/B03.mp4
  draws: one timeline — glucose line on top, meal markers, heart-rate band below;
         a sentence (placeholder strokes, no words) with thin lines to two dots on the curve
  text: "CONSTRUCTED — sketch, not built" (visible the whole beat)
  status: RENDERABLE (preview checked)

B04 · B04_Data · ~14s
  source: manim → manim/B04.mp4
  draws: spreadsheet grid; terracotta arrow into a small timeline sketch
  text: "Public dataset: CGMacros (PhysioNet)"
  status: RENDERABLE (preview checked)

B05 · B05_Pipeline · ~15s
  source: manim → manim/B05.mp4 (own three boxes — not SkillTeardownPipeline)
  draws: three boxes in a row with arrows; "Code checks" box outlined terracotta
  text: "Code computes" → "Claude explains" → "Code checks"
  status: RENDERABLE (preview checked)

B06 · B06_Verification · ~12s
  source: manim → manim/B06.mp4
  draws: three claim cards (placeholder strokes) with a check, an X, a terracotta stop sign
  text: "verified" · "failed" · "blocked"
  status: RENDERABLE (preview checked)

B07 · B07_WhoOpens · ~18s · CONSTRUCTED
  source: manim → manim/B07.mp4
  draws: meal card; chart with two terracotta highlighted points; small tab labelled Evaluation
  text: "Evaluation"; "CONSTRUCTED — mock-up, not built" (visible the whole beat)
  status: RENDERABLE (preview checked)

B08 · B08_HaveLearning · ~16s
  source: manim → manim/B08.mp4
  draws: paper with two columns, three simple icon tiles in each ("Learning" side terracotta)
  text: "Have" · "Learning"
  status: RENDERABLE (preview checked)

B09 · B09_OutOfScope · ~17s
  source: manim → manim/B09.mp4
  draws: picket fence; stethoscope, crystal ball, prescription pad, each crossed out in
         terracotta as it is named
  text: "No diagnosis" · "No predictions" · "No medical advice"
  status: RENDERABLE (preview checked)

B10 · B10_FirstRun · ~14s · CONSTRUCTED
  source: manim → manim/B10.mp4
  draws: one table row, columns claim / result / date, terracotta checkmark in the last cell
  text: "claim", "result", "date"; "CONSTRUCTED — planned log row" (visible the whole beat)
  status: RENDERABLE (preview checked)

## Order of work
1. Fill FACTCHECK.md verdicts and sign PEDAGOGY.md.
2. `python3 runtime/scripts/generate_audio_kokoro.py <reel>` — audio is the clock.
3. `./art run <reel>` — renders scenes.py at 4K, Gates A/W/B/L/F/V, slate cut.
