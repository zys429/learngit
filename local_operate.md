### 安装git

- [点击安装git](https://git-scm.com/downloads)，傻瓜式安装
- 安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功

​        进一步设置，在命令行输入：

```git
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

------

### 创建版本库

- 在本地创建一个文件夹，在文件夹中右键选择 git bash。
- 在命令行中输入`git init`就可以可以把这个文件夹变成一个 git 可以管理的仓库（出现 .git 文件夹）

------

### 把文件添加到版本库

在版本库中编写一个文件：local_operate.md



根据以下操作添加到版本库：

1. 第一步，用命令`git add`告诉Git，把文件添加到仓库

   ```git
   $ git add local_operate.md
   ```

   执行成功没有任何显示。

2. 第二步，用命令`git commit`告诉Git，把文件提交到仓库

   ```git
   $ git commit -m "创建了一个git笔记"
   ```

   -m 后面的引号里面是提交时的**说明，最好有意义**

------

### 版本回退

- 要随时掌握工作区和暂存区的状态，使用`git status`命令。

- 如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。

- 用`git log`命令显示从最近到最远的提交日志，每条日志第一行有版本号。

- 我们用以下语句回退到以前的版本：

  ```git
  $ git reset --hard HEAD~x
  ```

  x为1表示回退到上一个版本，以此类推。

- 回到未来某个版本：

  ```git
  $ git reset --hard commit_id(版本号)
  ```

- Git提供了一个命令`git reflog`用来记录你的每一次命令,

  ![image-20201207185103169](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20201207185103169.png)

------

### 撤销修改

- 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- filename`。
- 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD filename`，就回到了场景1，第二步按场景1操作。
- 已经提交了不合适的修改到版本库时，想要撤销本次提交，参考[版本回退](https://www.liaoxuefeng.com/wiki/896043488029600/897013573512192)一节，不过前提是没有推送到远程库。

------

### 删除文件

- 命令`git rm filename`用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失**最近一次提交后你修改的内容**。
- 如果删错了，可以用`git checkout -- filename`命令恢复到最新版本。