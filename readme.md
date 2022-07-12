# Git rebase and rewriting git history

## Rebase vs Merge

### Merge

![MarineGEO circle logo](/02%20Merging%20main%20into%20the%20feature%20branh.svg)

---

### Rebase

![MarineGEO circle logo](/03%20Rebasing%20the%20feature%20branch%20into%20main.svg)

---

## Advantages of rebasing

- Creates a cleaner git history. Avoid all those “Merged main into {{branch-name}}” commits.
- Allows you to make changes to your commit history as you pull in new changes. `git rebase -i {{branch-name}}`

## Disadvantages of rebasing

- If multiple people are working on the same branch it is usually not the optimal solution.
- It can be a little more complex than merging

## Interactive rebase

`git rebase -i {{branch-name}}`

You can pick, squash, edit, or drop commits

- Pick: Selects a commit to be included
- Squash: Squashes a commit, combining it with another
- Edit: Allows you to change a commit
- Drop: Will not select that commit to be included.

Once action is selected for the commits you can take the selected actions to each one and progress through them with `git rebase --continue`

## Recovering from problems with a rebase

- You can run `git rebase --abort` at any time during a rebase to transition your work into the state it was right before you ran the rebase command.
- You can run `git reflog` to recover from more serious problems. If you can find the here HEAD was at right before you ran a command that you want to recover from you can generally checkout or rebase onto this HEAD to recover your work.

## Work in progress commits

You can use a soft reset to undo your last commit
`git reset --soft HEAD~1`

This allows you to make work in progress commits when you want to make sure you don't lose work. (Ex. Checking out a branch for a PR review, breaking for lunch, stopping for the day, etc.)

You can then un-stage the committed files and continue working as normal.

## Additional Resources

- [Oh Shit Git](https://ohshitgit.com/)
- [Git Visualizations](https://dev.to/lydiahallie/cs-visualized-useful-git-commands-37p1)
- [Atomic Commits](https://www.freshconsulting.com/insights/blog/atomic-commits/)
- [Git Rebase Recipes](https://hotelengine.atlassian.net/wiki/spaces/DEVELOPMEN/pages/1307246593/Git+Rebase+Recipes)
- [Writing a Great Commit Message](https://hotelengine.atlassian.net/wiki/spaces/DEVELOPMEN/pages/1308065814/Write+A+Great+Commit+Message)
