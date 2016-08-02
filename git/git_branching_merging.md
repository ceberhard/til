## Git (github) Branching and Merging
To create a new branch from an existing one:
```bash
git checkout -b new-branch
```
*Slashes are acceptable in branch names, and actually create url paths in github*

To publish the new branch to github:
```bash
git push origin new-branch
```

To see branches within your local git repository:
```bash
git branch
```
*The active branch will have any asterik(*) next to it*

To switch back to the original branch:
```bash
git checkout source-branch
```

To merge the branch into its source after switching back to the source branch:
```bash
git merge new-branch
```

To delete the branch once you are done:
```bash
git branch -d new-branch
```

### References:
https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging
https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches
http://stackoverflow.com/questions/5601931/best-and-safest-way-to-merge-a-git-branch-into-master
