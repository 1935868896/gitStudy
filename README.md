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