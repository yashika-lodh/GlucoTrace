# FRICTIONAL — dated log

All entries are from 2026-10-24. Times are approximate, from file save times, git commits, and my chat history.

## Project decisions
- **~11:30 AM — Changed project.** Started with a WCAG accessibility-audit skill, but similar LLM auditors already exist. Switched to a glucose + wearable app, which has real numbers to check AI output against.
- **~11:45 AM — No WHOOP or live data.** No public WHOOP dataset exists, and my own wearable data can't be used. Live Fitbit sync is out of scope because the Fitbit API is being replaced by the Google Health API, which needs a privacy review.
- **~11:50 AM — Changed the pitch.** Found Oura + Dexcom Stelo already shows glucose beside sleep and activity. Changed the angle from "first to combine them" to "explanations you can check."
- **By 12:30 PM — Changed dataset.** Switched from HUPA-UCM (type 1 only) to CGMacros, which includes healthy and prediabetic adults and logged meals. It has no sleep data, so I dropped sleep from the pitch.
- **Before 1:30 PM — Cut scope.** Moved the "ask your data" agent from core to later.

## Setup problems
- **~1:35 PM — Setup hung.** ./setup --install finished, but re-running ./setup seemed to hang. Stopped it and ran ./art smoke instead, which passed.
- **Before 2:20 PM — Wrong folder and file name.** The reel folder ended up inside my repo, and the beat sheet was named beat-sheet.json. Moved the folder out and renamed it beat_sheet.json.
- **Afternoon (exact time not recorded) — No push access.** A classmate shared a message from a TA saying students can't push to the course repo yet and should submit the zip on Canvas. Submitting the zip on Canvas, with a matching copy in my own repo.

## Toolkit conflicts
- **~2:40 PM — Instructor bookends.** The ai-explainer skill requires a Claude chat-window opening and an outro with the instructor's handle, which the assignment forbids. Exempted three bookends. The outro's handle is hard-coded, so I left it out, and bookend_check.py reports one OUTRO failure.
- **~2:50 PM — No matching scenes.** No library scene fit my beats, so all 11 were drawn as new Manim scenes. Fixed a font gap that made the title read "Gluco Trace."

## Fact-check fixes
- **3:27 PM — Two claims corrected.** Softened B01 from "you usually can't see" to "it's often hard to see," since I couldn't support the stronger claim. Renamed "Dexcom app" to "Stelo by Dexcom app" on screen. 15 of 17 claims passed as written.
- **3:31 PM — Gates signed.** Signed Gate P and Gate F. Noted the CGMacros licence: CC BY-NC-SA 4.0, non-commercial only.

## Render
- **~3:50–4:16 PM — Render.** Six ./art run attempts to pass all gates (scene-loading bug, safe-area fixes on B03/B04/B07/B09/B10, frame-fill fixes, B08 cue timing). ./art final passed GATE T with 0 fails. Final film: glucotrace-pitch.mp4, 2:26, 4K. bookend_check.py still reports the OUTRO failure logged above.

## Submission
- **~5:05 PM — Accessibility evidence.** Ran a Chrome Lighthouse accessibility audit on my InnovateUS form (innovate-us.vercel.app): score 93, with two flagged issues (text contrast, and links distinguished by color only). Added it to PROJECT-BRIEF.md as public evidence of an existing skill.
- **5:28 PM — First Canvas submission.** Submitted the zip with commit d385ef9.

## After first submission
- **[time] — Resubmitted with small fixes.** Updated the beat_sheet.json notes (removed a leftover draft note; stated that the Kokoro voice was used), changed FACTCHECK.md's status to closed, and aligned FACTCHECK row 17 with the accessibility evidence in the brief. The film and narration are unchanged.