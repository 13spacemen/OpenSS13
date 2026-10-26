# Bug 48: APCs destory screwdrivers

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/48/ |
| Old tracker ID | 2013401 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 2 |
| Priority | 5 |
| Labels | — |
| Reported by | zjm7891 |
| Assigned to | zjm7891 |
| Created | 2008-07-08 11:42:08 UTC |
| Last modified | 2008-07-08 11:45:20 UTC |

## Description

If an APC doesn't have any power, when the user tries to add the powercell, attack\_by\(\) gets called after attack\_by\(obj\)

## Comments (2)

### zjm7891 · 2008-07-08 11:45:20 UTC · field change

- **status**: open --> closed-fixed

### zjm7891 · 2008-07-08 11:45:20 UTC

Logged In: YES 
user\_id=2047617
Originator: YES

Fixed in Rev 91.

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r91 | Fixed bug #2013401 and #2013405 | `7524a4d9c3cc` /branches/1.0-rc-2 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r91 | comment by zjm7891, 2008-07-08 11:45:20 | Fixed in Rev 91. | `7524a4d9c3cc` /branches/1.0-rc-2 |
