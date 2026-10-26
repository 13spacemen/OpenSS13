# Bug 50: Exploit: double-pull fire alarm for open firedoors + alarm

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/50/ |
| Old tracker ID | — |
| Status | open |
| Milestone | — |
| Priority | 5 |
| Labels | — |
| Reported by | kurper |
| Assigned to | — |
| Created | 2008-07-18 20:22:28 UTC |
| Last modified | 2008-07-18 20:22:28 UTC |

## Description

how to reproduce: pull fire alarm. pull it again twice in quick succession. congratulations, the fire alarm is now going off but the fire doors are open.

feel free to steal our fix for it, see rev446 of svn.slurm.us/public/spacestation13/branches/kurper/unstable/

## Comments (1)

### nobody · 2008-07-24 18:20:48 UTC

Logged In: NO 

Does this really have to be fixed? I find it rather handy when I want to lockdown an area but not have the alarm flashing.

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
