# git-learn

git 和 github 学习用

## Git 学习进度

- [Git Book](https://git-scm.com/book/zh/v2)
- 2.3 Git 基础 - 查看提交历史
-

## Git 常用命令

- 查看文件状态：git status
- 简短查看文件状态：git status -s / git status --short
- 查看尚未暂存的文件更新了哪些部分：git diff
- 查看已暂存的将要添加到下次提交里的内容：git diff --staged / git diff --cached
- 采用默认编辑器提交：git commit / git commit -v
- 提交信息与命令放在同一行：git commit -m 'your information'
- 跳过 git add（暂存区）提交：git commit -a
- 从磁盘删除文件移出跟踪目录：git rm filename
- 从暂存区删除文件但在工作区保留：git rm --cached filename
- 强制从暂存区和工作区删除文件：git rm -f filename
- 移动或重命名文件：git mv src-filename dst-filename
- 查看提交历史：git log
- 显示每次提交所引入的差异（按补丁的格式输出）：git log -p/--patch
- 限制现实的日志条目数量 number：git log -p/--patch -number
- 查看每次提交的简略统计信息：git log --stat
- 将每个提交简短显示：git log --pretty=oneline/short/full/fuller
- 定制提交记录的显示格式：git log --pretty=format:"%h - %an, %ar : %s"
- git log --pretty=format 常用的选项
  选项 说明
  %H 提交的完整哈希值
  %h 提交的简写哈希值
  %T 树的完整哈希值
  %t 树的简写哈希值
  %P 父提交的完整哈希值
  %p 父提交的简写哈希值
  %an 作者名字
  %ae 作者的电子邮件地址
  %ad 作者修订日期（可以用 --date=选项 来定制格式）
  %ar 作者修订日期，按多久以前的方式显示
  %cn 提交者的名字
  %ce 提交者的电子邮件地址
  %cd 提交日期
  %cr 提交日期（距今多长时间）
  %s 提交说明
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

- 限制输出长度：git log -<n>
- 按时间限制：git log --since/--untils
- 显示指定作者的提交：git log --author
- 搜索提交说明中的关键字：git log --grep
- 显示那些添加或删除了指定字符串的提交：git log -s <string>
- 指定路径（放在最后位置并用--隔开）：git log --<path>
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

## Vim 常用操作

- 从系统剪切板黏贴到 Vim:
