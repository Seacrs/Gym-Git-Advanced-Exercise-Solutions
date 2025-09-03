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

```
