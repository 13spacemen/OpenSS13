# Bug 10: Double shuttle speed, game end, restart

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/10/ |
| Old tracker ID | 1952749 |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | murrawhip |
| Created | 2008-04-27 14:54:41 UTC |
| Last modified | 2008-06-07 00:28:04 UTC |

## Description

When the shuttle arrives, the departure time counts down at double speed, and when it leaves, the game end messages appear twice. Then the game seems to somehow attempt to restart twice, which can cause exceptions.

The cause was that /datum/control/gameticker/proc/timeup\(\), which is called by extend\_process, would spawn\(0\) call extend\_process and then return, leaving two copies of extend\_process running.

To fix it in my copy of the source, I simply commented out the relevant block in timeup\(\):\
src.timeleft = 1800\
src.shuttle\_location = 1\
/\*switch\(src.mode\)\
if\("meteor"\)\
spawn\( 0 \)\
meteor\_process\(\)\
return\
else\
spawn\( 0 \)\
extend\_process\(\)\
return\
\*/

There are other alternative fixes, though, such as stopping the initial extend\_process after it calls timeup\(\).

## Comments (7)

### rockdtben · 2008-04-30 14:02:06 UTC · field change

- **assigned_to**: nobody --> hobnob13

### rockdtben · 2008-04-30 14:02:19 UTC · field change

- **assigned_to**: hobnob13 --> stephen001

### stephen001 · 2008-04-30 22:13:43 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

I have no means of testing this. Bit of a 3rd year project report going on, too.

### stephen001 · 2008-04-30 22:13:43 UTC · field change

- **assigned_to**: stephen001 --> murrawhip

### hobnob13 · 2008-05-02 15:48:31 UTC

*Old tracker: logged in: yes · user ID 2047692 · originator: no*

Fix as per sl13 implemented in rev 20. Seems to work just fine.

### rockdtben · 2008-05-02 18:49:41 UTC · field change

- **status**: open --> closed-fixed

### stephen001 · 2008-06-07 00:28:04 UTC · field change

- **milestone**:  --> Pre-release

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r20 | Fix bug #1952749 as per shadowlord13 | `78f34b16e5cd` /trunk |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r20 | comment by hobnob13, 2008-05-02 15:48:31 | Fix as per sl13 implemented in rev 20. Seems to work just fine. | `78f34b16e5cd` /trunk |
