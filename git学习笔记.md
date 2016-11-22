### 记录了我学习git的一些知识点

```
git init
```

进入想要创建版本库的文件夹，执行git init命令，创建版本库


```
git add filename
```



```
git commit -m "commit description"
```



```
git status
```



```
git log
```


```
git log --pretty=oneline
```



```
git diff
```

当修改了本地仓库中的文件后，可以通过diff命令查看做了哪些改变


```
git config --global gui.encoding utf-8
```

解决gui中文乱码


```
git reset --hard HEAD^
```

> 回退到上一个版本


```
git reset --hard 3628164
```

> 回退到指定版本


```
git reflog
```

> 记录执行的每一次命令，可以在这里查看到历史版本号

> 工作区与版本库（暂存区和分支）的概念
git管理的是修改，而不是文件


```
git checkout -- filename
```

> 丢弃工作区的修改
+ 一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
+ 一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。


```
git reset HEAD filename
```

> 丢弃暂存区的内容
+ 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
+ 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。
+ 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，可以使用reset回退，不过前提是没有推送到远程库。


```
ssh-keygen.exe -t rsa -C "saebalee@gmail.com"
```


```
git remote add origin git@github.com:wiwiluo/learning_git.git
```


```
git push -u origin master
```
> 首次推送

```
git push origin master
```

warning: refname 'HEAD' is ambiguous的解决方案，首先通过git branch查看分支情况，然后删除掉不需要的分支
删除分支命令：git branch -D branchName


```
git checkout -b dev
```
> 创建dev分支，然后切换到dev分支，相当于下面两个命令的合并执行

```
git branch dev2
git checkout dev2
```

```
git merge dev
```
> 合并指定分支dev到当前分支

```
git log --graph --pretty=oneline --abbrev-commit
```
> 查看分支合并图