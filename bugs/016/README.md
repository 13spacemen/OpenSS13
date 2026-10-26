# Bug 16: Many verbs don't check stat

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/16/ |
| Old tracker ID | 1980820 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 2 |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | zjm7891 |
| Created | 2008-05-31 17:39:11 UTC |
| Last modified | 2008-07-08 15:25:23 UTC |

## Description

Many or most verbs don't check the user's stat, so they still work even if the user is unconscious or dead.

An easy to demonstrate example is to get on the prison shuttle without any air supply, go to the south door, open it, and die on the door's tile. Once you're dead \(and can see again due to being dead\), right click the door and hit close. It will close \(It can be opened too\).

The best thing to do would be to just check all verbs. Some already check stat \(Pods' board verb checks it, for instance\), but many don't.

## Comments (9)

### stephen001 · 2008-06-07 00:28:04 UTC · field change

- **milestone**:  --> 824199

### stephen001 · 2008-06-21 23:42:05 UTC · field change

- **status**: open --> closed-postponed

### stephen001 · 2008-06-21 23:42:05 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

This should be remedied by a refactor.

### shadowlord13 · 2008-06-21 23:48:04 UTC · field change

- **status**: closed-postponed --> open-postponed

### shadowlord13 · 2008-06-21 23:48:04 UTC

Logged In: YES 
user\_id=365542
Originator: YES

This is already fixed in the trunk for most verbs, since they use canReach, and it checks stat. The rest of the verbs should probably have a stat check added to them still.

### zjm7891 · 2008-06-25 11:36:11 UTC · field change

- **milestone**: 824199 --> Version 1.0 RC 2

### zjm7891 · 2008-07-08 15:25:12 UTC · field change

- **assigned_to**: nobody --> zjm7891
- **status**: open-postponed --> open-fixed

### zjm7891 · 2008-07-08 15:25:12 UTC

Logged In: YES 
user\_id=2047617
Originator: NO

Fixed in Rev 95 as a cheap fix.  Trunk has the proper fix.

### zjm7891 · 2008-07-08 15:25:23 UTC · field change

- **status**: open-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r95 | Fixed bug #1980820 All verbs should now check status and restricted | `9a47ad3950e7` /branches/1.0-rc-2 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r95 | comment by zjm7891, 2008-07-08 15:25:12 | Fixed in Rev 95 as a cheap fix.  Trunk has the proper f… | `9a47ad3950e7` /branches/1.0-rc-2 |
