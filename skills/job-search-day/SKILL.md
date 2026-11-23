---
name: job-search-day
description: >
  This skill should be used when the user says "יום חיפוש", "בוא נתחיל את היום", "מה עושים היום
  בחיפוש העבודה", "שגרה יומית", "daily job search", or opens a session to run their whole
  job-search routine for the day.
---

# Job search day

> If `job-search/profile.md` does not exist yet, run the job-hunt-onboarding skill first.

Run the daily routine in one session, in this order, and keep the user in control of every send.

## Routine
1. **Status (1 minute):** read the profile and trackers. Show: open processes by stage, interviews coming up, follow-ups due today, replies waiting. Check the day: outreach only Sunday to Thursday.
2. **Replies and follow-ups first:** handle anything time-sensitive (recruiter replies, interview scheduling, thank-yous) with the follow-ups and recruiter-call skills.
3. **Job round:** run daily-job-round for the user's priority tracks; deliver the checklist with CV versions; log what the user applies to.
4. **Outreach:** on outreach days, prepare today's batch (default 15 to 20) with recruiter-outreach; send only after approval.
5. **Interview prep:** if an interview is within 48 hours, run interview-prep.
6. **Wrap-up:** short summary of the day (applied, contacted, replies, next steps with dates) and update the trackers.

## With the town
If `job-search/world.md` exists, the same day runs through the town: fill it in steps 3 and 4 instead of listing in chat (job-hunt-world, "Fill the town"), let the user decide in the houses, then carry out with one approval ("Carry out the decisions").

## Pace
- Ask once at the start if the user has limited time today, and shorten the routine to the top items.
- Batch approvals: one approval per batch of messages, showing every message.
- If a site blocks or asks for a login, pause that step, tell the user, and continue with the rest.

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
