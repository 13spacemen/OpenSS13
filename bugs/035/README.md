# Bug 35: DNA Add not succeesfully adding data.

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/35/ |
| Old tracker ID | 1999232 |
| Status | closed-duplicate |
| Milestone | Version 1.0 RC 1 |
| Priority | 5 |
| Labels | — |
| Reported by | stephen001 |
| Assigned to | stephen001 |
| Created | 2008-06-21 00:02:30 UTC |
| Last modified | 2008-07-05 02:20:17 UTC |

## Description

Originally submitted by Kurper.

Essentially, Data add does not add the contents of disk two onto the end of the contents of disk one. This was essentially a typo in the actual addition.

## Comments (7)

### stephen001 · 2008-06-21 00:06:22 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

Fixed in revision 63. Attached are patches for both trunk and RC 1, they should be good for anything back to revision 57.\
File Added: dna-add-typo-trunk.patch

### stephen001 · 2008-06-21 00:06:22 UTC

Patch for the trunk.

Attachment: [dna-add-typo-trunk.patch](attachments/dna-add-typo-trunk.patch) (513 bytes)

### stephen001 · 2008-06-21 00:06:42 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: yes*

File Added: dna-add-typo-rc-1.patch

### stephen001 · 2008-06-21 00:06:42 UTC

Patch for RC 1.

Attachment: [dna-add-typo-rc-1.patch](attachments/dna-add-typo-rc-1.patch) (549 bytes)

### stephen001 · 2008-06-21 00:07:03 UTC · field change

- **status**: open --> pending-duplicate

### sf-robot · 2008-07-05 02:20:17 UTC

*Old tracker: logged in: yes · user ID 1312539 · originator: no*

This Tracker item was closed automatically by the system. It was\
previously set to a Pending status, and the original submitter\
did not respond within 14 days \(the time period specified by\
the administrator of this Tracker\).

### sf-robot · 2008-07-05 02:20:17 UTC · field change

- **status**: pending-duplicate --> closed-duplicate

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r63 | Fixed #1999232, patches attached to the Bug. | `fd5399aecfe0` /branches/1.0-rc-1, `830c94694e01` /trunk |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r63 | comment by stephen001, 2008-06-21 00:06:22 | Fixed in revision 63. Attached are patches for both trunk an… | `fd5399aecfe0` /branches/1.0-rc-1, `830c94694e01` /trunk |
| r57 | comment by stephen001, 2008-06-21 00:06:22 | …hey should be good for anything back to revision 57. | `2324df01f3cc` /trunk |
