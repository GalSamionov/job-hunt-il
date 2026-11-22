---
name: cv-versions
description: >
  This skill should be used when the user asks to "build CV versions", "תכין לי קורות חיים",
  "גרסה לכל מסלול", "תעדכן את קורות החיים", "קורות חיים בעמוד אחד", "קורות חיים באנגלית",
  "תעצב לי קורות חיים", or wants a CV tailored to a role family or to a specific posting.
  Also used when helping a friend or family member with their CV.
---

# CV versions

> If `job-search/profile.md` does not exist yet, run the job-hunt-onboarding skill first.

Produce one CV per track from `job-search/profile.md`, in Hebrew and/or English, one page each, as PDF (and DOCX on request).

## Workflow
1. Read the profile and every CV file the user provided. If CV variants disagree on numbers (team size, volumes, years), list the conflicts and ask which is correct before writing.
2. Show 2 or 3 design directions as rendered previews of the first page before writing all versions. Use `references/cv-template.html` as the base design; vary header and metric treatment.
3. Write content per track following `references/writing-rules.md`.
4. Render to PDF at A4. Check it is exactly one page. Look at the rendered page before delivering.
5. Name files clearly: `CV_<Name>_<Track>_<LANG>_<YYYY-MM-DD>.pdf`. Save under `job-search/cv/` and send them to the user.
6. Update the CV map in the profile (track to file name).

## Content principles (summary, full list in references)
- Lead with what this track's recruiter screens for. Same facts, different emphasis per track.
- Every bullet: verb (or Hebrew noun form) + what + result with a number when the user has one.
- Never repeat a metric that already appears in the top metric cards.
- Keep numbers identical across all versions.
- Hebrew CVs: nominal phrasing ("ניהול", "הקמה", "הובלה"), not first person ("ניהלתי"). Company names, job titles and tool names stay in English where that is how the market writes them.
- For a step-down role (e.g. a manager applying to a hands-on role), add one honest line in the profile explaining the choice, after confirming it with the user.

## Rendering
- With a shell: fill the HTML template, render with Playwright or headless Chrome to PDF (print background on). Heebo covers Hebrew and Latin.
- Without a shell: use the docx skill if available, keeping the same structure.

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
