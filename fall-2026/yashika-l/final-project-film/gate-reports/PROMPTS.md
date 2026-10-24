# PROMPTS — glucotrace-pitch
# Beat-prefixed prompts for open slots. DRAFT 2026-10-24.

## Open slots: none

Every beat is drawn by `scenes.py` (Manim, local, free). No pantry images, no generated
stills, no AI video, no paid calls. Nothing needs to be dropped into `pantry/` or `media/`.

## Drawing briefs (the instruction each Manim scene was written from)

Rules for every beat: Claude palette (cream #F2F0E9, ink #3D3929, one terracotta #D97757
moment); simple line drawings; draw only what `shot.visual_intent` describes; no words on
screen except `shot.on_screen_text` and labels the description itself names; CONSTRUCTED
caption visible for the whole beat on B03, B07, B10; each `shot.show` event lands on its
`at` phrase.

- **B00:** Title card. A hand-drawn glucose curve with a small checkmark on it.
- **B01:** Two phones drawn far apart, one with a glucose line, one with a heart. Between them, a speech bubble with a question mark.
- **B02:** Two closed boxes, each with a small padlock and a device icon inside.
- **B03:** Sketch of one timeline: a glucose line on top, meal markers, heart-rate band below. A sentence with a thin line pointing to two dots on the curve.
- **B04:** A drawn spreadsheet with an arrow into the timeline sketch.
- **B05:** Three boxes in a row with arrows: Code computes → Claude explains → Code checks. (Own boxes, not the five-box pipeline scene.)
- **B06:** Three drawn claim cards: one with a check, one with an X, one with a stop sign.
- **B07:** Sketch of a meal card next to a chart with two highlighted points, and a small tab labelled Evaluation.
- **B08:** Two columns drawn on paper: 'Have' and 'Learning', with a few icons in each.
- **B09:** A fence. Outside it: a stethoscope, a crystal ball, a prescription pad, each crossed out as it is named.
- **B10:** A single drawn table row with columns claim, result, date, and a checkmark.

## Session decisions (2026-10-24)
- Field names restructured to match `examples/ai-explainer/claude-debunked/beat_sheet.json`; narration, visual descriptions, on-screen text and CONSTRUCTED labels unchanged.
- `./art scenes` found no library scene matching any beat, so each beat is a Manim drawing.
- Bookends deliberately omitted; `bookend_exempt: ["cold-open", "bvdt", "bhtf"]`; no outro (handle is hard-coded).
- Voice stays Kokoro `af_bella`, first person; no persona, voice line or credit.
