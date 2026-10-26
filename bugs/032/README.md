# Bug 32: Timer, infra_sensor, other weapons with auto-update dialogs

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/32/ |
| Old tracker ID | — |
| Status | open |
| Milestone | Trunk |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | — |
| Created | 2008-06-16 03:07:34 UTC |
| Last modified | 2008-07-10 04:32:06 UTC |

## Description

There's weirdness in the timers, infra\_sensors, and other things like them \(weapons with dialogs which auto-update\).

First, at least in timers, the timer dialog will pop up any time you walk near a ticking timer which is on the floor.

Second, you can close the dialog and it will just pop back up. There's no close link in the dialog, so no way to make it stop popping up. Dropping the timer doesn't help. Moving 2 squares away does make it stop updating \(and then you can close the dialog\), but if you then get back within 1 square while it's still ticking, the dialog will start coming up again.

I've already added a function called /obj/proc/updateSelfDialog\(atom/origin\), for the 'weapons' with dialogs \(timer, infra\_sensor, etc\), to unify their identical code in anticipation of future bugfixes to it for this bug or other bugs.

src.updateSelfDialog is checking for nearby players and calling attack\_self on them.

timer, each tick that it updates \(which is only when it's counting down\), is doing this:
if \(\!\( src.master \)\)
if \(istype\(src.loc, /mob\)\)
attack\_self\(src.loc\)
else
src.updateSelfDialog\(src\)
else
if \(istype\(src.master.loc, /mob\)\)
src.attack\_self\(src.master.loc\)
else
src.updateSelfDialog\(src.master\)

Translation:
If it is not in a contraption, and is held by a mob, the dialog re-opens for that mob.
If it is not held by a mob, updateSelfDialog is centered on the device.
If it is in a contraption, same thing except we check the contraption instead of the device.

Bugs in this \(in timer specifically - The others may or may not have the same ones, so they'll need to be looked at\):
It should only update if the window is already open. We should be able to close it without it coming back up. Add a close link. At least some of these already set machine to the user. \(I only checked two, which did, and didn't check the rest\)
They try to close the dialog if attack\_self is called if you get more than 1 tile away, but it never would be called then because the range for finding people to update the dialog on is only 1 tile away.
Even if you walked away, when you walked back the dialog would come up and resume updating.

## Comments (2)

### zjm7891 · 2008-06-25 11:36:11 UTC · field change

- **milestone**: 848631 --> 854524

### zjm7891 · 2008-07-10 04:32:06 UTC · field change

- **milestone**: 854524 --> Trunk

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
