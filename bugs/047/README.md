# Bug 47: AI Interaction in trunk

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/47/ |
| Old tracker ID | — |
| Status | open |
| Milestone | Trunk |
| Priority | 5 |
| Labels | — |
| Reported by | oronar |
| Assigned to | — |
| Created | 2008-07-08 05:23:08 UTC |
| Last modified | 2008-07-10 04:32:06 UTC |

> Patches pasted into the text below are missing the leading spaces and tabs of many lines; SourceForge already stores them that way. Attached `.patch` files, where there are any, are intact.

## Description

In the current trunk \(as of revision 90\), the AI cannot interact with anything that requires a double click\(or single if single click is toggled\).

When canreach was implemented, there was nothing to handle the possibility of the mob being an AI and to use attack\_ai. I've fixed the problem and attached a patch. It seems that that rc-2 has a handles it, which could be used instead of my patch.

Also the drone as well cannot interact with anything. This could be fixed by having it use attack\_hand like with /mob/human or by adding an attack\_drone proc.

## Comments (4)

### oronar · 2008-07-08 05:23:08 UTC

Patch to fix attack_ai

Attachment: [attackaifix.patch](attachments/attackaifix.patch) (29,456 bytes)

### oronar · 2008-07-08 05:23:27 UTC · field change

- **summary**: AI Interation in trunk --> AI Interaction in trunk

### stephen001 · 2008-07-08 05:43:35 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

I've attached a cleaned-up version of this patch. Dunno what all that random noise was about.

```diff
Index: trunk/Code/items.dm
===================================================================
--- trunk/Code/items.dm	(revision 90)
+++ trunk/Code/items.dm	(working copy)
@@ -5859,2 +5859,4 @@
src.hand_p(user, user.hand)
-			
+				else
+					if (istype(user, /mob/ai))
+						src.hand_a(user, user.hand)
```

### zjm7891 · 2008-07-10 04:32:06 UTC · field change

- **milestone**:  --> Trunk

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r90 | description | In the current trunk \(as of revision 90\), the AI cannot interact with anything… | `4993557aa3f4` /branches/1.0-rc-2 |
