# Bug 13: Carrying or throwing lit welders does not ignite plasma

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/13/ |
| Old tracker ID | 1980809 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 2 |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | hobnob13 |
| Created | 2008-05-31 17:17:49 UTC |
| Last modified | 2008-06-27 23:05:01 UTC |

## Description

If you carry a lit welder into plasma, it does not ignite.

If you throw a lit welder into plasma, it also does not ignite.

## Comments (7)

### rockdtben · 2008-06-05 02:54:20 UTC · field change

- **assigned_to**: nobody --> hobnob13

### stephen001 · 2008-06-07 00:28:04 UTC · field change

- **milestone**:  --> 824199

### zjm7891 · 2008-06-25 11:36:11 UTC · field change

- **milestone**: 824199 --> Version 1.0 RC 2

### hobnob13 · 2008-06-25 17:07:39 UTC

Logged In: YES 
user\_id=2047692
Originator: NO

Fixed in revision 80 of RC2.

### hobnob13 · 2008-06-26 03:03:02 UTC

Logged In: YES 
user\_id=2047692
Originator: NO

Oops, make that fixed in revn 83, since I forgot to add the new code file.

### zjm7891 · 2008-06-27 23:05:01 UTC · field change

- **status**: open --> closed-fixed

### zjm7891 · 2008-06-27 23:05:01 UTC

Logged In: YES 
user\_id=2047617
Originator: NO

Tested and fixed\! Thanks Hobnob\!

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r80 | Fixed bug #1980809, lit weldingtools now ignite plasma. | `f421fd2dc7ee` /branches/1.0-rc-2, `feedfc9af83d` /trunk |
| r81 | This patch allows V80 to compile, However, HobNob will need to rerun his bugfix to #1980809 | `9761a83acc75` /branches/1.0-rc-2 |
| r83 | Updated with missing code file to fix bug #1980809. | `b8efabe42fc3` /branches/1.0-rc-2 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r80 | comment by hobnob13, 2008-06-25 17:07:39 | Fixed in revision 80 of RC2. | `f421fd2dc7ee` /branches/1.0-rc-2, `feedfc9af83d` /trunk |
