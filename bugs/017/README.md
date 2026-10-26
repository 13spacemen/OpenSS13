# Bug 17: Inventory Window will not close on HTML unsafe names

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/17/ |
| Old tracker ID | 1986988 |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 5 |
| Labels | — |
| Reported by | stephen001 |
| Assigned to | stephen001 |
| Created | 2008-06-07 00:23:47 UTC |
| Last modified | 2008-06-17 21:46:29 UTC |

## Description

http://forums.ss13.net/index.php/topic,8489.0.html

Originally submitted by Darkman1920.

Click and drag a person with a \# in their name onto your character. A HTML window will open. Attempt to close the window by clicking on the 'Close Window' link, it will not close.

The problem lies in mob.dm, in the show\_inv proc responsible for showing the window does not html\_encode the name of the person who's inventory it is displaying, hence the link chokes on unsafe characters.

## Comments (8)

### stephen001 · 2008-06-07 00:27:09 UTC

_(empty)_

Attachment: [inventory-window-name.patch](attachments/inventory-window-name.patch) (5,043 bytes)

### stephen001 · 2008-06-07 00:27:10 UTC · field change

- **status**: open --> closed-fixed

### stephen001 · 2008-06-07 00:27:10 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

Fixed as of revision 38. Added html\_encode to src.name where relevant, making the name HTML safe.\
File Added: inventory-window-name.patch

### stephen001 · 2008-06-07 00:45:28 UTC · field change

- **status**: closed-fixed --> pending-fixed

### stephen001 · 2008-06-08 21:36:11 UTC · field change

- **status**: pending-fixed --> open-fixed

### stephen001 · 2008-06-08 21:36:11 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

Made a change for 1.0 RC 1 revision 51 and trunk revision 52. We should've been using url\_encode.

### stephen001 · 2008-06-08 22:11:43 UTC · field change

- **status**: open-fixed --> pending-fixed

### stephen001 · 2008-06-17 21:46:29 UTC · field change

- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r38 | Fixed Bug #1986988. | `51bcf70f4ac2` /trunk |
| r51 | Made a change for #1986988. It passed the test-case, but just | `d7860fa4730d` /branches/1.0-rc-1 |
| r52 | Fix for #1986988. Should be using url_encode. | `1a35995cb996` /trunk |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r38 | comment by stephen001, 2008-06-07 00:27:10 | Fixed as of revision 38. Added html\_encode to src.name where r… | `51bcf70f4ac2` /trunk |
| r51 | comment by stephen001, 2008-06-08 21:36:11 | Made a change for 1.0 RC 1 revision 51 and trunk revision 52. We should've bee… | `d7860fa4730d` /branches/1.0-rc-1 |
| r52 | comment by stephen001, 2008-06-08 21:36:11 | …ange for 1.0 RC 1 revision 51 and trunk revision 52. We should've been using url\_encode. | `1a35995cb996` /trunk |
