
# 准备

请先阅读《[一篇文章，教你学会Git](https://www.jianshu.com/p/9685a56bdf7a)》，理解一下git的基本概念

# 需要掌握命令

- git clone
- git fetch
- git pull
- git add
- git commit
- git push
- git status
- git rebase
- git revert
- git reset


# 需要熟悉的概念

- merge
- conflict
- fork
- PR


# 关于工作区和缓存区

创建一个文件 firstFile.txt
```
git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    firstFile.txt
```

运行`git status`得到上棉结果。表示新建的文件没有没有被跟踪（没有加入到缓存区（index））。

执行`git add firstFile.txt`命令可以将新建的文件加入到缓存区。

执行`git commit`将文件提交到本地代码仓库

# reset

分别提交 A B C 三个commit，然后`git reset HEAD^^`(默认的reset的mixed模式)删除B C两个commit，但是文件并没有改变B C两个commit对文件的修改移动到工作区，


分别提交 A B C 三个commit，然后`git reset --soft HEAD^^` 删除B C两个commit，但是文件并没有改变,B C两个commit对文件的修改被保留到了缓存区，工作区的修改依然没变（changes not staged）。

```
 git status
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   firstFile.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   firstFile.txt
```

分别提交 A B C 三个commit，然后`git reset --hard HEAD^^` 删除B C两个commit，工作区和缓存区被完全清空。代码和Acommit提交后保持完全一致。


