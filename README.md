# Challenges

## Refining Git History (10 Challenges)

### Missing File Fix:

```bash
git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test1.md
        test2.md
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git add test1.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git commit -m "chore: Create initial file"
[main (root-commit) b3dba64] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git add test2.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git commit -m "chore: Create another file"
[main 51ae076] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git add test3.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git commit -m "chore: Create third and fourth files"
[main abcdb78] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git log
commit abcdb78a8afadc576296a4f8550d20e3540c0a5a (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:23:08 2025 +0200

    chore: Create third and fourth files

commit 51ae0765a37a532bf8b59b604727f3a93a852770
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:15:32 2025 +0200

    chore: Create another file

commit b3dba64cdb8195762be7bdad14290fa6434a6674
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git add test4.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> git commit -m "chore: Create third and fourth files"
[main 8e4ea4f] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
PS C:\Users\freez\OneDrive\Desktop\exercise\Git-Exercises> 
```

### Editing Commit History:

```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git reflog
8e4ea4f (HEAD -> main) HEAD@{0}: commit: chore: Create third and fourth files
abcdb78 HEAD@{1}: commit: chore: Create third and fourth files
51ae076 HEAD@{2}: commit: chore: Create another file
b3dba64 HEAD@{3}: commit (initial): chore: Create initial file

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git rebase -i ^C

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git rebase -i b3dba64
[detached HEAD d7fdfdb] chore: Create Second file
 Date: Tue Sep 2 18:15:32 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git log
commit e0248de99d7e775e5329657237040c22b60f4ce0 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:23:54 2025 +0200

    chore: Create third and fourth files

commit 35c6759bc694873a739e6f2ad208ff5d67cff937
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:23:08 2025 +0200

    chore: Create third and fourth files

commit d7fdfdb23887def629c2d8171015cf144faec55b
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:15:32 2025 +0200

    chore: Create Second file

commit b3dba64cdb8195762be7bdad14290fa6434a6674
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

```
### Keeping History Tidy - Squashing Commits:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git rebase -i --root
[detached HEAD 627a4eb] chore: Create initial file
 Date: Tue Sep 2 18:13:20 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

```
### Splitting a Commit:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git reset --soft HEAD~

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test4.md


freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git reset --soft HEAD~

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test3.md
        new file:   test4.md
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git restore --staged test3.md

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test4.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md


freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git restore --staged test4.md

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git add test3.md

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git commit -m "chore: Create Third File"
[main 38095a4] chore: Create Third File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git add test4.md

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git commit -m "chore: Create Fourth File"
[main 7d60794] chore: Create Fourth File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git log
commit 7d6079432faf5dea3cec1dff421b0f9b54f15437 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:33 2025 +0200

    chore: Create Fourth File

commit 38095a4b11082489c27d8b07529139d724a69c1a
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    chore: Create Third File

commit 627a4eb2997c426b17fc6f0972a20416fddfd49c
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file
```
### Advanced Squashing:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log
commit 7d6079432faf5dea3cec1dff421b0f9b54f15437 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:33 2025 +0200

    chore: Create Fourth File

commit 38095a4b11082489c27d8b07529139d724a69c1a
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    chore: Create Third File

commit 627a4eb2997c426b17fc6f0972a20416fddfd49c
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git rebase -i 627a4eb
[detached HEAD 205d5e9] Create third and fourth files
 Date: Tue Sep 2 18:46:22 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log
commit 205d5e92309a370ffabe5689406bbeb8ea3938a0 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    Create third and fourth files

    chore: Create Third File

    chore: Create Fourth File

commit 627a4eb2997c426b17fc6f0972a20416fddfd49c
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> 
```
### Dropping a Commit:
```bash
git add unwanted.txt
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Unwanted commit"
[main 9d13c2f] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log
commit 9d13c2f69a0e5935889718eba89ec451b52be8ab (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Wed Sep 3 10:14:17 2025 +0200

    Unwanted commit

commit 205d5e92309a370ffabe5689406bbeb8ea3938a0
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    Create third and fourth files

    chore: Create Third File

    chore: Create Fourth File

commit 627a4eb2997c426b17fc6f0972a20416fddfd49c
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> ^C
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git rebase -i 205d5e9
Successfully rebased and updated refs/heads/main.
```
### Reordering Commits:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log
commit 205d5e92309a370ffabe5689406bbeb8ea3938a0 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    Create third and fourth files

    chore: Create Third File

    chore: Create Fourth File

commit 627a4eb2997c426b17fc6f0972a20416fddfd49c
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git rebase -i --root
Successfully rebased and updated refs/heads/main.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log
commit 87c0d8fd457610b6a9573ecb6a7fa1799cf33f54 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file

commit 58e4b498360b66a19be2cf367a314faed856f901
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    Create third and fourth files

    chore: Create Third File

    chore: Create Fourth File
(END)
```
### Cherry-Picking Commits:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout -b ft/branch
Switched to a new branch 'ft/branch'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch ft/branch
nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add test5.md
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Implemented test 5"
[ft/branch 45359c5] Implemented test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add test5.md
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Implemented test 5"
[ft/branch 45359c5] Implemented test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git reflog
45359c5 (HEAD -> ft/branch) HEAD@{0}: commit: Implemented test 5
87c0d8f (main) HEAD@{1}: checkout: moving from main to ft/branch
87c0d8f (main) HEAD@{2}: rebase (finish): returning to refs/heads/main
87c0d8f (main) HEAD@{3}: rebase (pick): chore: Create initial file
58e4b49 HEAD@{4}: rebase (pick): Create third and fourth files
d84f4e8 HEAD@{5}: rebase (start): checkout d84f4e8906d23e895c4a5ac85f909c172749d37d
205d5e9 HEAD@{6}: rebase (finish): returning to refs/heads/main
205d5e9 HEAD@{7}: rebase (start): checkout 205d5e9
9d13c2f HEAD@{8}: commit: Unwanted commit
205d5e9 HEAD@{9}: rebase (finish): returning to refs/heads/main
205d5e9 HEAD@{10}: rebase: fast-forward
627a4eb HEAD@{11}: rebase: fast-forward
41881f1 HEAD@{12}: rebase (start): checkout 41881f13571303242c254768add9eacbbf86aa01
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main   
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git cherry-pick 45359c5
[main 1f94321] Implemented test 5
 Date: Wed Sep 3 10:40:09 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log
commit 1f94321f4fdbd5e10d96f6af3dcf73807ff71714 (HEAD -> main)
Author: Seacrs <shemachris072@gmail.com>
Date:   Wed Sep 3 10:40:09 2025 +0200

    Implemented test 5

commit 87c0d8fd457610b6a9573ecb6a7fa1799cf33f54
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:13:20 2025 +0200

    chore: Create initial file

    chore: Create initial file

    chore: Create Second file

commit 58e4b498360b66a19be2cf367a314faed856f901
Author: Seacrs <shemachris072@gmail.com>
Date:   Tue Sep 2 18:46:22 2025 +0200

    Create third and fourth files

    chore: Create Third File

    chore: Create Fourth File
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> 
```
### Visualizing Commit History (Bonus):
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --graph 
* commit 1f94321f4fdbd5e10d96f6af3dcf73807ff71714 (HEAD -> main)
| Author: Seacrs <shemachris072@gmail.com>
| Date:   Wed Sep 3 10:40:09 2025 +0200
|
|     Implemented test 5
|
* commit 87c0d8fd457610b6a9573ecb6a7fa1799cf33f54
| Author: Seacrs <shemachris072@gmail.com>
| Date:   Tue Sep 2 18:13:20 2025 +0200
|
|     chore: Create initial file
|
|     chore: Create initial file
|
|     chore: Create Second file
|
* commit 58e4b498360b66a19be2cf367a314faed856f901
  Author: Seacrs <shemachris072@gmail.com>
  Date:   Tue Sep 2 18:46:22 2025 +0200

      Create third and fourth files

      chore: Create Third File

      chore: Create Fourth File
(END)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --graph --oneline
* 1f94321 (HEAD -> main) Implemented test 5
* 87c0d8f chore: Create initial file
* 58e4b49 Create third and fourth files
```
### Understanding Reflogs (Bonus):
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git reflog
1f94321 (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
87c0d8f HEAD@{1}: checkout: moving from ft/branch to main
45359c5 (ft/branch) HEAD@{2}: commit: Implemented test 5
87c0d8f HEAD@{3}: checkout: moving from main to ft/branch
87c0d8f HEAD@{4}: rebase (finish): returning to refs/heads/main
87c0d8f HEAD@{5}: rebase (pick): chore: Create initial file
58e4b49 HEAD@{6}: rebase (pick): Create third and fourth files
d84f4e8 HEAD@{7}: rebase (start): checkout d84f4e8906d23e895c4a5ac85f909c172749d37d
205d5e9 HEAD@{8}: rebase (finish): returning to refs/heads/main
205d5e9 HEAD@{9}: rebase (start): checkout 205d5e9
9d13c2f HEAD@{10}: commit: Unwanted commit
205d5e9 HEAD@{11}: rebase (finish): returning to refs/heads/main
205d5e9 HEAD@{12}: rebase: fast-forward
627a4eb HEAD@{13}: rebase: fast-forward
41881f1 HEAD@{14}: rebase (start): checkout 41881f13571303242c254768add9eacbbf86aa01
73b265e HEAD@{15}: commit: chore: Create third and fourth files
205d5e9 HEAD@{16}: rebase (finish): returning to refs/heads/main
205d5e9 HEAD@{17}: rebase: fast-forward
627a4eb HEAD@{18}: rebase: fast-forward
d952b31 HEAD@{19}: rebase (start): checkout d952b3122cade733b616d15f10eccbe303d4f2e2
dbbf735 HEAD@{20}: rebase (finish): returning to refs/heads/main
dbbf735 HEAD@{21}: rebase: fast-forward
205d5e9 HEAD@{22}: rebase: fast-forward
627a4eb HEAD@{23}: rebase: fast-forward
13a0873 HEAD@{24}: rebase (start): checkout 13a0873df37b5549fd22b1764d02522e338ad76f
78dd6c8 HEAD@{25}: commit: Unwanted commit
3cc66b7 HEAD@{26}: revert: Revert "Unwanted commit"
dbbf735 HEAD@{27}: reset: moving to dbbf735
dbbf735 HEAD@{28}: reset: moving to dbbf735
dbbf735 HEAD@{29}: reset: moving to HEAD
dbbf735 HEAD@{30}: commit: Unwanted commit
205d5e9 HEAD@{31}: rebase (finish): returning to refs/heads/main
205d5e9 HEAD@{32}: rebase (squash): Create third and fourth files
38095a4 HEAD@{33}: rebase (start): checkout 627a4eb
7d60794 HEAD@{34}: commit: chore: Create Fourth File
38095a4 HEAD@{35}: commit: chore: Create Third File
627a4eb HEAD@{36}: reset: moving to HEAD~
a8dc103 HEAD@{37}: commit: chore: Create Third File
627a4eb HEAD@{38}: reset: moving to HEAD~
3396771 HEAD@{39}: commit: chore: ^VCreate Third File
627a4eb HEAD@{40}: reset: moving to HEAD~
e732355 HEAD@{41}: reset: moving to HEAD~
46bb24e HEAD@{42}: reset: moving to HEAD
46bb24e HEAD@{43}: rebase (finish): returning to refs/heads/main
46bb24e HEAD@{44}: rebase (pick): chore: Create third and fourth files
e732355 HEAD@{45}: rebase (pick): chore: Create third and fourth files
627a4eb HEAD@{46}: rebase (squash): chore: Create initial file
b3dba64 HEAD@{47}: rebase: fast-forward
d769cbb HEAD@{48}: rebase (start): checkout d769cbb17e5d0f941fd60b57863e80805a4c60b4
e0248de HEAD@{49}: rebase (finish): returning to refs/heads/main
e0248de HEAD@{50}: rebase (pick): chore: Create third and fourth files
35c6759 HEAD@{51}: rebase (pick): chore: Create third and fourth files
d7fdfdb HEAD@{52}: rebase (reword): chore: Create Second file
51ae076 HEAD@{53}: rebase: fast-forward
b3dba64 HEAD@{54}: rebase (start): checkout b3dba64
8e4ea4f HEAD@{55}: commit: chore: Create third and fourth files
abcdb78 HEAD@{56}: commit: chore: Create third and fourth files
51ae076 HEAD@{57}: commit: chore: Create another file
b3dba64 HEAD@{58}: commit (initial): chore: Create initial file
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git reflog @{6.hour.ago}
7d60794 refs/heads/main@{Tue Sep 2 18:46:33 2025 +0200}: commit: chore: Create Fourth File
38095a4 refs/heads/main@{Tue Sep 2 18:46:22 2025 +0200}: commit: chore: Create Third File
627a4eb refs/heads/main@{Tue Sep 2 18:45:13 2025 +0200}: reset: moving to HEAD~
a8dc103 refs/heads/main@{Tue Sep 2 18:44:52 2025 +0200}: commit: chore: Create Third File
627a4eb refs/heads/main@{Tue Sep 2 18:44:34 2025 +0200}: reset: moving to HEAD~
3396771 refs/heads/main@{Tue Sep 2 18:43:34 2025 +0200}: commit: chore: ^VCreate Third File
627a4eb refs/heads/main@{Tue Sep 2 18:42:43 2025 +0200}: reset: moving to HEAD~
e732355 refs/heads/main@{Tue Sep 2 18:42:36 2025 +0200}: reset: moving to HEAD~
46bb24e refs/heads/main@{Tue Sep 2 18:36:38 2025 +0200}: rebase (finish): refs/heads/main onto d769cbb17e5d0f941fd60b57863e80805a4c60b4
e0248de refs/heads/main@{Tue Sep 2 18:30:42 2025 +0200}: rebase (finish): refs/heads/main onto b3dba64cdb8195762be7bdad14290fa6434a6674
8e4ea4f refs/heads/main@{Tue Sep 2 18:23:54 2025 +0200}: commit: chore: Create third and fourth files
abcdb78 refs/heads/main@{Tue Sep 2 18:23:08 2025 +0200}: commit: chore: Create third and fourth files
51ae076 refs/heads/main@{Tue Sep 2 18:15:32 2025 +0200}: commit: chore: Create another file
b3dba64 refs/heads/main@{Tue Sep 2 18:13:20 2025 +0200}: commit (initial): chore: Create initial file

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git reflog show ft/branch
45359c5 (ft/branch) ft/branch@{0}: commit: Implemented test 5
87c0d8f ft/branch@{1}: branch: Created from HEAD
```

## Branching Basics (10 Challenges)

### Feature Branch Creation:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git branch ft/new-feature
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git checkout ft/new-feature
Switched to branch 'ft/new-feature'
```
### Working on the Feature Branch:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/new-feature)
$ git add feature.txt

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/new-feature)
$ git commit -m "Impleted core functionality for new feature"
[ft/new-feature ac3c889] Impleted core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```
### Switching Back and Making More Changes:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        readme.txt

nothing added to commit but untracked files present (use "git add" to track)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git add readme.txt

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git commit -m "Updated project readme"
[main 9634bb3] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
```
### Local vs. Remote Branches:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch -r                    
  origin/ft/branch
  origin/ft/new-feature
  origin/main
```
### Branch Deletion:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
c88fcdb (HEAD -> main) Merge branch 'ft/new-feature' Added new feature
9634bb3 (origin/main) Updated project readme
ac3c889 (origin/ft/new-feature, ft/new-feature) Impleted core functionality for new feature
1f94321 Implemented test 5
87c0d8f chore: Create initial file
58e4b49 Create third and fourth files
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch -d ft/new-feature
Deleted branch ft/new-feature (was ac3c889).
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch
  ft/branch
* main
```
### Creating a Branch from a Commit:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
c88fcdb (HEAD -> main) Merge branch 'ft/new-feature' Added new feature
9634bb3 (origin/main) Updated project readme
ac3c889 (origin/ft/new-feature) Impleted core functionality for new feature
1f94321 Implemented test 5
87c0d8f chore: Create initial file
58e4b49 Create third and fourth files
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout -b ft/new-branch-from-commit 1f94321    
Switched to a new branch 'ft/new-branch-from-commit'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline --graph
* 1f94321 (HEAD -> ft/new-branch-from-commit) Implemented test 5
* 87c0d8f chore: Create initial file
* 58e4b49 Create third and fourth files
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch                        
  ft/branch
* ft/new-branch-from-commit
  main
```
### Branch Merging:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "new feature"
[ft/new-branch-from-commit 326b322] new feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git merge ft/new-branch-from-commit
Already up to date.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git merge ft/new-branch-from-commit
Auto-merging feature.txt
Merge made by the 'ort' strategy.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch
  ft/branch
  ft/new-branch-from-commit
* main
```
### Branch Rebasing:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
1e35dcf (HEAD -> ft/new-branch-from-commit) New features
326b322 new feature
1f94321 Implemented test 5
87c0d8f chore: Create initial file
58e4b49 Create third and fourth files
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git rebase main
dropping 326b322a21ab65d4a9775f1262dbae2064340aef new feature -- patch contents already upstream
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline --graph
* 666269f (HEAD -> ft/new-branch-from-commit) New features
* 8a01be2 (main) Impleted core functionality for new feature
* 9634bb3 (origin/main) Updated project readme
* 1f94321 Implemented test 5
* 87c0d8f chore: Create initial file
* 58e4b49 Create third and fourth files
```
### Renaming Branches:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status    
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch
  ft/branch
  ft/new-branch-from-commit
* main
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch -m ft/new-branch-from-commit ft/improved-branch-name
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch
  ft/branch
  ft/improved-branch-name
* main
```
### Checking Out Detached HEAD:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
8a01be2 (HEAD -> main) Impleted core functionality for new feature
9634bb3 (origin/main) Updated project readme
1f94321 Implemented test 5
87c0d8f chore: Create initial file
58e4b49 Create third and fourth files
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout 9634bb3
Note: switching to '9634bb3'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 9634bb3 Updated project readme
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add .
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "New files"
[detached HEAD c49e110] New files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test7.md
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
c49e110 (HEAD) New files
9634bb3 (origin/main) Updated project readme
1f94321 Implemented test 5
87c0d8f chore: Create initial file
58e4b49 Create third and fourth files
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  c49e110 New files

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> c49e110

Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
924433f (HEAD -> main) Implemented core functionality for new feature
9634bb3 (origin/main) Updated project readme
1f94321 Implemented test 5
87c0d8f chore: Create initial file
58e4b49 Create third and fourth files
```

##  Advanced Workflows (10+ Challenges)

### Stashing Changes:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
        nav.css

nothing added to commit but untracked files present (use "git add" to track)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
        new file:   nav.css

PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git stash     
Saved working directory and index state WIP on main: 924433f Implemented core functionality for new feature
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git stash list
stash@{0}: WIP on main: 924433f Implemented core functionality for new feature
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git stash show
 index.html | 0
 nav.css    | 0
 2 files changed, 0 insertions(+), 0 deletions(-)
```
### Retrieving Stashed Changes:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git stash
No local changes to save
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git stash show
 index.html | 0
 nav.css    | 0
 2 files changed, 0 insertions(+), 0 deletions(-)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git stash pop
On branch main
Your branch is up to date with 'origin/main'.

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
        new file:   nav.css

Dropped refs/stash@{0} (e7b22f11df148da02e9eca3386c65dd224fff849)
```
### Branch Merging Conflicts (Continued):
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Added changes"
[main cca32b9] Added changes
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout ft/new-feature
Switched to branch 'ft/new-feature'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout ft/new-feature
M       test4.md
Already on 'ft/new-feature'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch ft/new-feature
You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Additional changes"
[ft/new-feature f0d22a4] Additional changes
 1 file changed, 1 insertion(+), 1 deletion(-)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git merge ft/new-feature
Auto-merging test4.md
CONFLICT (content): Merge conflict in test4.md
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --merge --oneline
f0d22a4 (ft/new-feature) Additional changes
cca32b9 (HEAD -> main) Added changes
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   test4.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Merge fix"
[main e455a24] Merge fix
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

You are currently bisecting, started from branch 'main'.
  (use "git bisect reset" to get back to the original branch)

nothing to commit, working tree clean
```
### Resolving Merge Conflicts with a Merge Tool:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "changed test2"
[main 2c987c7] changed test2
 1 file changed, 4 insertions(+), 4 deletions(-)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git pull
Already up to date.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 970 bytes | 57.00 KiB/s, done.
From https://github.com/Seacrs/Git-Exercises
   5ea5def..89b30b0  main       -> origin/main
Auto-merging test2.md
CONFLICT (content): Merge conflict in test2.md
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git mergetool
Merging:
test2.md

Normal merge conflict for 'test2.md':
  {local}: modified file
  {remote}: modified file
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   test2.md

PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "merged conflicts"
[main 01e05a3] merged conflicts
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git push -u origin main
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 569 bytes | 569.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To https://github.com/Seacrs/Git-Exercises
   89b30b0..01e05a3  main -> main
branch 'main' set up to track 'origin/main'.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status            
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout ft/branch
Switched to branch 'ft/branch'
Your branch is up to date with 'origin/ft/branch'.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "changes made on test2"
[ft/branch 6437065] changes made on test2
 1 file changed, 1 insertion(+)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch ft/branch
Your branch is ahead of 'origin/ft/branch' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git merge ft/branch
Auto-merging test2.md
CONFLICT (content): Merge conflict in test2.md
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   test2.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --merge --oneline
6437065 (ft/branch) changes made on test2
01e05a3 (HEAD -> main, origin/main, origin/HEAD) merged conflicts
89b30b0 Update test2.md
2c987c7 changed test2
5ea5def Update test2.md
4272728 (origin/ft/branch) different test2
3dddef2 changed test2
3e91bd2 Made changes to test2
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git mergetool
Merging:
test2.md

Normal merge conflict for 'test2.md':
  {local}: modified file
  {remote}: modified file
warning: in the working copy of 'test2.md', LF will be replaced by CRLF the next time Git touches it
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "fixed conflict with ft/branch"
[main c4c9075] fixed conflict with ft/branch
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
### Understanding Detached HEAD State:
```bash
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
dd8d152 (HEAD -> main, origin/main, origin/HEAD) fixed using vim
857ab66 (ft/branch) Mirror
d601d66 new commit
9399d18 made changes to test4
c4c9075 fixed conflict with ft/branch
6437065 changes made on test2
01e05a3 merged conflicts
89b30b0 Update test2.md
2c987c7 changed test2
5ea5def Update test2.md
4272728 (origin/ft/branch) different test2
3dddef2 changed test2
3e91bd2 Made changes to test2
e455a24 Merge fix
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "Created index"
[main 8dc7043] Created index
 1 file changed, 14 insertions(+)
 create mode 100644 index.html
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
8dc7043 (HEAD -> main) Created index
dd8d152 (origin/main, origin/HEAD) fixed using vim
857ab66 (ft/branch) Mirror
d601d66 new commit
9399d18 made changes to test4
c4c9075 fixed conflict with ft/branch
6437065 changes made on test2
01e05a3 merged conflicts
89b30b0 Update test2.md
2c987c7 changed test2
5ea5def Update test2.md
4272728 (origin/ft/branch) different test2
3dddef2 changed test2
3e91bd2 Made changes to test2
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout dd8d152
Note: switching to 'dd8d152'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at dd8d152 fixed using vim
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git add -A
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git commit -m "made changes to index"
[detached HEAD dcdb8fe] made changes to index
 1 file changed, 25 insertions(+)
 create mode 100644 index.html
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
dcdb8fe (HEAD) made changes to index
dd8d152 (origin/main, origin/HEAD) fixed using vim
857ab66 (ft/branch) Mirror
d601d66 new commit
9399d18 made changes to test4
c4c9075 fixed conflict with ft/branch
6437065 changes made on test2
01e05a3 merged conflicts
89b30b0 Update test2.md
2c987c7 changed test2
5ea5def Update test2.md
4272728 (origin/ft/branch) different test2
3dddef2 changed test2
3e91bd2 Made changes to test2
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  dcdb8fe made changes to index

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> dcdb8fe

Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git log --oneline
8dc7043 (HEAD -> main) Created index
dd8d152 (origin/main, origin/HEAD) fixed using vim
857ab66 (ft/branch) Mirror
d601d66 new commit
9399d18 made changes to test4
c4c9075 fixed conflict with ft/branch
6437065 changes made on test2
01e05a3 merged conflicts
89b30b0 Update test2.md
2c987c7 changed test2
5ea5def Update test2.md
4272728 (origin/ft/branch) different test2
3dddef2 changed test2
3e91bd2 Made changes to test2
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git reflog --oneling
fatal: unrecognized argument: --oneling
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git reflog --oneline
8dc7043 (HEAD -> main) HEAD@{0}: checkout: moving from dcdb8fe97d2c039bcfcfab15b04a8b76b03a141e to main
dcdb8fe HEAD@{1}: commit: made changes to index
dd8d152 (origin/main, origin/HEAD) HEAD@{2}: checkout: moving from main to dd8d152
8dc7043 (HEAD -> main) HEAD@{3}: commit: Created index
dd8d152 (origin/main, origin/HEAD) HEAD@{4}: commit (merge): fixed using vim
d601d66 HEAD@{5}: checkout: moving from ft/branch to main
857ab66 (ft/branch) HEAD@{6}: commit: Mirror
9399d18 HEAD@{7}: checkout: moving from main to ft/branch
d601d66 HEAD@{8}: commit: new commit
c4c9075 HEAD@{9}: checkout: moving from ft/branch to main
9399d18 HEAD@{10}: checkout: moving from main to ft/branch
c4c9075 HEAD@{11}: reset: moving to c4c9075
6437065 HEAD@{12}: reset: moving to 6437065
9399d18 HEAD@{13}: reset: moving to 9399d18
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout dcdb8fe
Note: switching to 'dcdb8fe'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at dcdb8fe made changes to index
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout - b ft/index
error: pathspec 'b' did not match any file(s) known to git
error: pathspec 'ft/index' did not match any file(s) known to git
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git branch ft/index      
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout ft/index
Switched to branch 'ft/index'
PS C:\Users\freez\OneDrive\Desktop\Exercise\Git-Exercises> git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
```
### Ignoring Files/Directories:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ touch .gitignore

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git add -A

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git commit -m "Created .gitignore file"
[main baa9890] Created .gitignore file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .gitignore

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git add -A

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git commit -m "/tmp to be ignored"
[main 5c34768] C:/Program Files/Git/tmp to be ignored
 1 file changed, 1 insertion(+)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git add -A

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git commit -m "Added: secret txt to .gitignore"
[main bf1aa1b] Added: secret txt to .gitignore
 1 file changed, 2 insertions(+), 1 deletion(-)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git push -u origin main
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 8 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (14/14), 1.59 KiB | 812.00 KiB/s, done.
Total 14 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (5/5), completed with 1 local object.
To https://github.com/Seacrs/Git-Exercises
   dd8d152..bf1aa1b  main -> main
branch 'main' set up to track 'origin/main'.

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

```
### Working with Tags:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git log --oneline
bf1aa1b (HEAD -> main, origin/main, origin/HEAD) Added: secret txt to .gitignore
5c34768 C:/Program Files/Git/tmp to be ignored
baa9890 Created .gitignore file
58114d4 (ft/index) changed position of ft/index
8dc7043 Created index
dd8d152 fixed using vim
857ab66 (ft/branch) Mirror
d601d66 new commit
9399d18 made changes to test4
c4c9075 fixed conflict with ft/branch
6437065 changes made on test2
01e05a3 merged conflicts
89b30b0 Update test2.md
2c987c7 changed test2
5ea5def Update test2.md
4272728 (origin/ft/branch) different test2
3dddef2 changed test2
3e91bd2 Made changes to test2
e455a24 Merge fix
f0d22a4 (ft/new-feature) Additional changes
cca32b9 Added changes
81e6dee merge fix
afdc4a5 new features added

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git tag -a v1.0 bf1aa1b -m "Release version 1.0.0"

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git tag -l
v1.0
```
### Listing and Deleting Tags:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git tag -l
v1.0

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git tag -d v1.0
Deleted tag 'v1.0' (was 99ab76f)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git tag -l
```
### Pushing Local Work to Remote Repositories:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git push -u origin main
branch 'main' set up to track 'origin/main'.
Everything up-to-date

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git branch
  ft/branch
  ft/improved-branch-name
  ft/index
  ft/new-feature
* main

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git checkout ft/branch
Switched to branch 'ft/branch'
Your branch is ahead of 'origin/ft/branch' by 3 commits.
  (use "git push" to publish your local commits)

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/branch)
$ git push -u origin ft/branch
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Seacrs/Git-Exercises
   4272728..857ab66  ft/branch -> ft/branch
branch 'ft/branch' set up to track 'origin/ft/branch'.

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/branch)
$ git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/improved-branch-name)
$ git push -u origin ft/improved-branch-name
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 499 bytes | 166.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/improved-branch-name' on GitHub by visiting:
remote:      https://github.com/Seacrs/Git-Exercises/pull/new/ft/improved-branch-name
remote:
To https://github.com/Seacrs/Git-Exercises
 * [new branch]      ft/improved-branch-name -> ft/improved-branch-name
branch 'ft/improved-branch-name' set up to track 'origin/ft/improved-branch-name'.

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (ft/improved-branch-name)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$

```
### Pulling Changes from Remote Repositories:
```bash
freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git init
Reinitialized existing Git repository in C:/Users/freez/OneDrive/Desktop/Exercise/Git-Exercises/.git/

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git pull origin main
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 1.00 KiB | 48.00 KiB/s, done.
From https://github.com/Seacrs/Git-Exercises
 * branch            main       -> FETCH_HEAD
   cac2f50..0f78f74  main       -> origin/main
CONFLICT (modify/delete): readme.txt deleted in 0f78f749d7c577836babce61cd71c79d77b054e2 and modified in HEAD.  Version HEAD of readme.txt left in tree.
Automatic merge failed; fix conflicts and then commit the result.

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main|MERGING)
$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
        new file:   readme.md

Unmerged paths:
  (use "git add/rm <file>..." as appropriate to mark resolution)
        deleted by them: readme.txt

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main|MERGING)
$ git rm readme.txt
rm 'readme.txt'

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main|MERGING)
$ git commit -m "Fixed conflicts"
[main a05b09e] Fixed conflicts

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git push origin main
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 465 bytes | 465.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Seacrs/Git-Exercises
   0f78f74..a05b09e  main -> main

freez@FREEZ MINGW64 ~/onedrive/desktop/Exercise/Git-Exercises (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
