# Bug 46: CTF Mode Crashes Server

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/46/ |
| Old tracker ID | 2003004 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 2 |
| Priority | 7 |
| Labels | — |
| Reported by | zjm7891 |
| Assigned to | — |
| Created | 2008-06-26 08:36:37 UTC |
| Last modified | 2008-06-28 08:14:45 UTC |

## Description

runtime error: Cannot modify null.start.
proc name: New \(/obj/ctf\_assist/New\)
usr: null
src: the ctf assist \(/obj/ctf\_assist\)
call stack:
the ctf assist \(/obj/ctf\_assist\): New\(\)
show ctf\(\)
Capture the Flag Mode activated\!
The game start has been frozen to accomodate\!

This happens when you start CTF after someone has readied.
The result: Crash.

## Comments (2)

### zjm7891 · 2008-06-28 08:14:45 UTC · field change

- **status**: open --> closed-fixed

### zjm7891 · 2008-06-28 08:14:45 UTC

Logged In: YES 
user\_id=2047617
Originator: YES

Fixed in Revision 88 due to Animay's bugfix

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r87 | Applied Animay's bugfix to fix bug #2003004 | `f5e00da5c6e7` /branches/1.0-rc-2 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r88 | comment by zjm7891, 2008-06-28 08:14:45 | Fixed in Revision 88 due to Animay's bugfix | `ed78c8634688` /branches/1.0-rc-2 |
