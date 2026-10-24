# PROJECT-BRIEF — GlucoTrace (working title)

**Yashika Lodh** · INFO7375, Fall 2026 · Written 2026-10-24
**Target role:** early-career frontend / full-stack engineer (React + TypeScript), on teams building AI product features.
**Stack (planned):** Python script to clean the public dataset · React + TypeScript web app · Claude API for explanations · Zod schemas for AI output · Vitest tests · deployed on Vercel.

---

## 1. What is it?
A web app that will show glucose next to meals, heart rate, and activity, and explain the patterns in plain language, where **every AI sentence is checked against the data before it is shown.**

When it is done, it will exist as: a **deployed web app**, a **public GitHub repository** (code, prompt contract, tests), and an **evaluation page and log** showing how many of Claude's claims were verified, failed, or blocked.

## 2. Why would anyone care?
For an adult who wears a glucose monitor (CGM) and a fitness tracker, it will turn "here is your glucose graph" into explanations they can check: click any sentence and see the exact readings behind it.

Alternatives I looked at (public pages only; I don't own these devices):
- **Oura + Dexcom Stelo** shows Stelo glucose beside Oura sleep and activity. It requires a Stelo sensor, an Oura Ring (Gen3 or Ring 4), and an Oura membership.
- **Dexcom's own app** offers AI insights inside Dexcom's closed app.

What mine will do differently: it will work from export files instead of one hardware pairing, and it will **publish how often its AI was wrong.** I could not test the alternatives, so I am not claiming they have no internal checks, only that I could not find a published accuracy record.

## 3. Who opens it, and what do they do?
**Reader:** a hiring manager or engineer reviewing my portfolio. **End user:** an adult with a CGM and a fitness tracker.
**First 60 seconds:** open the link → pick a study participant and a day → read a meal card ("glucose rose about 60 points and settled in about two hours") → click it and see the readings highlight on the chart → open the Evaluation page to see the counts and real examples of Claude's mistakes.

## 4. What does it prove about me?
- **Prompt contracts:** Claude must return structured claims that cite computed facts, enforced by a schema.
- **Verification:** code computes every number; code checks Claude's numbers, times, and citations, and blocks medical or cause-and-effect language.
- **Evaluation:** every claim logged as verified, failed, or blocked, plus a hand-reviewed sample.
- **Source grounding:** every sentence links to the data points it uses.
- **Frontend:** an accessible, responsive React data-visualization UI.

A reviewer could fairly conclude that I can build an AI feature that refuses to show unchecked claims, and measure how well it works. Evidence will be the repo, the tests, the evaluation log, and the live link. I will **not** claim medical validity or results that generalize beyond the study participants.

## 5. What is in, what is out, what comes first?
- **In (core):** public data on one timeline · daily summary · meal response · Claude meal and day explanations · verification layer · evaluation log and page · participant picker · disclaimers · accessible UI · deployed link · README · tests.
- **Later:** "ask your data" agent · uploading your own exports (processed in the browser only) · activity-load score · pattern comparisons · cited knowledge base · photo carb estimates.
- **Out, deliberately:** it will not diagnose, give medical advice, predict glucose, or place anyone in a health group.
- **First piece that runs:** one participant, one day. Code computes one meal's response, Claude explains it, the verifier checks it, and one row is written to the evaluation log. **How you will know it ran:** a dated log row committed to the repo, a passing verifier test, and one README command that reproduces it.

## 6. What could sink it?
**Risk:** the verifier can only catch what a machine can check. Claude could write a sentence with correct numbers but misleading framing ("this was a bad meal"), and a number check would pass it.
**What I will do:** limit claims to a small fixed set of checkable types (rise, peak time, recovery time, daily high and low). Any sentence outside those types will be shown as "unverified," never as fact. I will hand-review a sample and report it separately, even if the unverified share is high.
**Known limit:** the dataset is small (45 adults, about 10 days, no sleep data), so the app will describe patterns, not causes.

## 7. Why this project?
A mix, leaning toward learning. I am interested in wearables and glucose, and I wanted a project where the AI's output can be checked against real numbers.
- **Skills I already have:** React, TypeScript, state management, accessible UI. Evidence: my public repositories at github.com/yashika-lodh, including my Buffett Intelligence RAG project. My WCAG 2.1 AA work at NewEra IT is not public, so for accessibility I will point to this app's own audit results instead.
- **Skills that are new to me:** cleaning time-series health data, designing a verifier, building an evaluation set, and health-domain guardrails.
- **What I don't know yet:** what share of Claude's claims will pass. I will find out from the first runnable piece and its log.

---

## Exists today (2026-10-24)
- This brief, the beat sheet, and the pitch film.
- No application code, no tests, no evaluation results.

## Will exist
- Data-cleaning script for the public dataset.
- React + TypeScript app: timeline, daily summary, meal cards, participant picker, disclaimers.
- Claude prompt contract and schema; verifier; evaluation log and page.
- Tests, README, deployed link.
- Later: agent, file upload, activity load, pattern comparisons, cited sources, photo carb estimates.