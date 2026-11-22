---
name: job-profile-setup
description: >
  This skill should be used when the user starts a job search with the plugin, or says
  "בוא נתחיל לחפש עבודה", "הקמת פרופיל", "תכיר אותי", "עדכן את הפרופיל שלי",
  "שיניתי כיוון", "set up my job search profile". Builds and maintains the job-search
  profile that every other skill in this plugin reads.
---

# Job search profile

Build `job-search/profile.md` in the working folder. Every other skill reads it first, so keep it accurate and current.

## Steps
1. Check whether `job-search/profile.md` exists. If it does, read it and only ask about what changed.
2. Ask for the current CV (file or text) and LinkedIn profile URL. Read the CV before asking anything it already answers.
3. Interview the user in short rounds (AskUserQuestion where available, max 4 questions per round). Cover the fields in `references/profile-template.md`. Do not ask what the CV already answers.
4. Let the user define their **tracks** (role families) through questions: ask what they want first, then offer fitting role families from the CV analysis as options to add or skip. The user decides. Each track gets its own CV version later. Support changing tracks anytime ("הוסף מסלול", "הורד מסלול", "שיניתי כיוון").
5. Write the profile from the template. Show a short summary in Hebrew and ask for corrections.
6. Suggest the next step: building CV versions (cv-versions skill).

## What matters most
- **Hard filters** the user states (location radius in minutes from home, minimum salary, full-time only, no shifts, no temp, no confidential "חסוי" postings) are rules. Every skill must respect them.
- **Privacy**: record what the user does NOT want mentioned publicly (family situation, health, reason for leaving, former employer's name). Respect it in every output.
- **Urgency and volume**: record whether the user needs a job urgently and how many applications per day they want.
- Update the profile whenever the user changes direction ("פחות ניהול פרויקטים, יותר AI"). Append a dated line to the change log section.

## Language and style (always)
- Talk to the user in Hebrew unless they write in another language.
- Never use em dashes. Use commas, colons or separate sentences.
- Do not start a Hebrew line or bullet with an English word; it breaks right-to-left display. Rephrase so the line starts in Hebrew.
- Avoid Latin variables or math notation inside Hebrew lines.
- Be direct and short. No preamble, no restating the request.
