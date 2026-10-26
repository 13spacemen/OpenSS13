# OpenSS13

OpenSS13 is an open source [BYOND](https://www.byond.com/) game: a space station survival simulation written in
DreamMaker. It was developed in 2008 on SourceForge
([sourceforge.net/projects/openss13](https://sourceforge.net/projects/openss13/)), starting from Space Station 13
code migrated from the SS13.net repository.

This repository holds the project's complete history, converted from its SourceForge SVN repository
(122 revisions, April to August 2008).

## Download

[OpenSS13 1.0](https://github.com/13spacemen/OpenSS13/releases/tag/1.0-release), released on 2008-07-10, is on the
Releases page with the original SourceForge downloads: the compiled game and the source as released.

## Building and running

1. Install BYOND, which includes Dream Maker (the compiler) and Dream Daemon (the server).
2. Open `spacestation13.dme` in Dream Maker and compile it. The map is `ss13h_new.dmp`.
3. Host the compiled `spacestation13.dmb` with Dream Daemon.

The server reads `config.txt` at startup and falls back to default settings without it. `mode.txt` holds the default game mode; the server rewrites it when the mode is changed.

The 1.0 release was compiled with BYOND 420 (2008). Current BYOND versions may need small code changes to compile
this source; that has not been tested here.

## Repository layout

`master` is SVN's trunk, the main line of development. New work goes here.

| Branch | Contents |
|---|---|
| `master` | SVN trunk, continued |
| `svn-final-import` | SVN trunk exactly as it was at the last SVN revision (r122). Kept unchanged as an archive. |
| `svn-mirror` | The whole SVN repository at every revision, including the contributor docs and build scripts that sat outside trunk |
| `1.0-rc-1`, `1.0-rc-2` | Release branches for 1.0 RC 1, RC 2 and the final 1.0 |
| `admin-system` | An experimental branch, created but never worked on |
| `1.0+p` | A short-lived branch for pipe changes |
| `admin-system@28`, `1.0+p@115` | Earlier versions of branches that were deleted and re-created in SVN |
| `sourceforge-tracker` | An archive of the SourceForge bug tracker: 55 bugs and 1 support ticket, with comments and patches |

| Tag | Points to |
|---|---|
| `1.0-release` | The commit the 1.0 release was built from (SVN r101) |
| `1.0`, `1.0-rc-1`, `1.0-rc-2` | The SVN tags. `1.0` was modified in SVN after the release (r118), so it is not the released code. |
| `1.0@99`, `1.0-rc-2@75` | Earlier versions of SVN tags that were deleted and re-created |

A name like `admin-system@28` follows SVN's notation: the branch as it existed up to revision 28.

### SVN details

Each converted commit ends with a `git-svn-id:` line giving its SVN path and revision. Further SVN information, such
as exact timestamps, changed paths and properties, is stored in git notes. After cloning, fetch and show them with:

```bash
git fetch origin refs/notes/svn:refs/notes/svn
```

```bash
git log --notes=svn
```

Commit authors are SVN usernames. SVN stored no email addresses, so each author has the address
`username@users.sourceforge.net`.

Bug numbers in commit messages, such as "Fixed bug #1936685", are IDs from SourceForge's old tracker. The
`sourceforge-tracker` branch maps every one of them to its ticket.

## Contributors

Commits in the SVN history are by stephen001, Zjm7891, shadowlord13, hobnob13 and murrawhip. SourceForge lists
Stephen Badger (stephen001) and Zach McNaney (zjm7891) as the project's developers. Many more people reported bugs
and contributed patches on the tracker.

## License

The SVN repository includes the GNU Lesser General Public License, version 3 (`lgpl-3.0.txt` at its top level, on the
`svn-mirror` branch). SourceForge's project page listed LGPL version 2.
