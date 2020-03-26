---
title: 在Mac下配置多个Git账户的SSH-Key
date: 2018-07-16 16:33:01
tags: [mac, git, ssh-key]
categories: [技术教程]
---
#### 准备工作
请确保在你的Mac上已安装Git。安装Git请参考：[传送门](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)  
在终端输入命令`$ git --version`， 能打印出具体的版本号，表示Git正确安装。

####  开始配置
本文以配置**GitHub**和**GitLab**为案例，将生成两对公共/私有rsa密钥对，**rsa_github** 和 **rsa_gitlab**。

##### 在本地创建SSH-Key
1、打开终端，`$ cd ~`，进入到当前用户目录下。  

2、使用命令`$ ssh-keygen -t rsa -C "i@itpoet.cn"`生成公共/私有rsa密钥对。此时会看到终端提示输入要保存密钥的文件名，为了做区分，我们给文件名加个后缀，本例第一个rsa密钥对：**rsa_github**。
接着会看到终端提示输入密码，敲两次 _**Enter回车键**_ 则不需要密码。最终在 _**.ssh 文件夹**_ 里生成 _**rsa_github**_ 和 _**rsa_github.pub**_ 两个文件，如图：  
![生成rsa_github](https://user-images.githubusercontent.com/24516169/43447613-6a4544ae-94de-11e8-8e91-07d6ef1e45e3.png)  
![rsa_github和rsa_github.pub密钥对](https://user-images.githubusercontent.com/24516169/43447618-6add7116-94de-11e8-9986-8b90bf50e098.png)  
**注意**：在 **第2步** 执行完后，如果用户目录下没有生成 _**.ssh 文件夹**_ ，那我们需要手动创建。  
```bash
$ cd ~
$ mkdir .ssh
$ cd .ssh
```
成功创建完 _**.ssh 文件夹**_ 之后，再执行 **第2步** 操作。  

3、创建本例的第二个rsa密钥对，**rsa_gitlab**。 
```bash
$ cd .ssh
$ ssh-keygen -t rsa -C "a@itpoet.cn"
```
如图：  
![生成rsa_github](https://user-images.githubusercontent.com/24516169/43447615-6a959e4a-94de-11e8-8f23-8fd2128ba6a7.png)
![rsa_github和rsa_github.pub密钥对](https://user-images.githubusercontent.com/24516169/43447619-6b104b72-94de-11e8-9a4b-4febc6458e4c.png)  

4、为ssh添加config配置文件，在 _**.ssh文件夹**_ 下，新建config文件。  
```bash
$ cd ~/.ssh
$ touch config
```
config文件创建好之后，将其内容修改为：
```
Host github.com
  User itPoet_github
  IdentityFile ~/.ssh/rsa_github

Host gitlab.com
  User itPoet_gitlab
  IdentityFile ~/.ssh/rsa_gitlab
```

5、配置 **.gitconfig** 文件。使用如下命令将会在用户目录下自动创建 **.gitconfig** 文件。
```bash
$ cd ~
$ git config --global user.name "itPoet_github"
$ git config --global user.email "i@itpoet.cn"
```

**注意**：在 **第4步** 执行完后，如果用户目录下没有生成 _**.gitconfig**_ 文件 ，那我们需要手动创建。

```bash
$ cd ~
$ touch .gitconfig
```
最后将.gitconfig文件的内容修改为：
```
[user]
    name = itPoet_github
    email = i@itpoet.cn
[user]
    name = itPoet_gitlab
    email = a@itpoet.cn
```
##### 在对应的Git网站添加SSH密钥设置
1、 **GitHub**  
settings --> SSH and GPG keys --> New SSH Key  
打开 **rsa_github.pub**，将里面的内容复制到 **Key** 输入框中，如图：
如图：  
![github.com-add-new-ssh-key-1](https://user-images.githubusercontent.com/24516169/43447624-6c25549e-94de-11e8-9584-527e2100964c.png)  
![github.com-add-new-ssh-key-2](https://user-images.githubusercontent.com/24516169/43447626-6c56a026-94de-11e8-9530-3ba0accc6a86.png)  


2、 **GitLab**  
Profile --> SSH keys
打开 **rsa_gitlab.pub**，将里面的内容复制到 **Key** 输入框中，如图：
如图：  
![gitlab.com-add-new-ssh-key-1](https://user-images.githubusercontent.com/24516169/43447628-6ca0b468-94de-11e8-95e5-377c7b85b97c.png)
![gitlab.com-add-new-ssh-key-2](https://user-images.githubusercontent.com/24516169/43447626-6c56a026-94de-11e8-9530-3ba0accc6a86.png)  

**至此，在Mac下配置多个Git账户的SSH-Key参考教程也完成，同理，我们还可以配置Coding、码云等。现在让我们来体验使用SSH提交代码吧~~**
