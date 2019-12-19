# 开发环境预安装

### Homebrew

**brief**：Homebrew是macOS上的软件包管理工具，类似于Red hat的yum，Ubuntu的apt-get

1. homebrew的安装

   ```
   /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
   ```

2. homebrew的卸载

   ```
   /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
   ```



### Git

**brief**：Git是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理

***ATTENTION***：以下的几乎所有配置都可以通过github的客户端完成

1. github使用ssh密钥

   **好处**：git可以通过https协议或者git协议进行远程下载，但是https协议每次push和pull时都需要输入用户名和密码，而git协议通过ssh密钥后不需要密码即可push和pull

   ● 首先查看~/.ssh目录下是否 存在ssh key

   ● 生成密钥

   ```
   ssh-keygen -t rsa -C "your email"    ##生成密钥
   ```

   ● 将ssh-key添加到ssh-agent

   ```
   eval $(ssh-agent-s)
   ssh-add ~/.ssh/id_rsa    ##将ssh-key添加到ssh-agent
   ```

   ● 将**~/.ssh/id_rsa.pub**文件中的内容复制粘贴到github上的ssh区域

   ● 验证ssh的连接

   ```
   ssh -T git@github.com    ##验证ssh的连接
   ```

2. git的安装和卸载

   ```
   brew install git  ##使用brew命令安装git
   which -a git      ##列出 git命令所在的位置
   ```

3. git的使用

   ```
   git --version                     ##查看git的版本
   git config --global user.name     ##配置用户名
   git config --global user.email    ##配置邮箱
   git config --list                 ##列出所有配置信息
   
   
   git init                            ##初始化一个仓库
   git status                          ##查看工作区状态 uncommited 已有的，刚修改  untracked 原先的，新建的
   git diff														##查看修改内容在哪里 
   git diff HEAD -- file               ##比较当前版本库和工作区最新文件之间的差别
   git add directory_name              ##将内容添加到缓存区  
   git commit -m "annotation"          ##提交并添加备注，相当于一个游戏中的存档工作
   
   
   git log                             ##查看commit情况，如果消息太多，可以加上--pretty=oneline
   git reset --hard commit_id.         ##回到过去，HEAD^回到上一个版本，HEAD^^回到上上个版本
   git reflog													##查看命令历史
   
   
   git checkout -- file                ##当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时
   git reset HEAD file                 ##当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改再																                     git checkout -- file
   
   
   其中origin为远程仓库的名字
   git remote add origin git@server-name:path/repo-name.git   ##添加远程仓库 
   git remote rm origin 												  						 ##删除远程仓库
   git remote -v															 								 ##查看远程仓库的信息
   git push -u origin master											 						 ##第一次推送至远程仓库时需要使用-u
   git push origin master																	   ##后面推送用这个
   git clone git@server-name:path/repo-name.git						   ##将项目从远程仓库中下载下来
   
   
   
   git branch											 ##查看分支
   git branch <name>						  	 ##创建分支
   git checkout <name>			         ##切换分支
   git checkout -b <name>		       ##创建+切换分支
   git merge <name>						   	 ##合并某分支到当前分支
   git branch -d <name>				     ##删除分支
   
   
   
   ```



<img src="https://www.liaoxuefeng.com/files/attachments/919020037470528/0" alt="git-repo" style="zoom:150%;" />