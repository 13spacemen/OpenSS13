# Bug 11: Crash with OOC!!!

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/11/ |
| Old tracker ID | 1965809 |
| Status | closed-fixed |
| Milestone | Pre-release |
| Priority | 9 |
| Labels | — |
| Reported by | anichowy |
| Assigned to | stephen001 |
| Created | 2008-05-17 05:50:09 UTC |
| Last modified | 2008-06-07 00:27:52 UTC |

## Description

"/mob/verb/ooc\(msg as text\)

if\(config.logooc\) world.log &lt;&lt; "OOC: \[src.name\]/\[src.key\] : \[msg\]"\
msg = cleanstring\(msg\)\
msg = html\_encode\(copytext\(msg, 1, 128\)\)\
if \(\!\( msg \)\)\
return\
if \(\(ooc\_allowed && \!\( src.muted \)\)\)\
for\(var/mob/M in world\)\
if \(\(M.client && M.client.listen\_ooc\)\)\
M &lt;&lt; text\("&lt;B&gt;OOC: \[\]&lt;/B&gt;: \[\]", src.key, msg\)\
//Foreach goto\(54\)\
return"

When it submits it to the world log, OOC isn't cut down to prevent spam, long strings of text could be sent into the dream daemon/seeker and could lag the server severely\!

Fix\!

Example:

Set a macro to:\
ooc "AHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHHH\(repeat like 400 more times\)

use it on repeat,

see the chat log fill up EVERYTHING you typed.

This crashes servers and people are abusing it\!

## Comments (7)

### anichowy · 2008-05-17 05:52:34 UTC

*Old tracker: logged in: yes · user ID 2056389 · originator: yes*

"if\(config.logooc\) world.log &lt;&lt; "OOC: \[src.name\]/\[src.key\] : \[msg\]"\
msg = cleanstring\(msg\)"


Should be


"msg = cleanstring\(msg\)\
if\(config.logooc\) world.log &lt;&lt; "OOC: \[src.name\]/\[src.key\] : \[msg\]"

### anichowy · 2008-05-17 05:53:40 UTC

*Old tracker: logged in: yes · user ID 2056389 · originator: yes*

And\
msg = html\_encode\(copytext\(msg, 1, 128\)\)\
should be before\
if\(config.logooc\) world.log &lt;&lt; "OOC: \[src.name\]/\[src.key\] : \[msg\]\
as well.

### anichowy · 2008-05-17 05:59:19 UTC

*Old tracker: logged in: yes · user ID 2056389 · originator: yes*

Important Note: You have to do this for every logging thing, like say.

### anichowy · 2008-05-17 06:05:04 UTC

*Old tracker: logged in: yes · user ID 2056389 · originator: yes*

and, I haven't fixed anything.

### stephen001 · 2008-05-23 18:10:02 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

I've moved the logging for both say and OOC to be much later in the verb. It should take into account stuff like muted status now, too. OOC is probably okay, not 100% on say though, I'd like that tested further.

### stephen001 · 2008-05-23 18:10:02 UTC · field change

- **assigned_to**: nobody --> stephen001
- **status**: open --> pending-fixed

### stephen001 · 2008-06-07 00:27:52 UTC · field change

- **milestone**:  --> Pre-release
- **status**: pending-fixed --> closed-fixed

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r28 | Attempt at fixing bug #1965809 | `7cb27a76b7b0` /trunk |

## SVN revisions mentioned in this ticket

None.
