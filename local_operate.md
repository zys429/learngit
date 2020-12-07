### 安装git

- [点击安装git](https://git-scm.com/downloads)，傻瓜式安装
- 安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功

​        进一步设置，在命令行输入：

​		

```git
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

------

### 创建版本库

- 在本地创建一个文件夹，在文件夹中右键选择 git bash。
- 在命令行中输入 git init 就可以可以把这个文件夹变成一个 git 可以管理的仓库（出现 .git 文件夹）

------

### 把文件添加到版本库

在版本库中编写一个文件：local_operate.md



根据以下操作添加到版本库：

1. 第一步，用命令 git add 告诉Git，把文件添加到仓库

   ```git
   $ git add readme.txt
   ```

   执行成功没有任何显示。

2. 第二步，用命令`git commit`告诉Git，把文件提交到仓库

   ```git
   $ git commit -m "wrote a readme file"
   ```

   -m 后面的引号里面是提交时的**说明，最好有意义**

------

### 版本回退

