# SOURCES

## What I used
| Source | Used for | Licence / terms | Checked on |
|---|---|---|---|
| Brutalist toolkit — https://github.com/nikbearbrown/brutalist.art | Rendering the film (free local pipeline) | No licence file in the repo; used as directed by the course assignment | 2026-10-24 |
| Kokoro voice `af_bella` (kokoro-v1.0.onnx, bundled with Brutalist) | Narration: a synthetic voice reading my first-person script | Apache 2.0, from the original model hexgrad/Kokoro-82M (https://huggingface.co/hexgrad/Kokoro-82M); no licence file in the bundled folder | 2026-10-24 |
| CGMacros dataset, PhysioNet — https://physionet.org/content/cgmacros/1.0.0/ | Named as the planned demo data (no data used in the film) | CC BY-NC-SA 4.0. Dataset DOI 10.13026/3z8q-x658 | 2026-10-24 |
| CGMacros paper, Scientific Data — https://pmc.ncbi.nlm.nih.gov/articles/PMC12462512 | Fact-checking dataset claims | Cited only. DOI 10.1038/s41597-025-05851-7 | 2026-10-24 |
| Oura Glucose Tracking page — https://support.ouraring.com/hc/en-us/articles/39145979972115-Glucose-Tracking | Alternative named in the pitch (Oura + Stelo) | Cited only | 2026-10-24 |
| Dexcom GenAI press release — https://investors.dexcom.com/news/news-details/2024/Dexcom-Launches-the-First-Generative-AI-Platform-in-Glucose-Biosensing/default.aspx | Alternative named in the pitch (Stelo by Dexcom app) | Cited only | 2026-10-24 |
| MD+DI article — https://www.mddionline.com/wearable-medical-devices/dexcom-ura-move-into-next-phase-of-partnership | Fact-checking the Oura + Stelo claims | Cited only | 2026-10-24 |

## What I made
- The project idea, scope decisions, name (GlucoTrace), and final wording of the brief and narration.
- The visual description for every beat. The drawings themselves were drawn by Claude Code as new Manim scenes from my descriptions.
- The fact check: I checked all 17 claims against the sources above and wrote every verdict.

## What Claude contributed
- **Claude (claude.ai chat), 2026-10-24:** brainstormed project options, searched for public CGM + wearable datasets and competing products, helped narrow scope, and drafted PROJECT-BRIEF.md, beat_sheet.json, README.md, BUILD-PROMPT.md, SOURCES.md, and FRICTIONAL.md.
- **Claude Code, 2026-10-24:** reformatted beat_sheet.json to the toolkit's format; drew all 11 beats as Manim scenes; drafted SHOTLIST.md, PROMPTS.md, and the FACTCHECK.md claim list; made the fixes I asked for (title, cue timing, two fact-check corrections, safe-area layout fixes); generated the audio and ran the render. The exact prompts are in BUILD-PROMPT.md.
- **What I changed or checked myself:** chose the project and scope; edited the narration; verified every claim on PhysioNet, the CGMacros paper, Oura's page, and Dexcom's press release; corrected B01 (softened an unsupported claim) and B02 (corrected the app name); signed Gate P and Gate F; reviewed each change Claude Code proposed before approving it.

## Third-party assets
- EB Garamond font, used for on-screen text. Set by the Brutalist ai-explainer skill's default "claude" style preset and bundled with the toolkit. Licence: SIL Open Font License 1.1 (runtime/fonts/EB_Garamond/OFL.txt in the toolkit).
- No logos, photos, or other third-party images. Competitor products are named in text only.