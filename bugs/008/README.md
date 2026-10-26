# Bug 8: leak to turf - Cannot execute null.get node dirs

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/8/ |
| Old tracker ID | — |
| Status | closed-later |
| Milestone | Pre-release |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | hobnob13 |
| Created | 2008-04-12 01:50:07 UTC |
| Last modified | 2008-06-19 02:20:04 UTC |

## Description

Had this show up in the console \(repeatedly spammed until Dream Daemon cut off exception messages\) during a Blob game.

runtime error: Cannot execute null.get node dirs\(\).
proc name: leak to turf \(/obj/machinery/pipeline/proc/leak\_to\_turf\)
source file: newpipe.dm,141
usr: null
src: the pipeline \#5 \(/obj/machinery/pipeline\)
call stack:
the pipeline \#5 \(/obj/machinery/pipeline\): leak to turf\(2\)
the pipeline \#5 \(/obj/machinery/pipeline\): process\(\)
/datum/control/cellular \(/datum/control/cellular\): process\(\)
: New\(\)

## Comments (7)

### hobnob13 · 2008-04-12 17:55:58 UTC

Logged In: YES 
user\_id=2047692
Originator: NO

Probably caused by deletion of an obj/machinery/pipes object \(by blob or by an explosion\). Currently pipelines don't handle this properly.

This bug should be fixed when proper handling of pipe construction/damage/destruction is implemented. I am working on
this at the moment.

### rockdtben · 2008-04-16 13:24:08 UTC · field change

- **assigned_to**: nobody --> hobnob13

### stephen001 · 2008-06-04 04:47:37 UTC

Logged In: YES 
user\_id=1640007
Originator: NO

This will be reviewed and hopefully sorted for version 2.

### stephen001 · 2008-06-04 04:47:38 UTC · field change

- **status**: open --> pending-later

### stephen001 · 2008-06-07 00:28:05 UTC · field change

- **milestone**:  --> Pre-release

### sf-robot · 2008-06-19 02:20:04 UTC · field change

- **status**: pending-later --> closed-later

### sf-robot · 2008-06-19 02:20:04 UTC

Logged In: YES 
user\_id=1312539
Originator: NO

This Tracker item was closed automatically by the system. It was
previously set to a Pending status, and the original submitter
did not respond within 14 days \(the time period specified by
the administrator of this Tracker\).

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
