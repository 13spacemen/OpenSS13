# Bug 9: Bug Merger [1937196] [1939088]

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/9/ |
| Old tracker ID | 1952091 |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 5 |
| Labels | — |
| Reported by | rockdtben |
| Assigned to | stephen001 |
| Created | 2008-04-26 05:27:41 UTC |
| Last modified | 2008-04-30 13:58:00 UTC |

## Description

It seems \[ 1937196 \] Prison Station + Interior Doors | and | \[ 1939088 \] Moving into machines through windows | are due to the same bug. This bug is related to the checkexit proc and the reason the user is able to do these actions is because windows and blue doors are not considered dense objects. 

These two bugs are essentially the same.

The usage of all tools through a window/bluedoor is possible and moving into an object through a window is also possible. 

I read the attackby proc for canisters and all the actions in that proc are not accesible through window/bluedoors so possibly theres a fix located somewhere related to canisters.

## Comments (7)

### stephen001 · 2008-04-26 06:37:28 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

Seems I was a little too downstream. Before the CheckExit calls, we do \(src.flags & 512\), meaning it's a window.

Will look into it further.

### shadowlord13 · 2008-04-26 14:42:16 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: no*

I was going to reply here, but can't \(due to not being in the dev team, presumably\): http://forums.ss13.net/index.php/topic,8463.0.html

I just added some debug messages to see what's going on. The problem is simple:

in /atom/DoubleClick, find this line: if \(src.loc.Enter\(D, src\)\)

That is where the problem is. If you are targetting, say, a closet, its loc will be the turf it is on. But if you are targetting a \*turf\*, then its loc will be the area that it is in. So, when you target the ground, this check returns true because \*it isn't checking the turf's Enter at all\*.

Simple fix:\
1\. Above if \(\(\(t5 || \(W && \(W.flags & 16\)\)\) && \!\( istype\(src, /obj/screen\) \)\)\) add:\
var/turf/turfTile = null\
if \(istype\(src, /turf\)\)\
turfTile = src\
else\
turfTile = src.loc

2\. Change all references to src.loc in the function after that point to turfTile instead.

### stephen001 · 2008-04-28 02:04:42 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

Implemented the fix suggested by shadowlord13. Unfortunately I can't test it, so could someone test revision 17, then report the results here?

### stephen001 · 2008-04-28 02:04:43 UTC · field change

- **status**: open --> pending-fixed

### stephen001 · 2008-04-28 02:05:01 UTC · field change

- **milestone**:  --> Pre-release

### shadowlord13 · 2008-04-28 02:47:37 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: no*

You appear to have missed one line: 	if \(src.loc.Enter\(D, src\)\)

That should be: 	if \(turfLoc.Enter\(D, src\)\)

### rockdtben · 2008-04-30 13:58:00 UTC · field change

- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r17 | Added suggested fix for Bug #1952091. Needs testing. | `31e25adfc51f` /trunk |
| r18 | Continue fixing bug #1952091 as per shadowlord13. | `66ea0045fede` /trunk |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r17 | comment by stephen001, 2008-04-28 02:04:42 | …I can't test it, so could someone test revision 17, then report the results here? | `31e25adfc51f` /trunk |
