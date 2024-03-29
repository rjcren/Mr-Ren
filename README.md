将目录变成Git可以管理的仓库：
git init
Initialized empty Git repository in <目录>

文件放入仓库：git add [-f] <name>             （-f：强制添加）
提交：git commit -m "说明"

查看仓库状态：git status
查看修改：git diff <name>

查看历史记录：git log  [--graph] [--pretty=oneline] [--abbrev-commit]
			   (–graph 图形，–pretty=oneline 减少数据，–abbrev-commit 头部数据减少)
查看所有历史命令：git reflog
回退：git reset --hard commit-id            (commit-id：版本号 || HEAD,HEAD^：当前版本,上一版本)
查看工作区和版本库里最新版本的区别：git diff HEAD -- <name>

丢弃工作区的修改：git checkout -- <name>
查看文件：cat <name>
文件删除：git rm <name>

关联的远程仓库：git remote add <库名> git@github.com:地址  （库名一般默认命名origin || 地址如274******93/***）
推送本地库内容到远程库：git push [-u] [<库名> <分支名>]   (-u：将本地分支推送到远程分支，并关联)
合并远程库最新提交到本地：git pull [--set-upstream-to=<库名>/<远程分支名> <本地分支名>]

查看远程库信息：git remote [-v]    （-v：查看详情）
删除远程库：git remote rm <库名>
克隆远程库：git clone git@github.com:地址

查看分支：git branch
创建分支：git branch <name>
切换分支：git checkout <name>    ||     git switch <name>
创建+切换分支：git checkout -b <name> [<库名>/<分支名>]   ||     git switch -c <name> [<库名>/<分支名>]   (可选部分为创建远程库的分支到本地)
合并某分支到当前分支：git merge [--no-ff] [-m "说明"] <name>
					（--no-ff：禁用Fast forward 用普通模式合并：合并后的历史有分支）
删除分支：git branch -d <name>
		   git branch -D <name>  （强行删除没有被合并过的分支）

储藏当前工作：git stash
储存的工作列表：git stash list
恢复工作区：git stash apply   （恢复后stash内容不删除，需用 git stash drop删除）
			git stash pop   （恢复并删除stash内容）
复制特定提交到当前分支：git cherry-pick <版本号>

将提交变成一条直线：git rebase

查看所有标签：git tag
给当前分支上次提交打上标签：git tag <标签名> [-m "说明"] [版本号]
查看标签信息：git show <标签名>
删除标签：git tag -d <标签名>
		   git push origin :refs/tags/<版本号>         （删除远程库的标签）
推送标签到远程库：git push <库名> <版本号>
				   git push <库名> --tags            （推送全部未推送的本地标签到远程）


让Git显示颜色：git config --global color.ui true
配置别名：git config [--global] alias.别名 原命令   （--global 全局参数,所有Git仓库使用      原命令为多个单词可加引号）
删除别名：.git/config文件 alias 后面，直接把对应的行删掉即可
