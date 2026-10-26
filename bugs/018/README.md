# Bug 18: Ranks allowed to do actions differ from ones shown them

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/18/ |
| Old tracker ID | 1987041 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 1 |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | shadowlord13 |
| Created | 2008-06-07 02:49:05 UTC |
| Last modified | 2008-06-17 21:46:29 UTC |

## Description

Basically, the obj/admins/Topic proc is checking to see if the name of the user's rank is in one of a set of names, and using that to decide whether to allow them to do the action. 

Everywhere else uses rank numbers, and the rank strings there probably don't match the rank strings which translated into the rank numbers.

## Comments (5)

### shadowlord13 · 2008-06-07 02:51:13 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: yes*

Should be fixed in revision 43 \(should probably be tested just in case, even though it was a rather small change\).

### shadowlord13 · 2008-06-07 02:51:13 UTC · field change

- **assigned_to**: nobody --> shadowlord13
- **status**: open --> pending-fixed

### stephen001 · 2008-06-09 00:17:09 UTC

_(empty)_

Attachment: [admin-positions.patch](attachments/admin-positions.patch) (14,605 bytes)

### stephen001 · 2008-06-09 00:17:11 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

Attached patch for 1.0 RC 1. I'll patch the trunk.\
File Added: admin-positions.patch

### stephen001 · 2008-06-17 21:46:29 UTC · field change

- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r43 | Fixed bug #1987041 - ranks allowed to do actions differ from ones shown them | `89f4a160d1a5` /branches/1.0-rc-1 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r43 | comment by shadowlord13, 2008-06-07 02:51:13 | Should be fixed in revision 43 \(should probably be tested just in cas… | `89f4a160d1a5` /branches/1.0-rc-1 |
