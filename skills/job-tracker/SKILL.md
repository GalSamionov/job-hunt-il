---
name: job-tracker
description: >
  This skill should be used when the user asks "איפה אני עומד", "כמה הגשתי", "תעדכן את המעקב",
  "טבלת מעקב", "תרשום שהגשתי", "track my applications", or whenever another skill in this
  plugin needs to log an application, an outreach contact or a status change.
---

# Job tracker

> If `job-search/profile.md` does not exist yet, run the job-hunt-onboarding skill first.

Keep two lists current: applications and outreach contacts. They are the memory of the whole search.

## Where to keep them
- If the session offers the Artifact tool with a shared database: create one tracker page with two collections, `applications` and `contacts`, and update rows through the database rather than republishing the page.
- Otherwise keep `job-search/applications.csv` and `job-search/contacts.csv` in the working folder (UTF-8 with BOM so Excel shows Hebrew), and offer an XLSX export.

## Fields
- applications: id, date, company, title, city, source, link, track, cv_version, status, next_step, next_date, contact, notes.
- contacts: id, date, name, title, company, profile_link, channel, message_variant, status, last_contact, next_date, notes.

## Statuses
applications: to_apply, applied, screening_call, interview, home_task, offer, rejected, withdrawn, no_answer.
contacts: prepared, sent, accepted, replied, call_set, cold.

## Rules
- Dedupe by link, then by company + title (applications) or profile link (contacts).
- Log the CV version for every application.
- When the user reports news ("עברתי שלב", "אמרו לא"), update the status and set the next step and date.
- On request, give a short status summary: applied this week, open processes by stage, follow-ups due, replies waiting.

## Language and style (always)
- Talk to the user in Hebrew unless they write in another language.
- Never use em dashes. Use commas, colons or separate sentences.
- Do not start a Hebrew line or bullet with an English word; it breaks right-to-left display. Rephrase so the line starts in Hebrew.
- Avoid Latin variables or math notation inside Hebrew lines.
- Be direct and short. No preamble, no restating the request.
