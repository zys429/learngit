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

------

### 手动解决冲突

- 当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
- 解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容，再提交。
- 用`git log --graph`命令可以看到分支合并图

------

### 分支管理策略

- 合并分支时，加上`--no-ff`参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而`fast forward`合并就看不出来曾经做过合并。
- 本次合并要创建一个新的commit，所以加上`-m`参数，把commit描述写进去。例子：`git merge --no-ff -m "merge with no-ff" dev`。