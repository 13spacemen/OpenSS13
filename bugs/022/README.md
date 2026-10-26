# Bug 22: AI can't find its APC if main breaker is flipped off

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/22/ |
| Old tracker ID | 1987067 |
| Status | closed-fixed |
| Milestone | — |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | shadowlord13 |
| Created | 2008-06-07 03:33:37 UTC |
| Last modified | 2008-06-17 21:46:29 UTC |

## Description

If the AI's APC's main breaker is flipped off, it fails to find the APC when it tries to hack it.

## Comments (4)

### shadowlord13 · 2008-06-07 03:33:57 UTC · field change

- **assigned_to**: nobody --> shadowlord13

### shadowlord13 · 2008-06-07 16:15:51 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: yes*

Fixed in revision 48.

### shadowlord13 · 2008-06-07 16:15:51 UTC · field change

- **status**: open --> pending-fixed

### stephen001 · 2008-06-17 21:46:29 UTC · field change

- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r48 | Fixes for bugs 1987067 and 1987483. | `757dd2a49cbc` /branches/1.0-rc-1 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r48 | comment by shadowlord13, 2008-06-07 16:15:51 | Fixed in revision 48. | `757dd2a49cbc` /branches/1.0-rc-1 |
