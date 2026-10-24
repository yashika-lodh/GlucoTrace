# FACTCHECK — glucotrace-pitch

Status: **OPEN — verdicts to be filled in by Yashika.** DRAFT 2026-10-24.
Fill each Verdict (PASS / FIX / CUT) after checking the named source. If a claim needs a
narration change, change it in beat_sheet.json and regenerate the audio.

## Factual claims (need a source)
| # | Beat | Claim (as spoken / shown) | Source to check | Verdict | Notes / fix |
|---|---|---|---|---|---|
| 1 | B00 | "Nothing is built yet" | Own repo | PASS | github.com/yashika-lodh/GlucoTrace contains only pitch files as of 2026-10-24 |
| 2 | B01 | Glucose-monitor and fitness-tracker data usually live in separate places | Oura Glucose Tracking page | PASS | General statement; Oura's integration supports only the Stelo sensor, and B02 names it as the exception. Checked 2026-10-24 |
| 3 | B01 | When an app explains the data, you usually can't see what the explanation is based on | Oura Glucose Tracking page; Dexcom press release | FIX | Neither page shows how a given insight was derived, but "usually can't see" was stronger than I could verify. Narration changed to "it's often hard to see what the explanation is based on." 2026-10-24 |
| 4 | B02 | Oura with Dexcom's Stelo shows glucose next to sleep and activity | https://support.ouraring.com/hc/en-us/articles/39145979972115-Glucose-Tracking | PASS | Page: view Stelo glucose data alongside Oura insights. Checked 2026-10-24 |
| 5 | B02 | Dexcom's own app has AI insights | https://investors.dexcom.com/news/news-details/2024/Dexcom-Launches-the-First-Generative-AI-Platform-in-Glucose-Biosensing/default.aspx | PASS | GenAI Weekly Insights in the Stelo app. Checked 2026-10-24 |
| 6 | B02 | Both are tied to specific hardware | Oura Glucose Tracking page | PASS | Oura needs Ring Gen3 or later, active membership, Stelo account; integrates only with the Stelo sensor. Stelo app reads the Stelo biosensor. Checked 2026-10-24 |
| 7 | B02 | From their public pages, no published record of how often their AI is wrong | Oura page, Dexcom press release, MD+DI article | PASS | None publishes an AI error rate. Oura cites Stelo *sensor* accuracy (93%), which is sensor accuracy, not AI accuracy. Checked 2026-10-24 |
| 8 | B02 / screen | "Oura + Stelo · Dexcom app" | Oura page; Dexcom press release | FIX | App is named "Stelo by Dexcom". On-screen text changed to "Oura + Stelo · Stelo by Dexcom app"; narration unchanged |
| 9 | B04 | CGMacros is a public research dataset | https://physionet.org/content/cgmacros/1.0.0/ | PASS | Open Access on PhysioNet; DOI 10.13026/3z8q-x658. Checked 2026-10-24 |
| 10 | B04 | Forty-five adults | PhysioNet page; https://pmc.ncbi.nlm.nih.gov/articles/PMC12462512 | PASS | 45 participants, ages 18–69 |
| 11 | B04 | Healthy, prediabetic and type 2 participants | PhysioNet page | PASS | 15 healthy, 16 prediabetes, 14 type 2 |
| 12 | B04 | About ten days of data per participant | PhysioNet page | PASS | Ten consecutive days; data spans approximately ten days |
| 13 | B04 | Meals are logged | PhysioNet page | PASS | Meal calories, carbs, protein, fat, fiber and meal type recorded at the meal's timestamp |
| 14 | B04 | Recorded data, not live, so anyone can check it | PhysioNet page, Access section | PASS | Access Policy: anyone can access the files, under the licence. Licence: CC BY-NC-SA 4.0. Checked 2026-10-24 |
| 15 | B04 / screen | "Public dataset: CGMacros (PhysioNet)" | PhysioNet page | PASS | Same as row 9 |
| 16 | B05 | Rise after a meal, peak time and time to settle can be computed from the data | PhysioNet page; paper Data Records section | PASS | CGM readings at 1-minute intervals with meal info on the same timestamped rows; paper also reports Fitbit heart rate and METs per minute |
| 17 | B08 | React, TypeScript and accessible UI are skills you already have | Own GitHub | PASS | React + TypeScript: github.com/yashika-lodh/Waypoint (Next.js, React 19, TypeScript). Accessibility: professional WCAG 2.1 AA work at NewEra IT, not public; GlucoTrace's own accessibility checks will be the public evidence. Checked 2026-10-24 |

## Plan statements (future tense, no source needed; check they still say "will")

| # | Beat | Statement |
|---|---|---|
| P1 | B03 | The app will put glucose, meals, heart rate and activity on one timeline; every AI sentence will link to its readings |
| P2 | B05 | Code will compute the numbers; Claude will only explain them and must cite each one |
| P3 | B06 | Code will check every claim; wrong numbers and missing citations fail; medical / cause-and-effect language is blocked; flagged claims are never shown as fact |
| P4 | B07 | A hiring manager will pick a participant and day, click a meal explanation, and open the evaluation page |
| P5 | B08 | The project is meant to show verification-first AI features and their measurement |
| P6 | B09 | It won't diagnose, predict glucose or give medical advice; claims outside the checkable types will be marked unverified and reviewed by hand |
| P7 | B10 | The first run is one participant, one day, one meal, written as one row in the evaluation log |

**GATE F:** sign here after every row in the first table has a verdict. Signed: [ x ] Yashika Lodh Date: 2026-10-24
