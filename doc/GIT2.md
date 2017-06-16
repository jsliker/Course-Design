## git之Branch

### 创建分支

现在我们就使用下面的命令去创建一个分支. 这个命令只是创建并没有切换到新创建的分支上. git仓库初始化创建的时候, 会为我们自动创建一个master的主分支.

```
$ git branch branch-name
```

可以从任何的地方创建分支, 并切换到新创建的分支上.

```
$ git checkout -b branch-name
```

### 显示分支

如果我们想要显示当前git仓库中有多少个分支.

```
$ git branch -av
```

### 分支切换

如果我们想从A分支切换到B分支使用下面的命令.

```
$ git checkout branch-name
```

### 删除分支

如果我们要删除一个分支, 那么我们一定要站在另一个分支上去删除它. 也就是说不能删除当前所在的分支.

```
$ git branch -D branch-name
```

## 远程仓库

### 添加远程仓库

如果我们现在本地有一个git仓库, 我们使用remote add 命令将它添加到远程的仓库中.

```
$ git remote add origin https://github.com/jsliker/Course-Design.git
```

并需要将远程的仓库的信息更步到本地, 这里主要指的示远程仓库的分支和远程库的提交变更信息.

```
$ git fetch origin
```

### 同步master分支

如果我们本地的仓库进行开发, 交进行提交commit. 那么我们本地的仓库和远程的仓库就不能保持同步了.那么我们需要把本地的这次提交也要反映在远程的仓库上. 那么我们就需要使用push命令.

```
$ git push origin master
```

### 同步其它分支

如果我们需要我们其它分支的提交也要反映在远程库中. 如果远程没有这个分支, 它就会自动创建这个分支.

```
$ git push origin branch-name
```

### 删除远程分支

可以用这个非常有意思的语法来删除它：git push [远程名] :[分支名]。 在于分支名前的冒号.

```
$ git push -u origin :branch-name
```

## 从远程仓库同步

### clone

当我们知道git仓库的地址了(在github上有很多的开源仓库.), 就可以使用下面的命令将源码拉取到本地.

```
$ git clone url
```

### pull

我们已经拉取源码到本地了, 但是服务器上的git已经更新了, 当我们需要将服务器的源码与本地源友进行同步进时, 需要使用下面的命令.

```
$ git pull
```


参考：

https://nts.newbieol.com/classroom/study/58?lid=4130
菜鸟公开课

