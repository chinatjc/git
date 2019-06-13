#### 时光穿梭机

##### 查看工作区、暂存区的状态

``` bash
git status
```

##### 查看工作区修改的内容

``` base
git diff
```

##### 查看分支的更新记录

``` base
git log
```


``` base

每条分支记录信息缩减为一行

git log --pretty=oneline
```

##### 版本回退

在git中，HEAD表示当前的版本

``` base

退回到上一条分支记录时的状态

git reset --hard HEAD^

```

``` base

退回到上上一条分支记录时的状态

git reset --hard HEAD^^

.
.
.
.
.
.

以此类推

```

``` base

退回到指定commit id的版本，commit id可以简写前几位，能表示唯一性即可

git reset --hard <COMMIT ID>
```

``` base

通过git reflog可以查看所有修改HEAD的记录，以回到某个记录状态

git reflog


```

##### 撤销修改

``` base

撤销工作区的修改

git checkout -- <FILE>

```

``` base

撤销暂存区的修改，让修改回到工作区

git reset HEAD <FILE>

```

``` base

撤销版本库某一次修改

git reset --hard <COMMIT ID>

```

##### 删除文件

``` base
rm <FILE>

只需要git checkout -- <FILE>，撤销工作区的删除即可
```

``` base

删除文件，且提交到暂存区
git rm <FILE>
```

##### 彻底删除某个文件

``` base
// 从版本库删除文件，删除文件路径是相对于.git的
git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch <PATH OF NEED TO DELETE FILE>' --prune-empty --tag-name-filter cat -- --all

// 强制推送删除文件后的版本库
git push origin master --force

// 清理和回收空间
rm -rf .git/refs/original/

git reflog expire --expire=now --all

git gc --prune=now

git gc --aggressive --prune=now
```
