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
