Pain Pattern Diary

A lightweight, single-file web app for tracking chronic back pain and finding the patterns behind it: when it flares, what precedes it, and how much it actually interferes with daily life.

Live demo: https://timhan78.github.io/pain/pain_diary.html


A note on language. The user interface is in Russian. This is intentional: the app was built for a specific person,  a daily-use tool for one real user, not a generic demo, and Russian is the language they think and self-report in.  Pain and mood are easiest to record honestly in your first language, so the interface follows the user rather than the portfolio. The data model, field names, and CSV export are all in English, so the dataset stays analysis-ready for any English-language tooling (pandas, Power BI, etc.).



What it does

The goal isn't just to log a pain score: it's to surface relationships the user can't easily see day to day:

Does pain rise on workdays versus days off?
Does walking help, hurt, or do nothing?
Does prolonged standing track with worse evenings?
How much does pain interfere with life, separately from how intense it is?


Features


Daily entry with morning and evening pain check-ins across multiple body zones (0–10 scale)
Quick in-day logging: one-tap timestamped notes (e.g. "sat too long", "walked 5 km")
Activity tracking: walking, standing, lifting, travel, exercise and its effect
Autosave: every change is written to local storage; no "save" button anxiety

CSV export / import with date-based merge, so data can be moved between devices and kept as a backup
Charts:  pain over time, intensity vs. interference, averages by day type, and scatter plots for activity-vs-pain
Automatic analysis: 7- and 30-day rolling averages, group comparisons, and a plain-language summary that flags likely triggers using correlation rather than eyeballing
Red-flag warning for symptom combinations that warrant urgent medical review


Analytics approach

The summary is deliberately cautious about causation. Comparing pain on days with an activity versus without it is only a first signal, it can be confounded by reverse causation (you reach for relief precisely on bad days). The app therefore favours correlation strength over single-day anecdotes and surfaces possible triggers as hypotheses to investigate, not conclusions.

Tech stack


Vanilla JavaScript, HTML, CSS  no framework, no build step
Chart.js for visualisations
Browser localStorage for persistence (no backend, no account, no data leaves the device)
Single .html file open it anywhere, host it anywhere


Privacy

All entries live only in the browser on the user's own device. Nothing is uploaded. The exported CSV is the only copy that leaves the browser, and only when the user chooses to create it.

Disclaimer

This is a personal self-tracking tool, not a medical device. It does not diagnose, treat, or replace professional medical advice.
