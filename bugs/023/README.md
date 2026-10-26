# Bug 23: AI does not lose HP if it drops below 0

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/23/ |
| Old tracker ID | 1987483 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 1 |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | shadowlord13 |
| Created | 2008-06-07 16:01:09 UTC |
| Last modified | 2008-06-17 21:46:28 UTC |

## Description

The AI does not lose HP over time like it should if its HP drops below 0. It also dies too slowly from power loss - it can take 20 minutes \*after\* its APC stops supplying power before it dies\! \(If you only cut power cables leading to its room, it can take even longer since the APC battery will last quite a while, especially if the AI turns off lights and environment\)

## Comments (3)

### shadowlord13 · 2008-06-07 16:15:30 UTC

Logged In: YES 
user\_id=365542
Originator: YES

Made a math error in the time there. 

More precisely:
It's taking 1 damage every 50 ticks \(instead of every tick\), which means:
50\*100 = 5000 ticks to hit 0 HP, so 500 seconds or 8 1/3 minutes
Then another 8 1/3 minutes to hit -100.

So it's actually about 16 minutes, rather than 20.

I've fixed the AI-not-losing-HP-over-time in revision 48. As a result of that, it dies in about 10 minutes instead of 16 \(since it'll start taking damage every tick \(If that's how often Life is called\) once it drops below 0 HP\).

### shadowlord13 · 2008-06-07 16:15:30 UTC · field change

- **assigned_to**: nobody --> shadowlord13
- **status**: open --> pending-fixed

### stephen001 · 2008-06-17 21:46:28 UTC · field change

- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r48 | Fixes for bugs 1987067 and 1987483. | `757dd2a49cbc` /branches/1.0-rc-1 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r48 | comment by shadowlord13, 2008-06-07 16:15:30 | …fixed the AI-not-losing-HP-over-time in revision 48. As a result of that, it dies in about… | `757dd2a49cbc` /branches/1.0-rc-1 |
