#  **git基本操作**

## 命令速查：

 ![git](src/git.jpg) 

`$  git  remote  set-url  <remote>  <url>` 	#更改远程版本库

`$  git checkout -b <name>`					#创建并切换分支

`git push origin master --force`                          #强制更新

## 暂存命令

1、将当前工作区的操作暂存

`$ git stash` 		可多次使用该命令

2、查看多次提交的stash

`$ git stash list`

3、恢复或删除stash

`$  git stash apply` 	#恢复（恢复并不会删除）

`$  git stash drop`		#删除

`$ git stash pop` 		#恢复并删除

## 将 git add 和 git commit -m 命令合二为一

1、合并命令

`git config --global alias.ac '!git add -A && git commit -m '`

2、使用命令

`git ac "提交信息"` 

## 版本回退

`$ git reset --hard HEAD^` 		#回退到上一个版本

## 初次安装git需要配置用户名和邮箱(并不是github用户名和邮箱)

`$ git config --list `       #查看 配置信息列表

`$ git config user.name `       #查看 用户名

`$ git config user.email `       #查看 邮箱

`$ git config --global user.name "随意名字"`  #修改 用户名

`$ git config --global user.email "随意邮箱"`  #修改 邮箱

## git使用ssh密钥

1、查看是否存在id_rsa和id_rsa.pub(或者是id_dsa和id_dsa.pub之类成对的文件)

`$ ls -al ~/.ssh` 

2、没有则用命令创建，之后一路按回车即可

`$ ssh-keygen -t rsa -C "你的邮箱"` 

3、查看公钥

`$ cat ~/.ssh/id_rsa.pub` 

4、登陆你的github帐户。点击你的头像，然后 Settings -> 左栏点击 SSH and GPG keys -> 点击 New SSH key。

然后你复制上面的公钥内容，粘贴进“Key”文本域内。 title域，自己随便起个名字。

点击 Add key。

5、验证

`$ ssh -T git@github.com` 

出现`Hi xxx! You've successfully authenticated, but GitHub does not # provide shell access.` 就成功了。
