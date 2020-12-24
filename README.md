# gitStudy

## 1.git  拉取线上的仓库

```git
git clone git@github.com:1935868896/gitStudy.git
```

## 2.git 提交单次文件

```
1.修改文件
2.git add .                                //此处提交文件到暂存区,可以提交多个,也可以提交一个
3.git commit -m 此处添加更新的备注            //此处提交文件到本地仓库
4.git push                                 //此处提交文件到远程仓库
```

### 1:git提交需要注意

- `git新增文件的操作和git修改文件的操作相同`,没有任何多余的其他步骤

-  `git提交的时候只会提交暂存区的文件`

### 附1: git add

在使用svn的时候,我们使用新增文件的时候 需要先add文件后提交,而更新的文件只需要commit即可
但是git当中,新增的文件git也默认添加了,但是新增和修改的文件都需要 add 添加到暂存区这一步骤

### 附2: Untracked files:

git untracked files 实际上就是新增的文件,但是当我们使用add的时候,它会直接提交到暂存区,此处一定要记住和svn新增文件的不同之处

使用git status 和git status -s 我们可以看到git 文件的状态

![](./图库/微信截图_20201224110834.png)

### 附3:git reset 

git reset 可以将我们提交到暂存区的文件重新返回去

## 3.git 多次提交文件

```
修改--->add--->commit
修改--->add--->commit
git push                                           //此时我们直接push两次commit
```

### git合并文件

```
git rebase -i HEAD~3
```

上面未被注释的部分列出的是我们本次rebase操作包含的所有提交，下面注释部分是git为我们提供的命令说明。每一个commit id 前面的`pick`表示指令类型，git 为我们提供了以下几个命令:



> - pick：保留该commit（缩写:p）
> - reword：保留该commit，但我需要修改该commit的注释（缩写:r）
> - edit：保留该commit, 但我要停下来修改该提交(不仅仅修改注释)（缩写:e）
> - squash：将该commit和前一个commit合并（缩写:s）
> - fixup：将该commit和前一个commit合并，但我不要保留该提交的注释信息（缩写:f）
> - exec：执行shell命令（缩写:x）
> - drop：我要丢弃该commit（缩写:d）

## 4.git pull

### 1.本地无修改,无冲突



### 2.本地有修改,无冲突



### 3.本地有修改,有冲突

两种普遍的解决方法:

#### 1.git stash

```
git stash
git pull
git stash pop stash@{0}
```

#### 2.git commit

```
git commit -m 本地提交
git pull              //此处进入 (main|MERGING)

1.git merge --abort (此种方法是返回到冲突之前的情况当中,就是咱们pull前的情况)

2.修改文件 ,解决冲突
git add 
git commit -m 解决冲突
git push               //会多提交一个解决冲突的版本
```



