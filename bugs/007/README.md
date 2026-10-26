# Bug 7: Moving into machines through windows

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/7/ |
| Old tracker ID | 1939088 |
| Status | closed-remind |
| Milestone | Pre-release |
| Priority | 4 |
| Labels | — |
| Reported by | murrawhip |
| Assigned to | stephen001 |
| Created | 2008-04-10 03:10:03 UTC |
| Last modified | 2008-07-06 02:20:21 UTC |

## Description

When on the opposite side of a window, a character can move through it, into a DNA Scanner/Implanter, DNA Physical Reconstruction Accelerator, sleeper or cryo cell. This can also be done while a character is inside a closet.

## Comments (25)

### murrawhip · 2008-04-10 03:10:48 UTC · field change

- **summary**: Moving into DNA machines through windows --> Moving into machines through windows

### murrawhip · 2008-04-10 03:12:32 UTC · field change

- **milestone**:  --> Pre-release

### rockdtben · 2008-04-16 13:20:28 UTC

Logged In: YES 
user\_id=2058192
Originator: NO

This is related to mostly all the machines in med/dna areas. So ill leave this one to you Zjm

### rockdtben · 2008-04-16 13:20:28 UTC · field change

- **assigned_to**: nobody --> zjm7891

### rockdtben · 2008-04-26 05:13:17 UTC · field change

- **status**: open --> open-duplicate

### rockdtben · 2008-04-26 05:14:05 UTC · field change

- **status**: open-duplicate --> closed-duplicate

### rockdtben · 2008-04-26 05:29:26 UTC

Logged In: YES 
user\_id=2058192
Originator: NO

BUG HAS BEEN MOVED TO \[ 1952091 \]

### rockdtben · 2008-04-30 13:58:20 UTC · field change

- **status**: closed-duplicate --> open-remind

### rockdtben · 2008-04-30 14:00:22 UTC

Logged In: YES 
user\_id=2058192
Originator: NO

Alright its now its own bug again. Reffler - "I've added the extra fix as mentioned by sl13 on the bugtracker \(now as rev 18\), and tested it. Everything seems to work \(you can no longer crowbar through windows\), except that you can still move into a DNA machine from the other side of the window. A closer look shows that the verb "move inside" doesn't do any kind of check for obstructions, so it's not surprising this doesn't fix it.



TODO: Anything you interactive with via a verb should have additional checks to stop this. Alternately, all verbs \(except trivial ones like examine\) should be migrated to click-type interactions, if possible."

### rockdtben · 2008-04-30 14:00:35 UTC · field change

- **priority**: 2 --> 4

### anichowy · 2008-05-01 19:21:10 UTC

Logged In: YES 
user\_id=2056389
Originator: NO

Windows are extremely buggy, I wouldn't be surprised to see more bug reports involving windows.

### shadowlord13 · 2008-05-25 05:48:31 UTC

Logged In: YES 
user\_id=365542
Originator: NO

You can also escape into shuttlepods, by the way, which brings us to one way to exploit this: If welded inside a locker, and all welders have been stashed somewhere inaccessible \(say, an ID-locked locker\), an associate can still free you by simply tearing up floor tiles and driving a shuttlepod up to your locker. You then just use the pod's board verb, and poof, you're in the pod instead of the closet.

This is only semi-related, since it's not a verb, but you can also drag a locker onto a morgue tray \*while the locker is closed and you're inside it\*.

### rockdtben · 2008-06-05 02:53:39 UTC · field change

- **assigned_to**: zjm7891 --> stephen001

### stephen001 · 2008-06-06 02:56:51 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

You're going to get the problem with both move\_inside and attackby \(the way of forcibly putting someone in\). What we really need is some kind of utility proc that properly works out if you can 'touch' the given atom. Presumably some code from DblClick could be broken up to serve this purpose, cleaning up DblClick a bit too.

### stephen001 · 2008-06-21 01:00:25 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

Attached are patches for RC 1 and the trunk, to fix this for the DNA Scanner and DNA Physical Reconstruction Accelerator. Fortunately shadowlord13's funny commit of canReach into RC1 makes this easy to fix in RC 1.
File Added: dna-scanner-restruct-canreach-rc-1.patch

### stephen001 · 2008-06-21 01:00:25 UTC

RC 1 patchfile.

Attachment: [dna-scanner-restruct-canreach-rc-1.patch](attachments/dna-scanner-restruct-canreach-rc-1.patch) (4,692 bytes)

### stephen001 · 2008-06-21 01:01:59 UTC

Trunk patchfile.

Attachment: [dna-scanner-restruct-canreach-trunk.patch](attachments/dna-scanner-restruct-canreach-trunk.patch) (2,897 bytes)

### stephen001 · 2008-06-21 01:01:59 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

Here's the trunk patch, see previous comment. Both have been applied, bringig us to revision 64.
File Added: dna-scanner-restruct-canreach-trunk.patch

### stephen001 · 2008-06-21 02:02:31 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

Adding patchfile for RC 1, for cryocells.
File Added: cryocell-canreach-rc1.patch

### stephen001 · 2008-06-21 02:02:31 UTC

Patchfile for RC 1, for cryocells.

Attachment: [cryocell-canreach-rc1.patch](attachments/cryocell-canreach-rc1.patch) (1,298 bytes)

### stephen001 · 2008-06-21 02:03:02 UTC

Patchfile for trunk, for cryocells.

Attachment: [cryocell-canreach-trunk.patch](attachments/cryocell-canreach-trunk.patch) (712 bytes)

### stephen001 · 2008-06-21 02:03:02 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

Adding patchfile for trunk, for cryocells.
File Added: cryocell-canreach-trunk.patch

### stephen001 · 2008-06-21 22:13:00 UTC · field change

- **status**: open-remind --> pending-remind

### sf-robot · 2008-07-06 02:20:21 UTC

Logged In: YES 
user\_id=1312539
Originator: NO

This Tracker item was closed automatically by the system. It was
previously set to a Pending status, and the original submitter
did not respond within 14 days \(the time period specified by
the administrator of this Tracker\).

### sf-robot · 2008-07-06 02:20:21 UTC · field change

- **status**: pending-remind --> closed-remind

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r64 | Applied canReach to DNA Scanner and DNA DNA Physical Reconstruction Accelerator, for #1939088. | `838c86235238` /branches/1.0-rc-1, `47f8dae09177` /trunk |
| r67 | Added canReach to Cryocells, as per #1939088. | `c400b6b419e9` /branches/1.0-rc-1, `41057541f6dc` /trunk |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r18 | comment by rockdtben, 2008-04-30 14:00:22 | …oned by sl13 on the bugtracker \(now as rev 18\), and tested it. Everything seems to w… | `66ea0045fede` /trunk |
| r64 | comment by stephen001, 2008-06-21 01:01:59 | …. Both have been applied, bringig us to revision 64. | `838c86235238` /branches/1.0-rc-1, `47f8dae09177` /trunk |
