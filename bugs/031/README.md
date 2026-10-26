# Bug 31: Miscellaneous fixes

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/31/ |
| Old tracker ID | — |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 1 |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | shadowlord13 |
| Created | 2008-06-16 02:28:32 UTC |
| Last modified | 2008-06-17 21:46:27 UTC |

## Description

\(items.dm\)\
The game kit window didn't update for the AI.

Brutepack and ointment amount were being reduced when used on non-humans, even though they didn't work on non-humans \(they also recalculated their health\)

Brutepack and ointment didn't give any indication that they weren't doing anything when used on non-humans. Now they show a message.

## Comments (3)

### shadowlord13 · 2008-06-16 02:30:50 UTC · field change

- **milestone**:  --> Version 1.0 RC 1
- **assigned_to**: nobody --> shadowlord13
- **status**: open --> pending-fixed

### shadowlord13 · 2008-06-16 02:30:50 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: yes*

All fixed in revision 53. \(All were in items.dm\)

I had also made a number of other changes to items.dm to fix the various ways you could abuse the AI, and to add an updateSelfDialog function in anticipation of a bugfix to the 'weapons' with dialogs \(timers, infra\_sensors, etc\).

### stephen001 · 2008-06-17 21:46:27 UTC · field change

- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r53 | comment by shadowlord13, 2008-06-16 02:30:50 | All fixed in revision 53. \(All were in items.dm\) | `a91d1bcf1c92` /branches/1.0-rc-1 |
