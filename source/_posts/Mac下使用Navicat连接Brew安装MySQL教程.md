---
title: Mac下使用Navicat连接Brew安装MySQL教程
date: 2019-07-11 18:26:05
tags: [MySQL, Navicat]
categories: [数据库]
---

### 安装MySQL
Mac安装MySQL有多种方式，最方便是这两种：
- 第一种直接从MySQL官网下载安装包进行安装，这里不做过多介绍。
- 第二种使用终端命令安装，前提要先安装好Homebrew。

安装Homebrew
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
安装MySQL
```bash
brew install mysql
```
![brew-install-mysql](https://user-images.githubusercontent.com/24516169/61051202-1d0d6480-a41b-11e9-85c2-05600f9712b4.png)


### 启动MySQL
使用brew成功安装MySQL之后，启动MySQL
```bash
bash mysql.server start
```
如图，则表示MySQL服务启动成功。
![start-mysql](https://user-images.githubusercontent.com/24516169/61096487-5a5d0b00-a48a-11e9-8715-7d3bb3a6d4da.png)


查看MySQL版本
```
mysql --version
```
![mysql-version](https://user-images.githubusercontent.com/24516169/61049925-52fd1980-a418-11e9-9558-7b4dee6c68b8.png)


登录MySQL
```
mysql -uroot
```
![mysql-version](https://user-images.githubusercontent.com/24516169/61114682-6fa25b80-a4c3-11e9-899b-a3c9033da25e.png)


默认的root账户不带密码，设置root账户密码（本例密码：123456）
```
set password for 'root'@'localhost'='123456';
```
![mysql-modification-password](https://user-images.githubusercontent.com/24516169/61114990-11c24380-a4c4-11e9-9437-e56f6b406357.png)

密码设置成功后，登录时需要输入密码才能访问MySQL数据库：
```
mysql -uroot -p'123456'
```
![mysql](https://user-images.githubusercontent.com/24516169/61114808-b09a7000-a4c3-11e9-9354-82d215b3c60f.png)

### 使用Navicat本地的MySQL数据库

点击Navicat Premium左上角的“连接”，选择“MySQL”

左上角新建mysql連接，參數如下，默認端口爲3306，想查看端口可以使用命令：

lsof -i:3306

點擊連接測試發現怎麼也連接不成功，報的錯爲：

2059 - Authentication plugin 'caching_sha2_password' cannot be loaded: dlopen(../Frameworks/caching_....... 

錯誤原因是由於從mysql5.7版本之後，驗證方式默認從原來的mysql_native_password改成了caching_sha2_password。

我們需要將驗證方式修改爲原來的，纔可以使navicat連接成功，先進入mysql，然後輸入以下命令：

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '密碼';
