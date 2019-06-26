在当前仓库中包含其他一个或多个依赖仓库。
1. 添加子模块
   ```
   git submodule add <repostry> module_name
   ```
在`.gitmodules`文件中会记录子模块的信息

1. 查看子模块状态
   ```
   git submodule status
   ```
   子模块信息路径：`.git/modules`
1. 初始化子模块 
   ```
   git submodule init
   ```
1. 更新子模块
   ```
   git submodule update
   ```
简化以上步骤的命令
```
git submodule update --init
```
```
git clone --recursive|recursive-submodule repositry
```

处理多个子模块
```
git submodule foreach git log --oneline
```
可用的几个变量
+ $name 子模块名称
+ $path 子模块路径
+ $sha1 超级项目中子模块的sha1值
+ $toplevel 到超级目录的绝对路径

1. 更新子模块
```
git pull --recurse-submodules
```
```
git submodule update --remote 
git submodule update --remote  submodule_name
```
```
git submodule foreach git pull origin master
```
```
git submodule update
```

查看子模块差异
```
git diff 
git diff --submodule
```
推送来自子模块的变更
```
git push --recurse-submodules=check|on-demand
```

带子模块的超级项目的合并提交流程：
1. 切换到子模块合并
2. 切换到超级项目
3. 验证子模块更新的值是否符合超级项目的引用
4. 暂存(添加)更新后的子模块引用
5. 进行提交，完成合并

注销子模块
```
git submodule deinit submodule_name
```