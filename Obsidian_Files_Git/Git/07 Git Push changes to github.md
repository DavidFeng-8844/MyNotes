![[Pasted image 20231018224932.png]]
Add the remote repository URL to your local Git repository:
```bash
git remote add origin <remote_repository_url>
```
Push your local changes to the remote repository:
```bash
git push -u origin master

```
The `-u` option is used to set the upstream branch, so in the future, you can simply use `git push` without specifying the remote and branch.