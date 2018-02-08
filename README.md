# test

## 创建版本库

```git
git init     
git init <指定目录>
```

## 添加新文件或修改文件到暂存区

```    
git add .  
git add <指定文件>
git add <文件1> <文件2> <文件3> <文件...>
```

## 提交暂存区中的更改到本地仓库

```
git commit -m "提交注释"
```

## Git配置

```
git config --global push.default matching
#git push 会把你本地所有分支push到名称相对应的远程分支上。

git config --global push.default simple
#git push 仅仅把当前所在分支push到对应的远程分支上。
```

## 克隆项目
```
git <仓库地址>
git <仓库地址> <指定目录>
```

## 查看仓库的当前状态

```
git status
git status -s        #获得简短的结果输出
```

## 查看文件改动
 - 查看尚未缓存的改动：git diff	(工作副本 <---> 缓存区)
 - 查看已缓存的改动：git diff --cached	(缓存区 <---> 本地仓库)
 - 查看已缓存的和未缓存的所有改动：git diff HEAD	(工作副本/缓存区 <---> 本地仓库)
 
## 取消已缓存的内容

```
git reset HEAD -- <文件>
```

## 从Git仓库中删除文件

```
git rm <文件>
git rm -f <文件>		#强制删除
git rm --cached <文件>
```


