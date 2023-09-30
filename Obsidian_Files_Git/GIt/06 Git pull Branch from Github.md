

# Use the fetch or pull to pull the changes 



![[Pasted image 20230929104440.png]]

So, we do not have the new `branch` on our local Git. But we know it is available on GitHub. So we can use the `-a` option to see all local and remote branches:

### Example

```shell
git branch -a
* master
  remotes/origin/html-skeleton
  remotes/origin/master
```

**Note:** `branch -r` is for remote branches only.
