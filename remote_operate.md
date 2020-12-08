### 添加远程库

- 要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`；
- 关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；
- 此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改。

------

### 从远程库克隆

- 要克隆一个仓库，首先必须知道仓库的地址，然后使用`git clone git@server-name:path/repo-name.git`命令克隆。
- 如果克隆的仓库不能 push ，先用 `git pull --rebase origin master` 把代码合并。
- 再用`git push origin master`往远程库push代码。

------

### 创建与合并分支

- 查看分支：`git branch`
- 创建分支：`git branch <name>`
- 切换分支：`git checkout <name>`或者`git switch <name>`
- 创建+切换分支：`git checkout -b <name>`或者`git switch -c <name>`
- 合并某分支到当前分支：`git merge <name>`
- 删除分支：`git branch -d <name>`