---
date: 2024-11-13 18:56
sources: 
tags:
  - zettel
  - software-dev
status: literature
publish: true
---
# restore files from previous commit

If you want to restore files from a previous commit to rewind back the changes, you can follow these steps:

#### Step-1: Identify the commit 
```bash
git log
```

#### Step-2: Checkout that commit
```bash
git checkout <commit-hash>
```

#### Step-3: Create a new branch from this commit
```bash
git checkout -b temp-branch
```

#### Step-4: Checkout into `main` branch
```bash
git checkout main 
```

#### Step-5: Restore files from `temp-branch`
**If you want to restore a specific file:**

```bash
git checkout temp-branch -- <path/to/file-or-directory>
```

**If you want to restore all files:**

```bash
git checkout temp-branch -- .
```

Follow the usual stuff of adding the changes and then committing the changes.  

---
## Related Notes

## References(links)
[I have git repo where I did some changes and it abruptly deleted all my files...](https://www.perplexity.ai/search/i-have-git-repo-where-i-did-so-S6SKP1j5QMKesybcgT70YQ)