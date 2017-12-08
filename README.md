# CommandNote
记录经常用到了一些命令

## GitHub上传文件大小不能超过100M，因此有时需要在commit时忽略掉一些库
在项目所在的根目录下。

1. touch  .gitignore     #创建gitignore隱藏文件  

2. vim    .gitignore     #编辑文件，加入指定文件

参考[https://github.com/github/gitignore](https://github.com/github/gitignore)

## Mac OS 10.12安全与隐私
sudo spctl —master-disable

## . ~/.nvm/nvm.sh

## 新建tag

1. git tag 名字 -m “注释”

2. git push origin tag名字

## 使用svn后，xcode修改文件，类名后面不显示**M**
在工作目录下执行：svn upgrade

## 查看gem的环境变量
gem env

## .bash_profile中增加永久路径
1. $ source ～/.bash_profile 打开根目录下的.bash_profile
2. 例如，将一个路径**/Users/zyjk_imac-penghe/.rvm/gems/ruby-2.2.0/bin/pod** 插入，

> export PATH:”/Users/zyjk_imac-penghe/.rvm/gems/ruby-2.2.0/bin/pod:$PATH”
结束编辑esc后，输入:wq保存。在终端输入命令:

3. $ source ～/.bash_profile  让这个配置文件在修改后立即生效

此时，再查看gem env发现SHELL PATH:列表中，增加了**/Users/zyjk_imac-penghe/.rvm/gems/ruby-2.2.0/bin/pod**这条路径。

参考[https://coolestguidesontheplanet.com/add-shell-path-osx/](https://coolestguidesontheplanet.com/add-shell-path-osx/)

## 更新一下gem版本
$ sudo gem update –system
