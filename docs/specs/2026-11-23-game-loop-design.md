# Job Hunt: המשחק, לולאת המשחק

Decided with Gal on 23.11.2026 (grill session). The town stops being a menu over a tracker and becomes a game: a daily adventure inside a city that grows with real progress.

## Decisions

1. **Genre.** A daily adventure plus a city that is built over time. Not a skin over a tool.
2. **Day.** A real calendar day, weekends included. Every later visit on the same day opens with what changed since the previous visit ("rounds"). The summary and celebration come when the player goes to bed. A skipped day carries no penalty.
3. **City growth.** Houses and districts grow only from real milestones. Stars (the points bank) buy cosmetics only: decorations in the town and hats for the hero. Nothing that measures progress can be bought.
4. **Inside a house.** The agent presents one item at a time in a pixel dialog window, and each house has one mechanic of its own:
   - Sourcing: swipe a job card (right applies, left skips).
   - CV: match a CV version to each approved job.
   - Outreach: a letter per person, stamped to send.
   - Follow-up: ring the bell per person who is due, close out the cold ones.
   - Interviews: a question battle, where a better answer takes more of the question's strength.
   A list view stays available in every house for speed.
5. **Street.** Real events appear in the town as people and objects: a recruiter who replied waits by the outreach house, a mail carrier brings what Claude sent, a hot new job arrives as a letter, an interview appears as a notice on the board, a rejection as a grey envelope. At most two events stand in the street at a time, the most important first, plus one star; the next comes in when one is opened. A street event opens only when the hero walks to it.

   **Calm town (23.11, after review):** no dock, the town itself is the menu. An agent stands outside its house only when there is work for the player there, and the plates carry no counts. One arrow only, over the most important event or the next house. Street furniture is cut to one lamp and one bench.
6. **Rejections and silence.** They appear in a matter-of-fact tone and give stars as a closure. Points reward only what is in the player's control.
7. **Ending.** Marking an accepted offer plays an ending scene, then a journey summary and a share card. The town is kept as it is.
8. **Execution.** What is decided in the game, Claude carries out automatically. A job that clearly fits the rules is applied to by Claude on its own and appears as a "sent" event. A borderline job, or anything that needs the player's answer, waits in a house. How wide "clearly" is, the player sets during onboarding and on the plan board (`settings/main.auto_level`: `off`, `narrow`, `wide`).
9. **When it runs.** Decisions accumulate. Leaving a house, or pressing "שלח לClaude", fires one run of the player's scheduled task through the Claude Code Remote connector (`fire_trigger` with `settings/main.trigger_id`). Fixed runs morning, noon and evening are the fallback. Results come back as street events. Outside Claude (ChatGPT and others) it stays a day file and copied decisions.

## Data contract additions

- `applications.status` adds `rejected`, `offer`, `hired`. `applications.by` is `"claude"` when Claude applied without a decision in the game. `applications.date` is the day it was applied.
- `requests.status` adds `blocked`, with `reason` (for example a mandatory salary field). A blocked request is shown by its agent in the street and in the house.
- `settings/main` adds `auto_level` and `trigger_id`, both written by Claude during setup; the player can change `auto_level` in the game.
- Everything else (stars, owned cosmetics, seen events, rounds snapshot, ending) is kept on the player's device.

## Milestones (house tiers 1, 2, 3)

| House | Counts | Tiers |
|---|---|---|
| Sourcing | jobs applied to | 10, 40, 100 |
| CV | CV versions, CV checks | 2, 4, 6 |
| Outreach | people contacted | 10, 40, 100 |
| Follow-up | replies received | 3, 10, 25 |
| Interviews | interviews plus practice answers | 2, 8, 20 |

Tier 1 puts flower boxes by the door, tier 2 lights the windows and raises a flag, tier 3 adds a gold trim and a star on the name plate.
