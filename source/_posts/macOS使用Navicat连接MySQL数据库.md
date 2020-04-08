---
title: macOS 使用 Navicat 连接 MySQL 数据库
date: 2019-07-11 18:26:05
tags: [MySQL, Navicat]
categories: [数据库]
---

### 安装 MySQL

- 从 MySQL 官网下载安装包进行安装，链接：https://www.mysql.com/downloads/
- 使用终端命令安装，需提前安装 Homebrew。
  1. 安装 Homebrew
  ```bash
  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```
  2. 安装 MySQL
  ```bash
  brew install mysql
  ```
### 打开 MySQL 服务

- 在终端使用命令 `mysql --version` 查看 MySQL 版本，出现具体的版本号，表示 MySQL 成功安装，如下图。

  ```bash
  mysql --version
  ```

  ![mysql-version](https://user-images.githubusercontent.com/24516169/61049925-52fd1980-a418-11e9-9558-7b4dee6c68b8.png)

- 在终端使用命令 `bash mysql.server start` 来打开 MySQL 服务。如下图，表示 MySQL 服务启动成功。

  ```bash
  bash mysql.server start
  ```

  ![start-mysql](https://user-images.githubusercontent.com/24516169/61096487-5a5d0b00-a48a-11e9-8715-7d3bb3a6d4da.png)

### 登录 MySQL

MySQL 默认的 root 账户不带密码，使用命令 `mysql -uroot` 可直接登录，如下图，表示登录成功。

```
mysql -uroot
```

![mysql-version](https://user-images.githubusercontent.com/24516169/61114682-6fa25b80-a4c3-11e9-899b-a3c9033da25e.png)

因为默认的 root 账户不带密码，安全起见，我们给 root 账户设置密码。（例如设置密码：123456）

```
set password for 'root'@'localhost'='123456';
```

![mysql-modification-password](https://user-images.githubusercontent.com/24516169/61114990-11c24380-a4c4-11e9-9437-e56f6b406357.png)

密码设置成功后，再次登录时需要输入密码，如下命令。

```
mysql -uroot -p'123456'
```

![mysql](https://user-images.githubusercontent.com/24516169/78643782-637aeb80-78e7-11ea-9b17-4fa3ce8b1ba3.png)

### Navicat 连接 MySQL

点击 Navicat Premium 左上角的"连接"，选择" MySQL "，新建一个 MySQL 连接，参数如下，默认端口 **3306**。
![mysql](https://user-images.githubusercontent.com/24516169/78645106-860e0400-78e9-11ea-9191-d7cd64447072.png)

注：

- 可使用命令 `lsof -i:3306` 查看 **3306** 端口是否被占用。
- 如果点击"**测试连接**"发现连接不上，出现报错信息：
  `2059 - Authentication plugin 'caching_sha2_password' cannot be loaded: dlopen(../Frameworks/caching_.......`
  错误原因是因为 MySQL 5.7 版本之后，默认验证方式由原来的 **mysql_native_password** 改成了 **caching_sha2_password**。只需把验证方式修改成原来的，就能连接上了。
  修改方法：登录 MySQL，执行命令：
  ```mysql
  ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';
  ```
