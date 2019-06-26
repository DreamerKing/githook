1. 添加子树
```
git subtree add --prefix project_name repositry_url branch_name 
```

1. 更新子树
   ```
   git subtree pull --prefix project_name repositry_url branch_name --squash
   git subtree merge --prefix project_name repositry_url branch_name --squash
   ```
1. 分离子树
   ```
   git subtree split --prefix=project_name --branch=branch_name
   ```
1. 子树推送
   ```
   git subtree push --prefix=project_name origin branch_name
   ```