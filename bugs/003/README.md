# Bug 3: Moving past density using Closets.

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/3/ |
| Old tracker ID | 1936685 |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 5 |
| Labels | — |
| Reported by | stephen001 |
| Assigned to | stephen001 |
| Created | 2008-04-07 12:58:34 UTC |
| Last modified | 2008-05-18 06:01:59 UTC |

## Description

This is a pretty long-standing bug. It was supposed to be fixed before the source release, but we seem to have regressed. Once again, a report by Animay:

\---------------------------------------------------------\
You go into a closet, before it closes click your character and drag it to a nearby closet, the closet you're in closes, then release the mouse button and you'll teleport.

You can do this into walls, get out of locked lockers, and other things.\
\---------------------------------------------------------

Considering how long we've had this one, it'd be nice to get it sorted out properly.

## Comments (7)

### shadowlord13 · 2008-04-07 20:56:51 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: no*

So far, I've only been able to reproduce this on closets which are only one tile away from the one I'm standing in, but that does allow teleporting through secure blue doors. However, the fact that you need an accomplice on the inside to put a closet behind the door kind of limits the possibilities for abuse.

Fixing this, however, appears quite simple: When someone is in a closet, their loc is that closet, rather than a turf.

So, add to /obj/closet/MouseDrop\_T\(atom/movable/O as mob|obj, mob/user as mob\):\
if \(user.loc==null\) // just in case someone manages to get a closet into the blue light dimension, as unlikely as that seems\
return\
if \(\!istype\(user.loc, /turf\)\) // are you in a container/closet/pod/etc?\
return

In my copy, I put it after the\
if \(\(\!\( istype\(O, /atom/movable\) \) || O.anchored || get\_dist\(user, src\) &gt; 1 || get\_dist\(user, O\) &gt; 1 || user.contents.Find\(src\)\)\)\
return

### stephen001 · 2008-04-07 21:12:56 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

Accepted task. I'll review the patch suggested by shadowlord13.

### stephen001 · 2008-04-07 21:12:56 UTC · field change

- **assigned_to**: nobody --> stephen001

### stephen001 · 2008-04-07 22:11:55 UTC · field change

- **status**: open --> closed-fixed

### stephen001 · 2008-04-07 22:11:55 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

Seems the patch did the trick, kudos to shadowlord13.

### stephen001 · 2008-05-18 06:01:32 UTC · field change

- **status**: closed-fixed --> wont-fix-fixed

### stephen001 · 2008-05-18 06:01:59 UTC · field change

- **status**: wont-fix-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r3 | Fixed bug #1936685, using patch provided by shadowlord13. | `c3245b85dbb6` /trunk |

## SVN revisions mentioned in this ticket

None.
