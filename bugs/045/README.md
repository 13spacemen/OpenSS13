# Bug 45: Emergency Close

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/45/ |
| Old tracker ID | 2002397 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 2 |
| Priority | 3 |
| Labels | — |
| Reported by | zjm7891 |
| Assigned to | zjm7891 |
| Created | 2008-06-25 11:39:11 UTC |
| Last modified | 2008-06-28 08:31:27 UTC |

## Description

On the security pads, when you press emergency close, it only closed the outer door, ignoring the inner door completely \(unless you press the button again\).

## Comments (2)

### zjm7891 · 2008-06-28 08:31:27 UTC · field change

- **status**: open --> closed-fixed

### zjm7891 · 2008-06-28 08:31:27 UTC

Logged In: YES 
user\_id=2047617
Originator: YES

The Emergency close option had a problem where its code didn't mirror emergency open.  Fixed in Rev 89

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r89 | Fixed bug #2002397 | `334e1c78a43f` /branches/1.0-rc-2 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r89 | comment by zjm7891, 2008-06-28 08:31:27 | …didn't mirror emergency open.  Fixed in Rev 89 | `334e1c78a43f` /branches/1.0-rc-2 |
