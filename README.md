# CommandNote
记录经常用到了一些命令

## GitHub上传文件大小不能超过100M，因此有时需要在commit时忽略掉一些库
在项目所在的根目录下。

1.touch  .gitignore     #创建gitignore隱藏文件  

2.vim    .gitignore     #编辑文件，加入指定文件

参考[https://github.com/github/gitignore](https://github.com/github/gitignore)

## Mac OS 10.12安全与隐私
sudo spctl —master-disable

## . ~/.nvm/nvm.sh

## 新建tag

1.git tag 名字 -m “注释”

2.git push origin tag名字

## 使用svn后，xcode修改文件，类名后面不显示**M**
在工作目录下执行：svn upgrade


