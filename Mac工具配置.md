# Mac工具配置

### 1. 自己搭建高速Shadowsocks服务

googlecloud可以免费使用一年，如果过期了再申请一个新的账号重新搭建

[参考博客http://godjose.com/2017/06/14/new-article/](http://godjose.com/2017/06/14/new-article/)

### 2. 百度云不限速工具

满速的下载，不用再买会员了，有两种方式如下:

> #### 破解试用会员方式

[github地址](https://github.com/CodeTips/BaiduNetdiskPlugin-macOS)

> #### proxyDown

**[参考博客](https://www.runningcheese.com/baiduyun)**

**mac环境快速安装方法如下**

```shell
#编译
git clone https://github.com/proxyee-down-org/proxyee-down.git
cd proxyee-down/front
#build html
npm install
npm run build
cd ../main
mvn clean package -Pprd
#运行
java -jar proxyee-down-main.jar
```

### 3. 汇编环境配置

    brew install nasm

### 4. 未知开发者应用安装

    sudo spctl --master-disable

### 5. gitbook

人人都是作家，快速排版

[参考博客](http://wuxiaolong.me/2017/09/05/GitBookGuide/)

```shell
#Gitbook 是用 npm 安装的，命令行：
sudo npm install -g gitbook-cli
#更新最新版本：
gitbook update
#卸载
npm uninstall -g gitbook
```

#### 流程

1. 在github创建新的repository
2. 在gitbook创建新的book，并在setting中设置和github的同步
3. 通过vscode，克隆 github上的repository到本地并打开操作
4. 在vscode打开的文件夹根目录中，编写readme.md和summary.md文件
 readme.md概述文件
 summary.md目录文件
5. 创建好后，在终端输入gitbook init，gitbook会根据summary.md文件创建文档结构。
编辑对应文档
6. 编辑完成之后，在终端输入 gitbook serve ，简历书籍服务器，在web浏览器中默认localhost:4000地址 进行访问。
7. 完成之后，通过git提交到github（自动同步到gitbook）。可在gitbook保存和阅览。

#### 输出

1. gitbook serve命令可以自己启动web服务器，预览。
2. Markdown Preview Enhanced默认预览就包括html。
3. 要输出为PDF的话，有两种方式：
4. 通过html打开，在html打印中，打印为pdf。
5. 安装princexml插件。建议从princexml官网下载只接安装。

> 使用gitbook命令时可能出现如下错误

Gitbook使用时出现`Error loading version latest`

    Cannot read property 'commands' of null

**解决办法**

下来进入到~/.gitbook/versions/3.2.3/目录中，删除掉node_modules和package.json。这样子gitbook就可以正常使用了