# multiple-git 

> 同时部署多个远程仓库

## 步骤

* 分别在远程端建立项目得到远程地址 `A.git` 和 `B.git`

* 初始化git `git init`（已存在.git目录的可跳过此步骤）

* `git remote add origin A.git`

* 修改`.git`目录下的`config`文件

```config
// 修改前
[remote "origin"]
    url = AAA
    fetch = +refs/heads/*:refs/remotes/origin/
// 修改后
[remote "origin"]
    url = A.git
    url = B.git
    fetch = +refs/heads/*:refs/remotes/origin/
```

* git push origin master


## 注意

* 多个远程仓库的当前分支需要保持一致

