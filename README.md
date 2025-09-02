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

```
