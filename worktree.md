工作树：可以使用多个单独的工作目录，所有的这些目录都使用相同的暂存区和本地仓库。
主工作树
链接工作树
1. 创建工作树
   ```
   git worktree add [--force] <path> [<branch>]
   git worktree add -b|B new_branch <path> [<branch>]
   ```
   --detach 分离模式创建工作树

工作树信息存储路径：.git/worktree

1. 列出工作树
   ```
   git worktree list [--forceplain]
   ```
3. 精简工作树
    ```
    git worktree prune
    ```
   + -n(--dry-num) 告知不执行
   + -v(--verbose) 显示执行信息
4. 锁定工作区
   ```
   git worktree lock tree_name
   ```