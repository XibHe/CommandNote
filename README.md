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

3. git tag -l  查看所有tag

## 删除tag

1. git tag -d tag名称   删除本地tag 

2. git push origin --delete tag "tag名称"  删除远程tag

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

## 每次部署执行hexo deploy都需要输入密码

每次部署执行hexo deploy都需要输入密码，但我明明已经在Github上设置了项目的Deploy keys了。用了一年多了，但最近突然就需要输入密码。最后，修改配置文件**_config.yml**中的deploy，将**repo: git@github.com:XibHe/XibHe.github.io**改为**repo: https://github.com/XibHe/XibHe.github.io**就解决了这个问题。

参考：

[https://segmentfault.com/a/1190000005125610](https://segmentfault.com/a/1190000005125610)

[https://www.jianshu.com/p/f8b6717e1238](https://www.jianshu.com/p/f8b6717e1238)

## 关于使用 cocoapods 导入 Masonry 后，编译报错的问题

```objectivec
-[UITextField mas_makeConstraints:]: unrecognized selector

```

在 *Xcode* ---> *Build Settings* ---> *Other Linker Flags* 增加环境变量  

```
$(inherited)
```

## pod install 时报错 ruby_executable_hooks:15:in `eval'

如下，

```
from /Users/mac/.rvm/rubies/ruby-2.2.0/lib/ruby/site_ruby/2.2.0/rubygems/dependency.rb:320:in `to_spec'

from /Users/mac/.rvm/rubies/ruby-2.2.0/lib/ruby/site_ruby/2.2.0/rubygems/core_ext/kernel_gem.rb:65:in `gem'

from /usr/local/bin/pod:22:in `'

from /Users/mac/.rvm/gems/ruby-2.2.0@global/bin/ruby_executable_hooks:15:in `eval'
```

解决方法，安装最新的ruby运行这些命令。具体步骤，依次输入以下命令：

* rvm install 2.2.10

* rvm use 2.2.10

* rvm use 2.2.10 --default //!设置2.2为运行的默认版本!

一旦安装在您的系统中，请执行以下步骤：

* sudo gem install activesupport -v 4.2.6

* sudo gem install cocoapods

* pod setup


## add nvm environment variable "This loads nvm"

* $ sudo vi ~/.bash_profile
* 插入并新增

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

* :wq
* $ source ～/.bash_profile

参考: 

[Unterminated substitute pattern #1083](https://github.com/creationix/nvm/issues/1083)

## nvm 管理不同的 node 版本

> nvm ls-remote  查看可用版本
> 
> nvm ls  查看当前可用版本
> 
> nvm use <version> 切换版本

不过此时，当新建一个shell窗口时，输入 node -v 当前版本号仍然是以前的。
这是因为利用 nvm use 指令只会在当前的shell生效，当你开了新的shell就会发现$PATH的值的值已经不包含刚才设定的node目录了。

要解决这个问题需要利用命令：

> nvm alias default <version>

来设置一个预设的node版本。此时，再开启一个新的shell窗口，就能直接看到修改后的shell版本了。

参考：

[mac中利用NVM管理不同node版本的方法详解](http://www.jb51.net/article/127739.htm)









 

