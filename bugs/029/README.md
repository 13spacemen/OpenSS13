# Bug 29: Camera not disconnecting viewers when cut

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/29/ |
| Old tracker ID | — |
| Status | closed |
| Milestone | Version 1.0 RC 1 |
| Priority | 4 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | shadowlord13 |
| Created | 2008-06-15 03:42:40 UTC |
| Last modified | 2008-07-06 02:20:20 UTC |

## Description

This is in camera.dm: When the camera is disconnected, it doesn't kick out viewers.

## Comments (5)

### shadowlord13 · 2008-06-15 03:44:32 UTC

Logged In: YES 
user\_id=365542
Originator: YES

I've put a fix on svn, but the fix needs to be tested \(needs two people - someone to watch through the camera and someone else to disconnect it with wirecutters\) before this gets marked fixed.

### shadowlord13 · 2008-06-15 03:44:33 UTC · field change

- **priority**: 5 --> 4
- **assigned_to**: nobody --> shadowlord13

### stephen001 · 2008-06-21 22:12:28 UTC · field change

- **status**: open --> pending

### sf-robot · 2008-07-06 02:20:20 UTC

Logged In: YES 
user\_id=1312539
Originator: NO

This Tracker item was closed automatically by the system. It was
previously set to a Pending status, and the original submitter
did not respond within 14 days \(the time period specified by
the administrator of this Tracker\).

### sf-robot · 2008-07-06 02:20:20 UTC · field change

- **status**: pending --> closed

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
