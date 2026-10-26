# OpenSS13 SourceForge trackers

This branch is an archive of the openss13 project's SourceForge issue trackers. It is **not part of the SVN history**.
The rest of this repository was converted from SVN; this branch was added afterwards and shares no history with it.

Snapshot taken 2026-10-26 through the SourceForge REST API (`https://sourceforge.net/rest/p/openss13/...`):

- [Bugs](bugs/INDEX.md): 55 tickets
- [Support tickets](support-tickets/INDEX.md): 1 ticket
- 249 comments in total, 10 attachments (all patch files)

## Layout

```
bugs/INDEX.md                 table of all bugs
bugs/NNN/README.md            readable ticket: fields, description, comments, related commits
bugs/NNN/ticket.json          raw API response for the ticket, unchanged
bugs/NNN/thread.json          raw API response for the full comment thread, unchanged
bugs/NNN/attachments/         files attached to comments
bugs/tracker.json             raw tracker listing: milestones, settings
support-tickets/...           same layout
cross-references/old-tracker-ids.md   7-digit IDs from the old tracker -> tickets
cross-references/by-revision.md       SVN revision -> tickets and git commits
project.json                  raw project description
```

## Notes

- Ticket numbers match SourceForge: bugs/003 is https://sourceforge.net/p/openss13/bugs/3/.
- Commit messages cite the old 7-digit tracker IDs; [old-tracker-ids.md](cross-references/old-tracker-ids.md) maps them to tickets.
- Ticket text is SourceForge Markdown, copied unchanged except for line endings. The raw JSON files keep it exactly.
- Many comments start with "Logged In: YES / user_id=… / Originator: …". That header was added by SourceForge's old tracker.
- Comments marked "field change" record changes to status, milestone and other fields.
- Times are as SourceForge reports them (UTC).
