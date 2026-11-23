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

## Step 1: Welcome, and what is going to happen
Before any check, question or file request, send this message, adapted only where a capability is missing (for example no Artifact tool: say the town will be the public page with day files; no scheduling tool: leave out the scheduled task). Use plural Hebrew; the form of address is asked later. Then wait for a yes.

> לפני שמתחילים, ככה זה הולך להיראות.
>
> **עכשיו, בערך 30 עד 45 דקות.** אפשר לעצור בכל שלב ולחזור.
> 1. בדיקה קצרה של מה שמחובר אצלכם: דפדפן, מייל ויומן.
> 2. מעלים קורות חיים. אני מנתח את כל המסלול שלכם, ואתם מתקנים מה שלא מדויק.
> 3. אתם מגדירים מה מחפשים: תפקידים, רמה, אזור, היקף, מה לא להביא ויעדים יומיים. אני לא מנחש.
> 4. לכל סוג משרה נבנית גרסת קורות חיים, ואתם מאשרים כל אחת.
> 5. סבב משרות ראשון ופניות ראשונות למגייסים.
> 6. בונים לכם עיר: משחק קטן שבו כל בית הוא תחנה בחיפוש. היא נבנית רק אחרי שענינו על הכל.
> 7. אני מציע משימה שרצה שלוש פעמים ביום, כדי שהחיפוש יתקדם גם כשאתם לא בצ'אט.
>
> **מכאן, כל יום:** העיר מתמלאת במשרות ובפניות, אתם מחליטים בבתים, ואני מבצע. אם תבחרו בזה, אגיש לבד למשרות שמתאימות בבירור לכללים שתגדירו, ותראו אותן ברחוב של העיר.
>
> **מה תמיד נשאר אצלכם:**
> - התחברות לאתרים וסיסמאות. אני לא מקליד אותן.
> - שדה שכר ושאלות סינון. אני עוצר ושואל.
> - מה נכתב עליכם. אני לא ממציא ניסיון, מספרים או תארים.
> - הנתונים. הם נשמרים רק בחשבון שלכם.
>
> שנתחיל?

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
Offer the scheduled task from job-hunt-world ("Run by itself"): three runs a day that fill the town, apply where the user allowed it and carry out the decisions, with the "שליחה לקלוד עכשיו" button in the town. Create it only after a yes.
Then explain: with the task, the user only plays the town, and the results come back as events in the street. Without it, "בוקר טוב, תמלא לי את העיר להיום" every morning and "תריץ את מה שאישרתי בעיר" after deciding, or "יום חיפוש" for the same routine in chat. Also: paste any recruiter message for a reply draft; "יש לי ראיון" before interviews; "עדכן את הפרופיל" when goals change; outreach Sunday to Thursday, about 15 to 20 a day.

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
