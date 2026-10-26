# Bug 36: Meteor chance method still not perfect

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/36/ |
| Old tracker ID | — |
| Status | closed-later |
| Milestone | Trunk |
| Priority | 3 |
| Labels | — |
| Reported by | shadowlord13 |
| Assigned to | — |
| Created | 2008-06-21 03:44:10 UTC |
| Last modified | 2008-07-23 02:20:27 UTC |

## Description

About the method of meteor chance that we're currently using \(which is better than the previous one, but still isn't perfect\):\
&lt;Kurper&gt; Trafalgar: it seems like that only works right if config.meteorchance is a divisor of 100\
&lt;Kurper&gt; because rand\(\) also only works with integers\
&lt;Kurper&gt; it still works mostly right if meteorchance is not a divisor\
&lt;Kurper&gt; but the probabilities would be off\
&lt;Kurper&gt; if config.meteorchance is 75 then it would always spawn them\
&lt;Kurper&gt; as an extreme example\
&lt;Trafalgar&gt; The damn byond dm reference docs don't help\
&lt;Trafalgar&gt; They don't say what inputs the functions accept or don't

The solution we came to, which will need to be implemented: Take the chosen chance, multiply times 100. Each tick, do rand\(10000\), compare the result to the pre-multiplied chance. This gives us have a chance with a precision of 0.01 percent points everywhere, which should be more than sufficient.

## Comments (8)

### shadowlord13 · 2008-06-21 06:49:20 UTC

*Old tracker: logged in: yes · user ID 365542 · originator: yes*

\(This bug is for both the trunk and rc branch.\)

### kurper · 2008-06-22 18:46:19 UTC

*Old tracker: logged in: yes · user ID 1978724 · originator: no*

Actually, it turns out that rand\(\) returns a random float between 0 and 1 if you call it with no arguments, so that'd be a better way than having an arbitrary cutoff precision \(and probably less processor-intensive, too\).

### zjm7891 · 2008-06-25 11:36:11 UTC · field change

- **milestone**:  --> 854524

### zjm7891 · 2008-07-08 15:31:28 UTC

*Old tracker: logged in: yes · user ID 2047617 · originator: no*

I need to look further into it.  As of the moment, I don't see the problem causing this.  I'll check back with you guys later

### zjm7891 · 2008-07-08 15:31:28 UTC · field change

- **priority**: 5 --> 3
- **status**: open --> pending-later

### zjm7891 · 2008-07-10 04:37:19 UTC · field change

- **milestone**: 854524 --> Trunk

### sf-robot · 2008-07-23 02:20:27 UTC · field change

- **status**: pending-later --> closed-later

### sf-robot · 2008-07-23 02:20:27 UTC

*Old tracker: logged in: yes · user ID 1312539 · originator: no*

This Tracker item was closed automatically by the system. It was\
previously set to a Pending status, and the original submitter\
did not respond within 14 days \(the time period specified by\
the administrator of this Tracker\).

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
