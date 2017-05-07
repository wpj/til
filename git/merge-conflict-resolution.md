# Resolving merge conflicts

## Choosing `ours` or `theirs`

When resolving a merge conflict, you can run `git checkout --ours` or `git
checkout --theirs` to choose the side of a merge conflict to use.

You can also use the `-Xours` or `-Xtheirs` flags when merging to automatically
choose `ours` vs `theirs` when merge conflicts occur.

## Merge log

To get a list of commits from either branch involved in a conflicting merge:

```sh
git log --oneline --left-right HEAD...MERGE_HEAD
# < f1270f7 update README
# < 9af9d3b add a README
# < 694971d update phrase to hola world
# > e3eb223 add more tests
# > 7cff591 add testing script
# > c3ffff1 changed text to hello mundo
```

To show a list of commits on either side that involve a file that's conflicted:

```
git log --oneline -left-right --merge
```
