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
