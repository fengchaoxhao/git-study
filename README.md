# Git 学习、练习项目

> - 目录
>   - [学习网址](#学习网址)

## 学习网址
> [Git教程 | 菜鸟教程](http://www.runoob.com/git/git-tutorial.html)  
> [廖雪峰的官方网站-Git](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)  
> [Git官方教程](https://git-scm.com/book/zh/v2)

## Git文件的三种状态
> - 已提交(committed)
> - 已修改(modified)
> - 已暂存(staged)

## Git项目的三个工作区的概念
>1. Git仓库
>    Git仓库目录是Git用来保存元数据和对象数据库的地方。
>2. 工作目录
>    工作目录是对项目的某个版本独立提取出来的内容。
>3. 暂存区域
>    暂存区域是一个文件，保存了下次将要提交的文件列表信息。

## Git配置
### Git配置文件存放路径
```
/etc/gitconfig                            #系统级配置文件存放路径
~/.gitconfig 或 ~/.config/git/config      #用户级配置文件存放路径
.git/config                               #仓库级配置文件存放路径
```
### Git常用配置
```
$ git config --list                             #查看配置信息
$ git config <key>                              #查看具体某项配置
$ git config --system                           #针对系统所有用户适用的配置
$ git config --global                           #针对当前用户适用的配置
$ git config                                    #针对当前仓库适用的配置
$ git config --global push.default matching     #git push 会把你本地所有分支push到名称相对应的远程分支上。
$ git config --global push.default simple       #git push 仅仅把当前所在分支push到对应的远程分支上。
$ git config --global core.editor vi            #修改核心编辑器为vi编辑器
$ git config --global color.ui true             #让Git显示颜色
$ git config --global alias.st status           #配置status命令参数的别名
```
## Git帮助查看
```
$ git help <verb>
$ git <verb> --help
$ man git-init
```
## 获取Git仓库
### 初始化仓库
```
$ git init     
$ git init <指定目录>
```
### 克隆现有的仓库
```
$ git clone <仓库地址>
$ git clone <仓库地址> <指定目录>
```

## 添加新文件或修改文件到暂存区
```    
$ git add .                                 #添加当前目录下的所有文件到暂存区
$ git add <指定文件>                         #添加指定文件到暂存区
$ git add <文件1> <文件2> <文件3> <文件...>   #添加多个指定文件到暂存区
```

## 查看当前文件的状态
```
$ git status             #注：如果一个目录下没有任何文件，则不会显示。
$ git status -s          #获得简短的结果输出
$ git status --short
```
![git status 效果](./images/git_status_02.png "git status 效果展示图")

## 查看文件改动
```
 - 查看尚未缓存的改动：git diff	(工作副本 <---> 缓存区)
 - 查看已缓存的改动：git diff --cached	(缓存区 <---> 本地仓库)
 - 查看已缓存的和未缓存的所有改动：git diff HEAD	(工作副本/缓存区 <---> 本地仓库)
```
![git diff 效果展示图](./images/git_diff_01.png "git diff 效果展示图")

注：[上面图片里的内容看不懂的话，请学习下如何读懂diff](http://www.ruanyifeng.com/blog/2012/08/how_to_read_diff.html)

## 提交暂存区中的更改到本地仓库
```
$ git commit
$ git commit -m "提交注释"
$ git commit -a -m "提交注释"
$ git commit -v
```

## 从Git仓库中删除文件
```
git rm <文件>	                  #从暂存区中删除
git rm -f <文件>	              #从暂存区中强制删除
git rm --cached <文件>	        #从暂存区中删除，工作区保留
git rm -r *		                  #递归删除
```
注：执行rm命令后只是从暂存区删除，最后还要commit之后才会在仓库中删除。

## 移动或重命名一个文件、目录
```
git mv <文件/目录> <文件/目录>
```

## 取消已暂存的内容
```
git reset HEAD -- <文件>
git reset --hard HEAD^    #TODO
```

## 撤销工作区的修改

```
git checkout -- <文件>
```

## 创建分支

```
git branch (分支名称)
```

## 查看分支

```
git branch
```

## 切换分支

```
git checkout (分支名称)
git checkout -b (分支名称) #创建新分支并立即切换到新分支下
```

## 删除分支

```
git branch -d (分支名称)
```

## 合并分支

```
git merge (分支名称)
git merge --no-ff -m "提交注释" (分支名称)
```

## 查看提交历史

```
git log
git log --oneline		        #以简短的方式查看日志
git log --oneline --graph		#查看分支合并
git log --oneline --reverse     #逆向显示日志
git log --author <用户名> 	 #查看某个用户的提交日志
```

## 查看命令历史

```
git reflog
```

## 打标签

```
git tag -a v1.0 -m "提交注释"    #给当前最近一次提交(HEAD)打标签
git tag -a v1.0 <版本号>    #给历史的某一版本打标签
git tag    #查看标签
git tag -d v0.1    #删除标签
```

## 查看标签详情

```
git show <版本号>
```

## 添加远程仓库

```
git remote add <别名> <远程仓库地址>
```

## 查看仓库

```
git remote    #查看当前远程仓库
git remote -v    #查看当前远程仓库，并显示实际的链接地址
```

## 删除远程仓库

```
git remote rm <别名>
```

## 提取远程仓库

```
git fetch
```

## 推送远程仓库

```
git push
```

## 存放工作区

```
git stash
git stash list
git stash apply
git stash pop
注：没有被stage或者head的文件，是无法被 stash的。  
而且会显示在各个分支里。让你迷惑它到底该属于哪个分支。  
 所以stash起作用的全是stage 或者 head 的文件。
```
