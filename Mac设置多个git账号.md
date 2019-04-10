# Mac设置多个git账号

## 场景

默认情况下，一台电脑的Git只对应一个账户，只能往一个网站push代码，非常不便。

如何在一个Git终端中配置多个账户，同时管理多个托管网站的代码？

## 配置步骤

### 1. 生成sshkey

根据不同邮箱账号生成不同的key


> **github 账号的key** 
```shell

ssh-keygen -C "lvandroid@outlook.com"

#输入保存的文件名 id_rsa_lvandroid 会生成 id_rsa_lvandroid（私钥）和id_rsa_lvandroid.pub(公钥)
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/liugui/.ssh/id_rsa): id_rsa_lvandroid 

```
>**gitlab 账号的key**

```shell
ssh-keygen -C "zhaolu@xxxx.com"

#输入保存的文件名 id_rsa_lvandroid 会生成 id_rsa_zhaolu（私钥）和id_rsa_zhaolu.pub(公钥)
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/liugui/.ssh/id_rsa): id_rsa_zhaolu 

```

### 2. 私钥添加到本地

```shell
ssh-add ~/.ssh/id_rsa_lvandroid
ssh-add ~/.ssh/id_rsa_zhaolu
```

### 3. 对本地秘钥进行配置

由于添加了多个密钥文件，所以需要对这多个密钥进行管理。在.ssh目录下新建一个config文件：

```shell
vi config

# 增加如下配置
Host github 
HostName github.com
User lvandroid
IdentityFile ~/.ssh/id_rsa_lvandroid

Host gitlab
HostName tech.xiaojubianli.com
User zhaolu
IdentityFile ~/.ssh/id_rsa_zhaolu
```

### 4. 添加公钥到github和gitlab

```shell
# 复制公钥的内容
cat ~/.ssh/id_rsa_lvandroid.pub|pbcopy
```

执行以上命令后直接粘贴到网站ssh-key即可

### 5. 测试一下配置是否成功

```shell
ssh -T git@github.com
#在config文件中，给GitHub网站配置的别名就是github，所以可以直接使用别名也可以
ssh -T git@github

ssh -t git@gitlab
```