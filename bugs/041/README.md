# Bug 41: Attacking with objects that have afterefffects

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/41/ |
| Old tracker ID | 2002317 |
| Status | closed-fixed |
| Milestone | Version 1.0 RC 2 |
| Priority | 8 |
| Labels | — |
| Reported by | zjm7891 |
| Assigned to | zjm7891 |
| Created | 2008-06-25 08:55:36 UTC |
| Last modified | 2008-06-28 05:17:06 UTC |

> Patches pasted into the text below are missing the leading spaces and tabs of many lines; SourceForge already stores them that way. Attached `.patch` files, where there are any, are intact.

## Description

Any gun is currently able to attack like its orange\(1\) no matter how far away you are.  I'll be looking into this.

## Comments (6)

### zjm7891 · 2008-06-25 13:54:16 UTC · field change

- **summary**: Attacking with a "guns" --> Attacking with objects that have afterefffects

### zjm7891 · 2008-06-25 13:54:16 UTC

*Old tracker: logged in: yes · user ID 2047617 · originator: yes*

Also, Other items such as fire extinguishers are effected and you can attack from far away.

### stephen001 · 2008-06-26 00:54:04 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

I've attached a patch to actually add weldingtools back into the repository. Unfortunately Hobnob will need to redo his bug-fix, at least in part. Apply at branches/1.0-rc-2/

```diff
Index: spacestation13.dme
===================================================================
--- spacestation13.dme	(revision 80)
+++ spacestation13.dme	(working copy)
@@ -26,7 +26,6 @@
// END_FILE_DIR

// BEGIN_PREFERENCES
-#define DEBUG
// END_PREFERENCES

// BEGIN_INCLUDE
Index: Code/Item/Weapon/weldingtool.dm
===================================================================
--- Code/Item/Weapon/weldingtool.dm	(revision 0)
+++ Code/Item/Weapon/weldingtool.dm	(revision 0)
@@ -0,0 +1,46 @@
+/obj/item/weapon/weldingtool
+	flags = 322.0
+	force = 3.0
+	icon_state = "welder"
+	name = "weldingtool"
+	throwforce = 5.0
+	throwspeed = 5.0
+	w_class = 2.0
+	var/welding = 0.0
+	var/weldfuel = 20.0
+	
+	afterattack(obj/O, mob/user)
+		if (src.welding)
+			src.weldfuel--
+			if (src.weldfuel <= 0)
+				usr << "\blue Need more fuel!"
+				src.welding = 0
+				src.force = 3
+				src.damtype = "brute"
+				src.icon_state = "welder"
+			var/turf/location = user.loc
+			if (!( istype(location, /turf) ))
+				return
+			location.firelevel = location.poison + 1
+	
+	attack_self(mob/user)
+		src.welding = !( src.welding )
+		if (src.welding)
+			if (src.weldfuel <= 0)
+				user << "\blue Need more fuel!"
+				src.welding = 0
+				return 0
+			user << "\blue You will now weld when you attack."
+			src.force = 15
+			src.damtype = "fire"
+			src.icon_state = "welder1"
+		else
+			user << "\blue Not welding anymore."
+			src.force = 3
+			src.damtype = "brute"
+			src.icon_state = "welder"
+	
+	examine()
+		set src in usr
+		usr << text("\icon[] [] contains [] units of fuel left!", src, src.name, src.weldfuel)
+
```

### stephen001 · 2008-06-26 00:59:41 UTC

*Old tracker: logged in: yes · user ID 1640007 · originator: no*

Attached is a patch to fix the actual bug. Apply at branches/1.0-rc-2/. Watch out for long lines wrapping, none of these lines wrap.

```diff
Index: Code/items.dm
===================================================================
--- Code/items.dm	(revision 80)
+++ Code/items.dm	(working copy)
@@ -5803,9 +5803,10 @@

if (retval & CANREACH_ALLOWED)
if (!( usr.restrained() ))
-			if ((W && !( istype(src, /obj/screen) )))
-				src.attackby(W, usr)
-				if (W)
+			if ((W && !( istype(src, /obj/screen))))
+				if (retval & CANREACH_CANTOUCH)
+					src.attackby(W, usr)
+				if ((retval & CANREACH_USINGWEAPON) && !(retval & CANREACH_CANTOUCH))
W.afterattack(src, usr)
else
if (istype(usr, /mob/ai)) /*The AI couldn't activate computers, this should fix that problem*/
```

### zjm7891 · 2008-06-28 05:17:06 UTC · field change

- **status**: open --> closed-fixed

### zjm7891 · 2008-06-28 05:17:06 UTC

*Old tracker: logged in: yes · user ID 2047617 · originator: yes*

Fixed by Stephen001, Works as of REV 83

## Commits that cite this ticket

| SVN revision | Commit message | git commit |
|---|---|---|
| r82 | Applied patch by Stephen001 to fix bug #2002317 | `aa99bcf75c06` /branches/1.0-rc-2 |

## SVN revisions mentioned in this ticket

These are text matches like "fixed in rev 93". Some are only references, not fixes.

| SVN revision | Where | Text | git commit |
|---|---|---|---|
| r83 | comment by zjm7891, 2008-06-28 05:17:06 | Fixed by Stephen001, Works as of REV 83 | `b8efabe42fc3` /branches/1.0-rc-2 |
