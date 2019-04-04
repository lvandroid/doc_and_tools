# Mac工具配置

### 1. 自己搭建高速Shadowsocks服务

googlecloud可以免费使用一年，如果过期了再申请一个新的账号重新搭建

[参考博客http://godjose.com/2017/06/14/new-article/](http://godjose.com/2017/06/14/new-article/)

### 2. 百度云不限速工具

满速的下载，不用再买会员了

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

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1qe7smyd5j30le0pvn0q.jpg)

![](https://ws2.sinaimg.cn/large/006tKfTcly1g1qe7uu9u6j30jb05sjs9.jpg)