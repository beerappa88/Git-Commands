# Git & GitHub Commands Cheat Sheet

## 1. Basic Commands
```bash
git init                          # Initialize new repository
git clone <url>                   # Clone remote repository
git add <file>                    # Stage specific file
git add .                         # Stage all changes
git commit -m "message"           # Commit staged changes
git status                        # Show working directory status
git push                          # Push commits to remote
git pull                          # Fetch and merge remote changes
git log                           # View commit history
```

## 2. First-Time Setup (Local → GitHub)
```bash
git init
echo "# Project" > README.md      # Create README
git add .
git commit -m "Initial commit"
git remote add origin <url>       # Link to GitHub repo
git branch -M main                # Rename branch to main
git pull --allow-unrelated-histories origin main  # Sync if GitHub has content
# (Resolve merge commit if prompted)
git push -u origin main           # Push and set upstream
```

## 3. Remote Repository Management
```bash
git remote -v                     # List remotes with URLs
git remote add <name> <url>       # Add new remote
git remote remove <name>          # Remove remote
git remote rename <old> <new>     # Rename remote
git fetch <remote>                # Download changes without merging
```

## 4. Branching
```bash
git branch                        # List branches
git branch <name>                 # Create new branch
git checkout <name>               # Switch branch
git checkout -b <name>            # Create & switch branch
git switch <name>                 # Modern branch switch (Git 2.23+)
git switch -c <name>              # Modern create & switch
git merge <name>                  # Merge branch into current
git branch -d <name>              # Delete merged branch
git branch -D <name>              # Force delete unmerged branch
```

## 5. Undoing Changes
```bash
git checkout -- <file>            # Discard unstaged file changes
git reset HEAD <file>             # Unstage file (keep changes)
git reset --hard HEAD             # Discard all uncommitted changes
git reset --hard HEAD~1           # Delete last commit (permanent!)
git revert <commit>               # Create new commit to undo changes
```
## 6. Stashing Changes
```bash
git stash                         # Temporarily save changes
git stash list                    # List all stashes
git stash apply                   # Apply most recent stash
git stash pop                     # Apply & remove most recent stash
git stash drop                    # Remove most recent stash
git stash clear                   # Remove all stashes
```

## 7. Viewing Differences
```bash
git diff                          # Show unstaged changes
git diff --staged                 # Show staged changes
git diff <branch1> <branch2>      # Compare branches
git show <commit>                 # Show commit details
git log --oneline                 # Compact commit history
git log --graph                   # Visualize branch history
```

## 8. Configuration
```bash
git config --global user.name "Name"    # Set username
git config --global user.email "email"  # Set email
git config --list                  # View all settings
git config --global core.editor vim    # Set default editor
git config --global init.defaultBranch main  # Set default branch name
```

## 9. Ignoring Files
```bash
echo "node_modules/" >> .gitignore  # Add directory to ignore
echo "*.log" >> .gitignore          # Add file pattern to ignore
git rm -r --cached <file>           # Stop tracking (keep local file)
```

## 10. Rebasing
```bash
git rebase <branch>                # Reapply current branch on another
git rebase -i HEAD~3               # Interactive rebase (last 3 commits)
git rebase --continue              # Continue after resolving conflicts
git rebase --abort                 # Cancel rebase
```

## 11. Merge Conflicts
```bash
git status                        # Identify conflicted files
# Manually edit conflicted files
git add <resolved-file>            # Mark as resolved
git commit                        # Complete merge
# (For rebase conflicts: use `git rebase --continue`)
```

## 12. Tagging
```bash
git tag                           # List all tags
git tag <name>                    # Create lightweight tag
git tag -a <name> -m "msg"        # Create annotated tag
git push origin <tag>             # Push specific tag
git push origin --tags            # Push all tags
git tag -d <name>                 # Delete local tag
git push origin :refs/tags/<name> # Delete remote tag
```

## 13. Collaboration
```bash
git checkout -b <branch> origin/<branch>  # Create local from remote
git request-pull                   # Generate pull request summary
git format-patch                   # Create email patches
```

## 14. Cleanup
```bash
git clean -n                      # Preview untracked files to remove
git clean -f                      # Remove untracked files
git clean -fd                     # Remove untracked files/directories
git gc                            # Optimize repository
```

## 15. Advanced Log Options
```bash
git log --author="name"           # Filter by author
git log --since="2023-01-01"      # Commits since date
git log --until="2023-12-31"      # Commits until date
git log --grep="keyword"          # Search commit messages
```
