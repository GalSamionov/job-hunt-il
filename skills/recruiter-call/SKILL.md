---
name: recruiter-call
description: >
  This skill should be used when a recruiter or employer contacts the user, or the user asks
  "מה לענות למגייסת", "שאלו על ציפיות שכר", "קיבלתי הצעה", "הצעה לשיחה", "מה לשאול",
  "salary expectations", "negotiate the offer", or pastes a WhatsApp, email or LinkedIn
  message from a recruiter.
---

# Recruiter call and salary

> If `job-search/profile.md` does not exist yet, run the job-hunt-onboarding skill first.

Help the user answer recruiters fast and well, and get the facts that decide whether a role is worth it.

## Steps
1. Read the profile (tracks, hard filters, salary range, privacy) and the job details the user shared.
2. Give a short fit verdict: what matches, what is a gap, and any conflict with the user's own rules (for example a city outside the radius). Say it plainly; the user decides.
3. Draft the reply in the user's voice: warm, specific, 3 to 6 lines. Lead with the strongest relevant proof. Ask the open questions from `references/questions-and-salary.md` that matter for this role.
4. If asked about salary, follow the salary rules in the reference. Adjust for outsourcing, commute and benefits.
5. Recommend which CV version to send.
6. Log the opportunity in the tracker with status and next step.

## Rules
- Answer factual questions truthfully (years of experience, skills). Help the user frame real experience; never inflate it.
- Do not send anything yourself. The user sends.
- This is general guidance, not legal or financial advice; mention it once if the user asks about contracts or terms.

## Language and style (always)
- Talk to the user in Hebrew unless they write in another language.
- Never use em dashes. Use commas, colons or separate sentences.
- Do not start a Hebrew line or bullet with an English word; it breaks right-to-left display. Rephrase so the line starts in Hebrew.
- Avoid Latin variables or math notation inside Hebrew lines.
- Be direct and short. No preamble, no restating the request.
