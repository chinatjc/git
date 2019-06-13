#### 分支管理

##### 查看分支

``` base
git branch
```

##### 创建分支

``` base
git branch <NAME>
```

##### 切换分支

``` base
git checkout <NAME>
```

##### 创建 & 切换分支

``` base
git checkout -b <NAME>
```

##### 三种合并方式，及其区别

> 快进合并模式(fast-forward)，合并后无历史分支记录，但有commit记录

``` base
git merge <NAME>
```

> 普通合并模式(no-ff)，合并后有历史分支记录

``` base
git merge --no-ff -m '<MESSAGE>' <NAME>
```

> 压缩合并模式(squash)，把被合并分支上所有改动合并为一条，然后把这条改动应用到合并分支上，最后git commit -m '\<MESSAGE\>'提交到版本库

``` base
git merge --squash <NAME>
```

##### 删除分支

``` base
git branch -D <NAME>

// 批量删除分支
git branch | grep -v '<NOT DELETE BRANCH NAME>' | xargs git branch -D
```

##### 恢复被删除的分支

``` base
// 找到删除分支对应的commit id
git reflog

git branch <DELET_BRANCH_NAME> <DELET_BRANCH_COMMIT_ID>
```

##### 查看代码中的冲突代码

``` javascript
<<<<<<< HEAD
Creating a new branch is quick & simple.
=======
Creating a new branch is quick AND simple.
>>>>>>> feature1
```

##### 查看分支合并图

``` base
git log --graph
```

``` base
git log --graph --pretty=oneline --abbrev-commit
```

##### 临时保存手头工作

> 保存
``` base
git stash
```

> 查看临时保存的列表
``` base
git stash list
```

> 找到原先的分支后，恢复临时保存的状态
``` base
git stash pop
```
