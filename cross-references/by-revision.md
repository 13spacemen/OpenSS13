# Tickets by SVN revision

For each SVN revision: tickets whose old tracker ID its commit message cites ("cites"), and tickets whose text mentions the revision ("mentioned in").
Find the git commits for a revision with `git log --all --grep="@<rev> "`.

| SVN revision | Commit message | Tickets | git commit |
|---|---|---|---|
| r3 | Fixed bug #1936685, using patch provided by shadowlord13. | cites [bugs 3](../bugs/003/README.md) | `c3245b85dbb6` /trunk |
| r4 | Fixed bug #1937139. | cites [bugs 5](../bugs/005/README.md) | `b902cc91d72c` /trunk |
| r5 | Fixing bug #1936688, display (and logging) when player mode voting toggled was incorrect. | cites [bugs 4](../bugs/004/README.md)<br>mentioned in [bugs 4](../bugs/004/README.md) | `f5254ee9384f` /trunk |
| r12 | Fixed bug #1936681 | cites [bugs 2](../bugs/002/README.md) | `2ad01cf92795` /trunk |
| r17 | Added suggested fix for Bug #1952091. Needs testing. | cites [bugs 9](../bugs/009/README.md)<br>mentioned in [bugs 9](../bugs/009/README.md) | `31e25adfc51f` /trunk |
| r18 | Continue fixing bug #1952091 as per shadowlord13. | cites [bugs 9](../bugs/009/README.md)<br>mentioned in [bugs 7](../bugs/007/README.md) | `66ea0045fede` /trunk |
| r20 | Fix bug #1952749 as per shadowlord13 | cites [bugs 10](../bugs/010/README.md)<br>mentioned in [bugs 10](../bugs/010/README.md) | `78f34b16e5cd` /trunk |
| r28 | Attempt at fixing bug #1965809 | cites [bugs 11](../bugs/011/README.md) | `7cb27a76b7b0` /trunk |
| r38 | Fixed Bug #1986988. | cites [bugs 17](../bugs/017/README.md)<br>mentioned in [bugs 17](../bugs/017/README.md) | `51bcf70f4ac2` /trunk |
| r43 | Fixed bug #1987041 - ranks allowed to do actions differ from ones shown them | cites [bugs 18](../bugs/018/README.md)<br>mentioned in [bugs 18](../bugs/018/README.md) | `89f4a160d1a5` /branches/1.0-rc-1 |
| r44 | Fix for bug 1987047, "You cannot perform this. Action you must be of a higher ..." | cites [bugs 19](../bugs/019/README.md)<br>mentioned in [bugs 19](../bugs/019/README.md) | `1a8b49f89f01` /branches/1.0-rc-1 |
| r48 | Fixes for bugs 1987067 and 1987483. | cites [bugs 22](../bugs/022/README.md)<br>cites [bugs 23](../bugs/023/README.md)<br>mentioned in [bugs 22](../bugs/022/README.md)<br>mentioned in [bugs 23](../bugs/023/README.md) | `757dd2a49cbc` /branches/1.0-rc-1 |
| r51 | Made a change for #1986988. It passed the test-case, but just | cites [bugs 17](../bugs/017/README.md)<br>mentioned in [bugs 17](../bugs/017/README.md) | `d7860fa4730d` /branches/1.0-rc-1 |
| r52 | Fix for #1986988. Should be using url_encode. | cites [bugs 17](../bugs/017/README.md)<br>mentioned in [bugs 17](../bugs/017/README.md) | `1a35995cb996` /trunk |
| r53 | A bunch of bug fixes. I have the details on the fixes written down, what fixes are in what files, and what the fixes do, etc. I just need my internet connection to be reliable for long enough while I'm here to do all the virtual paperwork on the bug tracker about them all. | mentioned in [bugs 20](../bugs/020/README.md)<br>mentioned in [bugs 21](../bugs/021/README.md)<br>mentioned in [bugs 26](../bugs/026/README.md)<br>mentioned in [bugs 27](../bugs/027/README.md)<br>mentioned in [bugs 28](../bugs/028/README.md)<br>mentioned in [bugs 30](../bugs/030/README.md)<br>mentioned in [bugs 31](../bugs/031/README.md) | `a91d1bcf1c92` /branches/1.0-rc-1 |
| r57 | Implemented canReach for verbs, added calls to it to the verbs which needed it | mentioned in [bugs 35](../bugs/035/README.md) | `2324df01f3cc` /trunk |
| r63 | Fixed #1999232, patches attached to the Bug. | cites [bugs 35](../bugs/035/README.md)<br>mentioned in [bugs 35](../bugs/035/README.md) | `fd5399aecfe0` /branches/1.0-rc-1, `830c94694e01` /trunk |
| r64 | Applied canReach to DNA Scanner and DNA DNA Physical Reconstruction Accelerator, for #1939088. | cites [bugs 7](../bugs/007/README.md)<br>mentioned in [bugs 7](../bugs/007/README.md) | `838c86235238` /branches/1.0-rc-1, `47f8dae09177` /trunk |
| r67 | Added canReach to Cryocells, as per #1939088. | cites [bugs 7](../bugs/007/README.md) | `c400b6b419e9` /branches/1.0-rc-1, `41057541f6dc` /trunk |
| r80 | Fixed bug #1980809, lit weldingtools now ignite plasma. | cites [bugs 13](../bugs/013/README.md)<br>mentioned in [bugs 13](../bugs/013/README.md) | `f421fd2dc7ee` /branches/1.0-rc-2, `feedfc9af83d` /trunk |
| r81 | This patch allows V80 to compile, However, HobNob will need to rerun his bugfix to #1980809 | cites [bugs 13](../bugs/013/README.md) | `9761a83acc75` /branches/1.0-rc-2 |
| r82 | Applied patch by Stephen001 to fix bug #2002317 | cites [bugs 41](../bugs/041/README.md) | `aa99bcf75c06` /branches/1.0-rc-2 |
| r83 | Updated with missing code file to fix bug #1980809. | cites [bugs 13](../bugs/013/README.md)<br>mentioned in [bugs 41](../bugs/041/README.md) | `b8efabe42fc3` /branches/1.0-rc-2 |
| r85 | Sovled bug #1989294 and also removed a exploit ex had added for when he attacks with swords (AttackDelay was removed) | cites [bugs 24](../bugs/024/README.md)<br>mentioned in [bugs 24](../bugs/024/README.md) | `f7f83051dfae` /branches/1.0-rc-2 |
| r87 | Applied Animay's bugfix to fix bug #2003004 | cites [bugs 46](../bugs/046/README.md) | `f5e00da5c6e7` /branches/1.0-rc-2 |
| r88 | Fixed bug when making CTF_ASSIST as an object, it will create all grilles and reset everyone's position even though the game already started | mentioned in [bugs 46](../bugs/046/README.md) | `ed78c8634688` /branches/1.0-rc-2 |
| r89 | Fixed bug #2002397 | cites [bugs 45](../bugs/045/README.md)<br>mentioned in [bugs 45](../bugs/045/README.md) | `334e1c78a43f` /branches/1.0-rc-2 |
| r90 | Fixed bug #2002391   | cites [bugs 44](../bugs/044/README.md)<br>mentioned in [bugs 44](../bugs/044/README.md)<br>mentioned in [bugs 47](../bugs/047/README.md) | `4993557aa3f4` /branches/1.0-rc-2 |
| r91 | Fixed bug #2013401 and #2013405 | cites [bugs 48](../bugs/048/README.md)<br>cites [bugs 49](../bugs/049/README.md)<br>mentioned in [bugs 48](../bugs/048/README.md)<br>mentioned in [bugs 49](../bugs/049/README.md) | `7524a4d9c3cc` /branches/1.0-rc-2 |
| r92 | Fixed bug #2002387. | cites [bugs 43](../bugs/043/README.md)<br>mentioned in [bugs 43](../bugs/043/README.md) | `9935cef69805` /branches/1.0-rc-2 |
| r93 | Fixed bug #1980814 and.. it was a doozy!  stupid logic trees | cites [bugs 15](../bugs/015/README.md)<br>mentioned in [bugs 15](../bugs/015/README.md) | `32b24ffb6278` /branches/1.0-rc-2 |
| r94 | Fixed bug #2002381, also removed the issue with unloading yourself | cites [bugs 42](../bugs/042/README.md)<br>mentioned in [bugs 42](../bugs/042/README.md) | `66c3bb76e753` /branches/1.0-rc-2 |
| r95 | Fixed bug #1980820 All verbs should now check status and restricted | cites [bugs 16](../bugs/016/README.md)<br>mentioned in [bugs 16](../bugs/016/README.md) | `9a47ad3950e7` /branches/1.0-rc-2 |
| r106 | Applied stephen's cellautomata-cleanup-trunk.patch file. | mentioned in [bugs 51](../bugs/051/README.md)<br>mentioned in [bugs 52](../bugs/052/README.md)<br>mentioned in [bugs 53](../bugs/053/README.md) | `7ed0e07d46b1` /trunk |
