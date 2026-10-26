# Bug 1: Sandbox - Deleting Metal Causes DS Crash

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/1/ |
| Old tracker ID | — |
| Status | closed-rejected |
| Milestone | Pre-release |
| Priority | 9 |
| Labels | Sandbox Mode |
| Reported by | stephen001 |
| Assigned to | — |
| Created | 2008-04-07 12:50:45 UTC |
| Last modified | 2008-05-18 06:01:59 UTC |

## Description

I've marked this as highest priority, simply on the grounds it seems to crash DreamSeeker / DreamDaemon servers entirely, presumably producing a core dump too.

The original bug report from Animay is as follows:

\---------------------------------------------------------\
Spawned metal from sandbox panel, when deleted \(tested using Hobnob's debug verb "delete", the metal was in my right hand\) crashed my local host server, with windows debugger coming up, actually.\
\---------------------------------------------------------

Sandbox is a rather flaky mode, however it is reasonably popular, so temporarily removing it seems not to be a good idea. For more information on this bug, contact Animay \(his email should be available via SF\).

## Comments (7)

### crushu · 2008-04-07 21:10:53 UTC

*Old tracker: logged in: yes · user ID 1947276 · originator: no*

Without even looking at the delete verb code, I'm betting it's because the metal is equipped to your hand. I know when looking at code for other objects which can run out, u\_equip\(\) is called on them before del\(\) is.

Check for whether the delete\(\) verb is unequipping before deleting.

### crushu · 2008-04-08 02:56:24 UTC

*Old tracker: logged in: yes · user ID 1947276 · originator: no*

Hm. Looked at the delete\(\) verb \(and there's a delete proc as well, both are category "debug", which is Odd.\) Neither check for if it's equipped. I presume that's because it assumes that you're deleting an object Not on Your Person.

Option 1: Call user.u\_equip before deleting an object. You'd need a check to see whether it's actually equipped I think?

Option 2: Don't delete stuff on yourself. Dummy. :P

### hobnob13 · 2008-04-08 07:58:39 UTC

*Old tracker: logged in: yes · user ID 2047692 · originator: no*

I haven't been able to reproduce the bug, following the steps listed \(spawn metal in sandbox, place in right hand, delete\). It may be a matter of timing/lag - perhaps the metal got deleted halfway through some pending action, causing DS to crash.

Explanation of the two "delete"s - the "delete" verb is a debug verb defined in \_debug.dm, which should never be included in live versions anyway \(everything in that dm file is just for local testing\). The "Delete" proc/pseudoverb in datumvars.dm is a logged version that's granted to level 5 admins.

### stephen001 · 2008-04-08 13:08:54 UTC · field change

- **status**: open --> closed-rejected

### stephen001 · 2008-04-08 13:08:54 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

Seems we've had a number of people fail to re-create the bug, Twerty, SpeyMan, Hobnob, CrushU and Animay again.

### stephen001 · 2008-05-18 06:01:32 UTC · field change

- **status**: closed-rejected --> wont-fix-rejected

### stephen001 · 2008-05-18 06:01:59 UTC · field change

- **status**: wont-fix-rejected --> closed-rejected

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
