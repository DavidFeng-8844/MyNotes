# Use fetch to  gets all the change history of a tracked branch/repo.
![[Pasted image 20230929093238.png]]


![[Pasted image 20230929100334.png]]



![[Pasted image 20230929100313.png]]

# Or you can simply write 

git pull origin 
(which is a combination of fetch and merge )



***
# Keep Local Branch updated

```git 
git fetch --prune
```

Use the `git fetch --prune` command to fetch the latest changes from the remote and prune (remove) references to remote branches that no longer exist on the remote: