---
name: daily-job-round
description: >
  This skill should be used when the user asks to "find jobs", "תביא לי משרות", "סבב משרות",
  "משרות חדשות להיום", "מה יש לי להגיש", "תחפש לי עבודה", or wants a fresh list of relevant
  open positions with the CV version to send for each.
---

# Daily job round

> If `job-search/profile.md` does not exist yet, run the job-hunt-onboarding skill first.

Bring only fresh, relevant, still-open roles the user has not seen, each with the CV version to send.

## Steps
1. Read `job-search/profile.md` (tracks, hard filters, CV map) and the tracker (job-tracker skill) to know what was already sent or applied to.
2. Search the sources in `references/sources.md` that fit the user's tracks. Use web search and, when a browser is connected and the user is logged in, the boards' own search pages. Run several searches per track (title variants in Hebrew and English, synonyms, city names in the radius).
3. Open each candidate posting. Keep it only if all of these hold:
   - Posted or refreshed recently (prefer the last 7 days) and still open.
   - Matches a track and every hard filter (location radius, full-time, salary if stated, not temp, not part-time, not confidential "חסוי", not VIP/customers-only, not an industry the user excluded).
   - Not already in the tracker (dedupe by link and by company + title).
4. For each kept job record: company, title, city, source, link, track, CV version (from the CV map, with language matching the posting's language), one line on why it fits, and any flag (commute, salary unknown, agency posting).
5. Rank by fit, then by freshness. Put the user's priority tracks first.
6. Deliver a clickable checklist (an HTML page or artifact with links and checkboxes, grouped by track) plus a short Hebrew summary in chat. State the CV version for every role.
7. After the user applies, log the applications to the tracker with the CV version used.

## Applying on the user's behalf
- Apply automatically only if the user explicitly asks, the site allows it without bot checks, and the user approves the batch. Pace slowly.
- If the site shows any bot protection, CAPTCHA or blocking, stop at once. Do not retry with other methods. Give the user the list to apply manually.
- Never fill passwords. Ask the user to log in.

## Quality bar
- Fewer, real roles beat many stale ones. Say plainly when a source returned nothing new.
- Never bring a link the user cannot apply to.

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
