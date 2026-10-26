# Bug 55: Closets use absolute string in open/close procs + coffins

| Field | Value |
|---|---|
| SourceForge page | https://sourceforge.net/p/openss13/bugs/55/ |
| Old tracker ID | — |
| Status | open |
| Milestone | Trunk |
| Priority | 5 |
| Labels | — |
| Reported by | aaron-aza |
| Assigned to | — |
| Created | 2009-06-07 13:26:16 UTC |
| Last modified | 2009-06-07 13:26:16 UTC |

## Description

Firstly, this fix fixes the limited ability to add your own closets to the code. By default, it used 'emcloset1' as a icon\_state when opening nearly all closets. I have changed this so that it reflects the 'orig\_closed' variable, which \(contrary to the name\) holds the string for the open value of closets. 

Now it is possible to add new 'closet' items with custom open icons by adding it like this:

/obj/closet/coffin
desc = "It's a coffin."
name = "Coffin"
icon\_state="coffin"
original="coffin"
orig\_closed = "coffino"

And as the code would suggest, I have also added in a coffin to replace the default 'closet' that has been used as coffins for an age. The patch also adds two icons - a coffin and coffin open icon \('coffin' and 'coffino'\) to stationobjs.dmi.

Attached is the patch file.

## Comments (1)

### aaron-aza · 2009-06-07 13:26:17 UTC

Closets use absolute string & coffin patch.

Attachment: [ss13coffinpatch.patch](attachments/ss13coffinpatch.patch) (3,509 bytes)

## Commits that cite this ticket

None of the SVN commit messages cite this ticket's old tracker ID.

## SVN revisions mentioned in this ticket

None.
