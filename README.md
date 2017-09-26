# notes
自己的一些学习笔记等等
#vultr 服务器的基本配置及其教程
## 1.1 vultr的购买
   自己之前一直想把自己项目挂在网上，但是由于github上访问比较慢并且国内的服务器需要备案等等。因此自己便选择了国外的一些代理。个人比较推荐搬瓦工（附上传送门：http://banwagong.cn/），  vultr （附上传送门：https://www.vultr.com/）。
   如果有想免费试试搭建服务器可以试试亚马逊（AWS） 后期如果有时间，我会附上这个的部署教程。
## 1.2 购买前的准备
首先需要在vultr申请一个账号，在早些时候vultr还是不支持支付宝的。如果你有Paypel的话在支付时可以选择使用这个支付。但是后边由于大陆用户的增加，最终这个网站开通了支付宝支付。
话不多说。让我们直接开始购买吧。

购买 Tokyo Ubuntu 16.10 x64
安装 Bitvise SSH Client

Server
host : IP地址 或 域名A记录解析到IP
Port : 22
Authentication

Username : root
Password : ******
Login 弹出命令框

##node
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
apt-get install nodejs
##npm
npm config set registry https://registry.npm.taobao.org
##yarn
##配置仓库
$ curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
##安装
$ apt-get update && sudo apt-get install yarn
##镜像源
$ yarn config set registry https://registry.npm.taobao.org
##pm2
$ yarn add pm2
$ pm2 kill

##MongoDB

##安装
$ apt-get install -y mongodb-server

##初始化
$ mongod --dbpath=/root/mer/data/db

##守护进程
$ mongod --fork --dbpath=/root/mer/data/db --logpath=/root/mer/data/db/log/err.log --logappend

