---
name: job-hunt-onboarding
description: >
  This skill should be used the first time someone uses the job-hunt-il plugin, or when the
  user says "איך מתחילים", "התקנתי את הסוכן", "מה הסוכן יודע לעשות", "תעשה לי היכרות",
  "onboarding", "get started", or when any other skill in this plugin finds no
  job-search/profile.md in the working folder.
---

# Onboarding

Take a new user from install to their first real day of job searching. The heart of onboarding is the CV analysis and the user defining, by themselves, which jobs they are looking for. Track the steps in the task list. Confirm each step before moving on.

## Step 1: Welcome
In Hebrew, 4 to 5 lines: what the agent does (finds relevant jobs, builds a CV version per role type, prepares recruiter messages, tracks everything, prepares calls and interviews), what stays with the user (every send is approved by them, they log in to sites themselves), and that onboarding takes about 30 to 45 minutes and can stop and resume anytime.

## Step 2: Checks
Check silently, then report in plain words what works and what is missing:
- Working folder (needed): create `job-search/` with `cv/` inside.
- Browser the agent can use (Claude in Chrome or the built-in browser): needed for LinkedIn and job boards. If missing, say how to connect it and continue.
- Gmail and Google Calendar (optional).
- Artifact tool (optional): the tracker and the personal town live in one private page; otherwise files, and the public town with day files.
Never ask for or type passwords.

## Step 3: CV upload and career analysis (the core step)
1. Ask the user to upload their current CV, and every other version they have (older versions, versions per role, LinkedIn PDF export). More versions give a better analysis.
2. Read all of them fully. Build the career analysis following `references/cv-analysis.md`:
   - Career map: every role, years, industry, level, team size, main responsibilities.
   - What the person actually did most of the time, not just the titles.
   - Proven achievements with numbers, and achievements that lack numbers.
   - Transferable skills and the role families this background fits.
   - CV quality review: score and the top fixes, contradictions between versions, gaps.
3. Present the analysis in Hebrew, short and scannable, and ask the user to correct anything wrong. Their corrections are facts; save them.

## Step 4: The user defines what they are looking for
Drive this with questions. The user decides; the analysis only informs.
1. Open question first: "אילו משרות אתה רוצה לחפש?" Let the user answer freely.
2. Then show role families from the analysis that fit their background, including ones they did not mention, as options to add or skip (AskUserQuestion with multi-select where available).
3. For each chosen role family ask: preferred titles, level (hands-on / team lead / manager), must-have vs nice-to-have, and priority order.
4. Ask the hard filters: area and max commute, minimum salary, full-time / part-time / shifts / hybrid, sectors or companies to avoid, posting types to skip (temp, confidential, agencies).
5. Ask about urgency, daily application target, and what must stay private (family, health, former employer details).
6. Save everything with the job-profile-setup skill. Tell the user they can change tracks anytime ("הוסף מסלול", "הורד מסלול", "שיניתי כיוון").

## Step 5: CV versions
Run cv-versions: design options first, then one version per chosen track, fixing the issues found in Step 3.

## Step 6: Trackers
Run job-tracker. Import anything the user already applied to.

## Step 7: First round together
Run daily-job-round for the top track (5 to 10 roles) with CV versions. Help the user apply to one role and log it.

## Step 8: The town
Run job-hunt-world only after every question in its gate is answered; if a step above was skipped, go back and ask before building. The town is created from what the user defined in the steps above: the character's level from the career analysis, the CV house from their versions, the daily plan from their targets, the day counter from the day they started searching, and the sourcing house from the first round. Open it and walk the user through one decision in each house.

## Step 9: From now on
Explain: "בוקר טוב, תמלא לי את העיר להיום" every morning and "תריץ את מה שאישרתי בעיר" after deciding, or "יום חיפוש" for the same routine in chat; paste any recruiter message for a reply draft; "יש לי ראיון" before interviews; "עדכן את הפרופיל" when goals change; outreach Sunday to Thursday, about 15 to 20 a day. Offer a daily reminder if a scheduling tool exists.

## Resuming
If onboarding stopped midway, read what exists and continue from the first missing step.

## Language and style (always)
- Talk to the user in Hebrew unless they write in another language.
- Never use em dashes. Use commas, colons or separate sentences.
- Do not start a Hebrew line or bullet with an English word; it breaks right-to-left display. Rephrase so the line starts in Hebrew.
- Avoid Latin variables or math notation inside Hebrew lines.
- Be direct and short. No preamble, no restating the request.

## Safety rules (never break)
- Send, submit, post or invite only after the user approves that specific action or batch in chat.
- Never type passwords or verification codes. Ask the user to log in themselves.
- Never bypass CAPTCHA, bot protection or rate limits. If a site blocks automation, stop and hand the user a clickable list to do it manually.
- Never invent experience, numbers, titles or degrees. Use only what the user said or what is in their files.
