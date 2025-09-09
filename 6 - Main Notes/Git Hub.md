
2025-09-09 23:20

Status: #1/10

Tags: [[Learning]] 

# Git Hub

## How to work independently

**1 Make a new branch**
``` git checkout -b feature/dialog-baselines```
**2 Work on my changes**
``` 
git add baselines.py utils.py main.py
git commit -m "Implement majority and rule-based baselines with preprocessing"

 ```
**3** **Push the branch (optional, if you want remote backup) **
```git push origin feature/dialog-baselines```

**4 Merge**
```
git checkout main
git pull origin main
git merge feature/dialog-baselines
```
**5 Clean up (Optional)**
```
git branch -d feature/dialog-baselines # local branch
git push origin --delete feature/dialog-beaselines # remote branch
```

## Reference

[github tutorial](https://www.atlassian.com/git/tutorials/advanced-overview)