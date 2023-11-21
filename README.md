# CaptainHook Examples

Repository with lots of example branches to demo the CaptainHook functionality. Clone the repository and then activate the
Captain.

```
$ git clone git@github.com:captainhook-go/examples.git & cd examples
$ captainhook install -f
```


- [git-notify notifications](#git-notify-functionality)
- [inject issue key from branch](#inject-issue-key-from-branch)
- [block fixup and squash commits](#block-fixup-and-squash-commit-from-being-pushed)


## git-notify functionality
Checkout the first branch.
```
$ git switch action/git-notify-checkout-first
```
If you update your working directory with `merge`, `rebase`, `checkout` and any commit contains `git-notify:` followed by a message the message will be displayed.
```
$ git switch action/git-notify-checkout-second
```

## inject issue key from branch

Checkout the demo branch.
```
$ git switch action/inject-key-from-branch-PROJ-12345
```
Add a new file, and commit it to the repository
```
$ touch demo
$ git add demo
$ git commit
```
Your editor should already contain the `PROJ-12345` issue key extracted from the branch name.

## block fixup! and squash! commit from being pushed

Start by checking out the starting branch.
```
$ git switch action/prevent-push-fixup+squash
```
Merge a prepared fixup! commit.
```
$ git merge action/prevent-push-fixup+squash-fix
```
If you try to push the changes the push should fail.
```
$ git push
```


