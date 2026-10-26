# Bug 4: Player Voting Toggle Display Problem

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/4/ |
| Old tracker ID | 1936688 |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 3 |
| Labels | — |
| Reported by | stephen001 |
| Assigned to | hobnob13 |
| Created | 2008-04-07 13:01:20 UTC |
| Last modified | 2008-05-18 06:01:59 UTC |

## Description

Not a major one, but it is a little misleading. Report from Animay:

\---------------------------------------------------------
In the show panel, toggling player voting on/off produces odd messages.

Example:

Player mode voting toggled to On.
Player mode voting toggled to On.
Player mode voting toggled to On.

It also has been locked on "off" before for me. I think it does change the ability to vote modes, but it doesn't display right on the output window.
\---------------------------------------------------------

## Comments (5)

### stephen001 · 2008-04-07 13:01:43 UTC · field change

- **milestone**:  --> Pre-release

### hobnob13 · 2008-04-08 15:43:19 UTC

Logged In: YES 
user\_id=2047692
Originator: NO

Should be fixed as of revision 5.

### stephen001 · 2008-04-08 18:23:42 UTC · field change

- **assigned_to**: nobody --> hobnob13
- **status**: open --> closed-fixed

### stephen001 · 2008-05-18 06:01:32 UTC · field change

- **status**: closed-fixed --> wont-fix-fixed

### stephen001 · 2008-05-18 06:01:59 UTC · field change

- **status**: wont-fix-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r5 | Fixing bug #1936688, display (and logging) when player mode voting toggled was incorrect. | `f5254ee9384f` /trunk |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r5 | comment by hobnob13, 2008-04-08 15:43:19 | Should be fixed as of revision 5. | `f5254ee9384f` /trunk |
