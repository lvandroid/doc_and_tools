# git奇淫技巧

## 命令行创建github远程仓库

```shell
#创建远程仓库 我的github账号是 lvandroid, 我要创建一个叫demo的仓库执行下面命令后，会让你输入密码，输入正确密码后，如果创建成功会打印一长串json
curl -u 'lvandroid' https://api.github.com/user/repos -d '{"name":"demo"}'

# 将本地的文件夹初始化
git init 
git add .
git commit -m 'init'
# 添加到远程仓库
git remote add origin git@github.com:lvandroid/demo.git

# push 代码
git push -u origin master
```

## 同一个仓库推到不同账号

在.git文件夹下修改config配置文件中的url即可

```
cd demo/.git/

vi config

# 如下配置，将gitlab 的url注释掉，添加github的url就可以推送到github上

[remote "origin"]
        #url = git@tech.xiaojubianli.com:zhaolu/doc_and_tools.git
        url = git@github.com:lvandroid/doc_and_tools.git
        fetch = +refs/heads/*:refs/remotes/origin/*

```