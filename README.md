# Git Patch This Branch

## Overview
Creating and applying patches allows you to share changes between branches or with collaborators without merging.

## Creating a Patch

### From Current Branch
```bash
git diff > changes.patch
```

### Specific Commits
```bash
git format-patch -1 HEAD
git format-patch -2 HEAD  # Last 2 commits
```

### Against Another Branch
```bash
git diff main..feature > changes.patch
```

### Between Two Commits
```bash
git diff commit1 commit2 > changes.patch
```

## Applying a Patch

### Apply Patch
```bash
git apply changes.patch
```

### Apply with Format Patch
```bash
git am changes.patch
```

### Dry Run (Preview)
```bash
git apply --check changes.patch
```

## Common Options

| Option | Description |
|--------|-------------|
| `--stat` | Show statistics of changes |
| `--reverse` | Reverse the patch |
| `--reject` | Create `.rej` files for conflicts |
| `-p <n>` | Strip n leading path components |

## Tips
- Use `git format-patch` for commit-based patches with metadata
- Use `git diff` for simple file changes
- Check patches with `--check` before applying
- Use `git am` to preserve commit history
