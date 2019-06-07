# **Git的优势**  
 1. 快速
 2. 分布式
 3. 重写历史

 # **关键概念** 
 1. 工作目录  
 2. 暂存区  
 3. 本地仓库
 4. 远程仓库 

 自动补全配置
 git-completion

配置帮助 
```
git help config 
```

 配置
 ```bash
 git config --global user.name "King"
 git config --global user.email "dreamingking@live.cn" 
 ```
 配置范围 
  1. --system 系统 适用系统上的任何用户 `/usr/[local]/etc/gitconfig`
  2. --global 全局 特定用户下的所有仓库 `~/.gitconfig`
  3. --local 本地 特定仓库 默认 可以不明确指定 `<rep dir>/.git/config`
  
  没有指定范围时配置读取顺序：local > global > system 

```
sudo git config --system core.autocrlf ture  
git config --system core.autocrlf 
cat /etc/gitconfig
```

查看配置   
```bash
git config --list  --local
git config user.name
```
配置
```bash
git config <settings>
```

一次性配置
```
git -c <setting>=<value><rest>
```

撤销配置
```
git config --unset [setting] [value]
```
查看配置来源
```
git config --show-origin user.name
git config --show-origin --list
```
配置模糊查找
```bash
git config --get-regexp user
```
配置默认编辑器
```bash
git config core.editor vim
```
设置行结束符
```bash
git config --global core.autocrlf=true
```
autocrlf值及其行为
1. true 文件入库时会自动使用LF作为行结束符，出库会自动使用CRLF作为行结束符。Windows用户推荐使用。
1. input 文件入库时会自动使用LF作为行结束符,出库不做修改。类Unix推荐使用。
1. false 签入或签出都不修改。不推荐使用
行结束符的控制最好写在`.gitattributes`文件中并提交到仓库中 

# 别名
语法： git config [scope] alias.<name> [command string]
```
git config alias.l 'log --pretty=format:"%h %ad | %s %d" --date=short'
```

命令用法
git [git-option] <command> [command-option] [operands]

`--`区分提交|分支|标签与一个或多个文件或路径可能出现混淆 

`.git`目录下的文件 
+ HEAD 持续追踪当前所在分支 
+ description GitWeb仓库浏览器使用
+ config 本地仓库配置文件 
+ object/pack 实际存储区域 

写配置文件  
```bash
git config --file test.config remote.mytest.test https://git-scm.com/book/zh/v2
```

高级命令：面向普通用户,更便利。
底层命令：更为直接地从仓库中提取或修改内容和信息。

高级命令
| 命令 | 作用 |
|:----:|:----|
| add | 添加文件内容到索引 |
| bisect | 二分查找 |
| branch | 分支管理 |
| chechout | 分支切换 |
| cherry | 找出有待应用的上游提交 |
| cherry-pick | 应用已有提交 |
| clone | 复制项目 |
| commit | 确认变更到仓库 |
| config | 仓库或全局配置 |
| diff | 显示提交或工作树变更之间的差异 |
| fetch | 拉取仓库 |
| grep | 输出匹配的模式 |
| help | 获取帮助信息 |
| log | 查看提交日志信息 |
| merge | 变更合并 |
| mv | 移动或重命名文件、目录或符号链接 |
| pull | 分支拉取并合并 |
| push | 更新远程引用及相关对象 |
| rebase | 将本地提交转发到更新的上游头信息 |
| rerere | 将所记录的解决内容重用于合并的冲突 |
| revert | 还原一些已有提交 |
| rm | 删除文件 |
| show | 显示各种类型的对象 |
| status | 显示各种类型的状态 |
| submodule | 初始化、更新和检查子模块 |
| subtree | 合并子树 |
| worktree | 工作树管理 |
| init | 初始化仓库 |

底层命令 
| 命令 | 作用 |
|:----:|:----|
| cat-file | 提供仓库对象的内容或类型和大小信息 |
| commit-tree | 创建一个新的提交对象 |
| count-objects | 统计松散对象的数量和磁盘消耗|
| diff-index | 将树与工作树或索引进行对比 |
| for-each-ref | 输出每个引用上的信息 |
| hash-object | 计算对象id |
| ls-files | 显示与索引和工作树有关的文件信息 |
| merge-base | 为合并找到尽可能通用的源 |
| read-tree | 将信息读取到索引中 |
| rev-list | 时间倒序列出对象 |
| rev-parse | 选取并且修饰参数 |
| show-ref | 列出本地仓库的引用 |
| symbolic-ref | 读取、修改和删除符号引用 |
| update-index | 将工作树中的内容更新到索引 |
| update-ref | 更新被安全存储在引用中对象的名称 |
| verify-pack | 验证打包好的git归档文件 |
| write-tree | 从当前索引中创建对象 |

自动补全 git-competion.bash 
```
https://github.com/git/git/blob/master/contrib/completion/git-completion.zsh
```
[在Mac下安装bash-completion](https://www.jianshu.com/p/9964ec6717c8)

Window下的自动补全提示工具[`Clink`](http://mridgers.github.io/clink/)

帮助信息 
简短版  
```
git command -h
``` 
详细版
```
git command --help
git help command
```
查看帮助指南
```
git help -g
```
查看术语表 
```
git help glossary
```

指定帮助信息显示格式
```
git config --global help.format.man
```

多仓库模型

追踪、暂存和添加

要追踪首先要暂存，暂存区的目的之一就是允许构建一组完整的内容以便作为一个单元提交到本地仓库中。



 
 