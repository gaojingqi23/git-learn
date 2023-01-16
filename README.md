# git-learn

git 和 github 学习用

## Git 学习进度

- [Git Book](https://git-scm.com/book/zh/v2)
- [3.6 Git 分支 - 变基](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%8F%98%E5%9F%BA)
- [ ] [10.7 git 内部原理 - 维护与数据恢复](https://git-scm.com/book/zh/v2/Git-%E5%86%85%E9%83%A8%E5%8E%9F%E7%90%86-%E7%BB%B4%E6%8A%A4%E4%B8%8E%E6%95%B0%E6%8D%AE%E6%81%A2%E5%A4%8D#_data_recovery)
- [ ] [7.7 git 工具 - 重置揭密](https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E9%87%8D%E7%BD%AE%E6%8F%AD%E5%AF%86#_git_reset)
- [x] [7.3 git 工具 - 贮藏与清理](https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E8%B4%AE%E8%97%8F%E4%B8%8E%E6%B8%85%E7%90%86)
- [ ] [Git - 子模块](https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E5%AD%90%E6%A8%A1%E5%9D%97)

## Git 常用命令

### 基础

- 列出所有 Git 当时能找到的配置：git config --list
- 查看所有的配置以及它们所在的文件：git config --list --show-origin
- 全局配置：git config --global ...
- 查看文件状态：git status
- 简短查看文件状态：git status -s / git status --short
- 查看尚未暂存的文件更新了哪些部分：git diff
- 查看已暂存的将要添加到下次提交里的内容：git diff --staged / git diff --cached
- 采用默认编辑器提交：git commit / git commit -v
- 提交信息与命令放在同一行：git commit -m 'your information'
- 跳过 git add（暂存区）提交：git commit -a
- 从工作区删除文件移出跟踪目录：git rm filename
- 从暂存区删除文件但在工作区保留：git rm --cached filename
- 强制从暂存区和工作区删除文件：git rm -f filename
- 递归删除文件夹：git rm -r \<diectory>
- 移动或重命名文件：git mv src-filename dst-filename
- 查看提交历史：git log
- 显示每次提交所引入的差异（按补丁的格式输出）：git log -p/--patch
- 限制现实的日志条目数量 number：git log -p/--patch -number
- 查看每次提交的简略统计信息：git log --stat
- 将每个提交简短显示：git log --pretty=oneline/short/full/fuller
- 定制提交记录的显示格式：git log --pretty=format:"%h - %an, %ar : %s"
- git log --pretty=format 常用的选项

  | 选项 | 说明                                          |
  | ---- | --------------------------------------------- |
  | %H   | 提交的完整哈希值                              |
  | %h   | 提交的简写哈希值                              |
  | %T   | 树的完整哈希值                                |
  | %t   | 树的简写哈希值                                |
  | %P   | 父提交的完整哈希值                            |
  | %p   | 父提交的简写哈希值                            |
  | %an  | 作者名字                                      |
  | %ae  | 作者的电子邮件地址                            |
  | %ad  | 作者修订日期（可以用 --date=选项 来定制格式） |
  | %ar  | 作者修订日期，按多久以前的方式显示            |
  | %cn  | 提交者的名字                                  |
  | %ce  | 提交者的电子邮件地址                          |
  | %cd  | 提交日期                                      |
  | %cr  | 提交日期（距今多长时间）                      |
  | %s   | 提交说明                                      |

- 形象地展示你的分支、合并历史:git log --pretty=oneline --graph
- **git log 的常用选项**

| 选项            | 说明                                                                                                      |
| --------------- | --------------------------------------------------------------------------------------------------------- |
| -p              | 按补丁格式显示每个提交引入的差异                                                                          |
| --stat          | 显示每次提交的文件修改统计信息                                                                            |
| --shortstat     | 只显示 --stat 中最后的行数修改添加移除统计                                                                |
| --name-only     | 仅在提交信息后显示已修改的文件清单                                                                        |
| --name-status   | 显示新增、修改、删除的文件清单                                                                            |
| --abbrev-commit | 仅显示 SHA-1 校验和所有 40 个字符中的前几个字符                                                           |
| --relative-date | 使用较短的相对时间而不是完整格式显示日期（比如“2 weeks ago”）                                             |
| --graph         | 在日志旁以 ASCII 图形显示分支与合并历史                                                                   |
| --pretty        | 使用其他格式显示历史提交信息, 可用的选项包括 oneline、short、full、fuller 和 format（用来定义自己的格式） |
| --oneline       | --pretty=oneline --abbrev-commit 合用的简写                                                               |

- 限制输出长度：git log -\<n>
- 按时间限制：git log --since/--untils
- 显示指定作者的提交：git log --author
- 搜索提交说明中的关键字：git log --grep
- 显示那些添加或删除了指定字符串的提交：git log -s <string>
- 指定路径（放在最后位置并用--隔开）：git log -- \<path>
- **限制 git log 输出的选项**

  | 选项             | 说明                                     |
  | ---------------- | ---------------------------------------- |
  | -\<n>            | 仅显示最近的 n 条提交                    |
  | --since,--after  | 仅显示指定时间之后的提交                 |
  | --until,--before | 仅显示指定时间之前的提交                 |
  | --author         | 仅显示作者匹配指定字符串的提交           |
  | --committer      | 仅显示提交者匹配指定字符串的提交         |
  | --grep           | 仅显示提交说明中包含指定字符串的提交     |
  | -S               | 仅显示添加或删除内容匹配指定字符串的提交 |

- 隐藏合并提交:git log --no-merges
- 重新提交并保留上次提交信息(用一个新的提交替换旧的提交)(非常好用)：**git commit --amend**
- 取消暂存的文件：git restore --staged \<file>...
- 撤销对文件的修改（用最近提交的版本覆盖掉它,**在 Git 中，已提交的东西总是可以恢复的**）：git restore \<file>...
- 查看远程仓库：git remote / git remote -v
- 详细查看远程仓库信息：git remote show \<remote-name>
- 添加远程仓库：git remote add \<shortname> \<url>
- 从远程仓库抓取上一次抓取后新推送的所有工作（不会自动合并）：git fetch \<remote>
- 从远程仓库抓取并自动合并到当前分支（前提是设置了跟踪远程分支）：git pull \<remote>
- 远程仓库重命名：git remote rename \<src-name> \<dst-name>
- 远程仓库移除：git remote remove \<name>

### 标签

- 列出标签：git tag
- （按通配符）查找标签：git tag -l/--list \<通配符>
- 创建附注标签（annotated）：git tag -a \<tagname> -m \<tag description>
- 查看标签信息和与之对应的提交信息：git show \<tagname>
- 轻量标签（lightweight）：git tag \<tagname>
- 给某个 commit 打标签：git tag -a \<tagname> \<commit id>
- 共享标签（推送标签到远程服务器上）：git push \<remote> \<tagname>
- 一次性推送多个标签：git push \<remote> --tags
- 本地删除标签：git tag -d \<tagname>
- 远程移除标签：git push \<remote> --delete <tagname> / git push \<remote> :refs/tags/\<tagname>
- 查看某个标签所指向的文件版本(会使你的仓库处于“分离头指针（detached HEAD）”的状态——这个状态有些不好的副作用)：git check \<tagname>
- **Git 别名例子**

  | 命令                                                                                              | 备注     |
  | ------------------------------------------------------------------------------------------------- | -------- |
  | git config --global alias.co checkout                                                             |          |
  | git config --global alias.br branch                                                               |          |
  | git config --global alias.ci commit                                                               |          |
  | git config --global alias.st status                                                               |          |
  | git config --global alias.unstage 'reset HEAD --'                                                 |          |
  | git config --global alias.last 'log -1 HEAD'                                                      |          |
  | git config --global alias.visual '!gitk'                                                          | 可视化   |
  | git config --global alias.lg "log --pretty=format:'%Cred%h%Creset - %s %Cgreen(%ar) %Cblue<%an>'" | 实用 log |

### 分支

#### 本地分支

- 创建一个本地分支：git branch \<brance-name>
- 查看各个分支当前所指的对象：git log --oneline --decorate
- 切换分支：git checkout \<branch-name>
- 创建并切换至新分支：git checkout -b \<newbranchname>
- 删除分支：git branch -d \<branch-name>
- 强制删除分支：git branch -D \<branch-name>
- 合并分支：git merge \<branch-name>
- 查看分叉历史：git log --oneline --decorate --graph --all
- 图形化工具解决合并冲突：git mergetool
- 将冲突标记为已解决：git add
- 解决合并冲突后完成合并提交：git commit
- 查看当前所有分支：git branch
- 查看每一个分支的最后一次提交：git branch -v
- 查看哪些分支已经合并到当前分支：git branch --merged /<branch-name>(默认当前分支)
- 查看所有包含未合并工作的分支：git branch --no-merged /<branch-name>(默认当前分支)
- 将分支 b1 的修改变基到 b2 上（首先切换到 b1 分支）：git rebase b2
- 取出 b2 基于 b1 的修改编辑在 master 上(当前在 b1)：git rebase --onto master b1 b2

#### 远程分支

- 获得远程引用的完整列表：git ls-remote \<remote>
- 获得远程分支的更多信息：it remote show \<remote>
- 修改（默认 origin） git clone 时默认的远程仓库名字：git clone -o \<newname>
- 与给定的远程仓库同步数据：git fetch \<remote>
- 推送本地分支至远程仓库的分支：git push \<remote> \<branch> / git push \<remote> \<localbranch>:<remotebranch>
- 合并远程分支到当前所在的分支：git merge \<remote>/\<branch>
- 建立本地分支并跟踪远程分支：git checkout -b \<localbranch> \<remote>/\<branch>
- 设置跟踪分支：git checkout --track \<remote>/\<branch>
- 设置/修改已有的本地分支跟踪一个刚刚拉取下来的远程分支：git branch -u/--set-upstream-to \<remote>/\<branch>
- 上游快捷方式：@{upstream}/@{u}
- 列出所有本地分支并包含更多的信息：git branch -vv
- 抓取所有的远程仓库：git fetch --all
- 拉取并合并：git pull \<remote>/\<branch>(相当于 git fetch;git merge)
- 删除远程分支：git push \<remote> --delete \<branch>

### 贮藏与清理

- 处理工作目录的脏的状态(贮藏（stash）,即跟踪文件的修改与暂存的改动,然后将未完成的修改保存到一个栈上)：**git stash / git stash push**
- 查看贮藏的东西: git stash list
- 应用贮藏的工作: git stash apply （不指定一个贮藏，Git 认为指定的是最近的贮藏）
- 尝试重新应用暂存的修改：git stash apply --index
- 应用贮藏然后立即从栈上扔掉它：**git stash pop**
- 移除贮藏：git stash drop \<stashname>
- 贮藏任何未跟踪文件(git stash 只会贮藏已修改和暂存的 已跟踪 文件): git stash -u/--include-untracked
- 额外包含忽略的文件: git stash -a/--all
- 交互式地提示哪些改动想要贮藏、哪些改动需要保存在工作目录中: git stash --patch
- 从贮藏创建一个分支: git stash branch \<new branchname>
- 从工作目录中移除未被追踪的文件: **git clean**
- 移除工作目录中所有未追踪的文件以及空的子目录: git clean -f -d
- 仅提示将要移除什么: git clean -n/--dry-run
- 移除包含在.gitignore 的忽略文件：git clean -x
- 交互式移除：git clean -i/interactive
- (多次)强调移除：git clean -f -f
- 安全移除（移除每一样东西并存放在栈中）：git stash --all

### 子模块


## Git 常见问题

### git status 中文输出有误

A: git config core.quotepath false

### Git GUI中文乱码
1. Edit->options
2. Change 'UTF-8'

## 杂项

### [PR 之优雅修正 Review 意见](https://club.rt-thread.org/ask/article/e19f1f0f77fbd119.html)

如何修正 Review 意见，以及修正后如何让你的提交信息保持优雅（只是一个而不是多个）：

1. 如何将本地仓设置两个 remote？（一个上游仓 URL upstream，一个个人仓 URL personal），以及如何在本地同步自己的个人仓（学会 git rebase 之类的操作）；
2. PR 发出后修正 Review 意见后，用 git commit --amend 将少量修改合并到此前的提交记录中；
3. 修正 Review 意见后，用 git push personal master --force 强制推送到个人仓（覆盖掉个人仓最新的提交记录）；

### Git 恢复至某个提交

git reset --hard commit-id (不可撤销)

### 强制推送

git push --force
