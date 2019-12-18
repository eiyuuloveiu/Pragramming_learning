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

1. github使用ssh密钥的好处

   git可以通过https协议或者git协议进行远程下载，但是https协议每次push和pull时都需要输入用户名和密码，而git协议通过ssh密钥后不需要密码即可push和pull

2. git的安装和卸载

   ```
   brew install git  ##使用brew命令安装git
   which -a git      ##列出 git命令所在的位置
   ```

   

3. git的使用

   ```
   git --version     ##查看git的版本
   
   ```

   



