#### 标签管理

##### 新建标签
``` base
git tag <TAGNAME>
```

##### 查看标签
``` base
git tag
```

##### 推送标签到远程
``` base
git push origin <TAGNAME>

git push origin --tags
```

##### 本地删除标签
``` base
git tag -d <TAGNAME>
```

##### 远程删除标签
``` base
git push origin :refs/tags/<TAGNAME>
```
