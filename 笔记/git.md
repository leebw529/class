# git版本管理工具

### linux基本命令

### 1. cd 进入文件夹

### 2. ll 查看当前文件夹里面的所有文件

​	ll -a  查看当前文件夹所有的文件 包含隐藏文件

### 3. ls 查看当前文件夹里面的所有文件

### 4.clear 清除屏幕信息

### 5. rm  -rf  ./*  删除当前文件夹里面的所有文件

### 6. touch 文件名  创建一个文件

### 7. echo '文件内容' >> 文件名





~ 表示的是用户的家目录

/ 表示的是服务器的根目录







## 创建仓库的步骤：

1. 创建一个文件夹----> 建议放在服务器里面
2. 打开执行git命令行的界面
3. 进入到创建的文件夹里面
4. git操作



## git的基本操作

+ 初始化版本管理仓库

```
git  init   
```

会在当前文件夹中创建一个空的版本管理仓库。会创建一个.git的文件夹。也会创建一个master分支。

+ 查看git的状态

```
git status 
```

+ 将文件添加到git管理中来

```
git add  文件名
git add .  （将单当前文件夹里面的所有文件都使用git管理起来）
```

+ 提交修改的记录

```
git commit  -m  '提交的记录消息'
```

+ 查看文件与之前记录的区别

```
git diff 文件名
```

+ 查看历史提交记录

```
git log
git log  --pretty=oneline
```

+ 版本回滚

```
git reset --hard HEAD^   表示回到上一个版本
git reset --hard 版本号
```

+ 版本恢复

  如果没有关闭命令行工具，也就是可以找到之后的版本号，可以使用版本号直接回复

```
git reset --hard 版本号
```

​        如果已经关闭过命令行了，那么需要使用一下命令找到版本号

```
git reflog
```

+ 撤销当前时间段的修改 ，恢复到上一次提交后的状态

```
git checkout --  文件名
```

+ 删除文件

  从git管理里面删除一个文件，表示git对这个文件不再进行管理了。

```
git  rm  文件名
```

如果删除的文件删除错误了，可以使用撤销恢复。

```
git  checkout -- 文件名
```





## git分支操作

+ 查看分支

```
git branch
```

+ 创建分支

```
git checkout -b 分支名称
```

+ 切换分支

```
git  checkout  分支名
```

+ 删除分支

```
git branch -d 分支名
```

+ 分支合并

```
git merge 分支名
```



## git远程仓库交互

### 1. 如果本地代码提交远程，本地没有仓库，远程新创建仓库

```
git init
git add . 
git commit -m "first commit"
git remote add origin https://github.com/cxymds/day12-4.git
git push -u origin master
```

### 2. 如果远程已经具有仓库，自己本地没有代码，克隆远程仓库

```
git clone https://github.com/cxymds/day12-4.git
```

### 3.远程新建仓库，本地具有代码，具有本地仓库，想要创建远程仓库，建立连接

```
git remote add origin https://github.com/cxymds/day12-4.git
git push -u origin master
```

### 4. 本地没有代码，远程刚创建空代码仓库

```
echo "# day12-4" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/cxymds/day12-4.git
git push -u origin master
```



## 远程代码交互

1. 提交

   ```
   git push
   ```

2. 下拉

   ```
   git pull
   ```



