# Bug 12: timer/igniters don't ignite plasma when the timer finishes

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/12/ |
| Old tracker ID | — |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 5 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | shadowlord13 |
| Created | 2008-05-31 17:13:44 UTC |
| Last modified | 2008-06-17 22:04:59 UTC |

## Description

Timer/igniters don't seem to ignite plasma when the timer finishes counting down.

Once the cause is figured out, we should probably make sure prox/igniters and such aren't similarly broken.

## Comments (4)

### shadowlord13 · 2008-05-31 18:27:33 UTC

Logged In: YES 
user\_id=365542
Originator: YES

Fixed \(and tested to make sure the fix works\).

The cause was that screwdrivering the timer/igniter didn't set status on the igniter like it was supposed to, \(It did for radio/igniters and prox/igniters\) so basically the igniter remained unsecured and wouldn't ignite.

### shadowlord13 · 2008-05-31 18:27:33 UTC · field change

- **status**: open --> open-fixed

### shadowlord13 · 2008-05-31 18:27:53 UTC · field change

- **status**: open-fixed --> closed-fixed

### stephen001 · 2008-06-17 22:04:59 UTC · field change

- **assigned_to**: nobody --> shadowlord13

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
