# git远程仓库的操作
[本地仓库的操作在这里](book1.md)
## 生成ssh密钥
在bash中执行``` ssh-keygen -t rsa -b 4096 -C 你的邮箱```

邮箱最好是填写自己的邮箱
## 查看密钥
在bash中执行```cat ~/.ssh/id_rsa.pub```


这时会生成SSH密钥。
## 设置密钥的方法
打开github,打开settings，选择SSH and GPGkeys ，选择new ssh key,title随便写，key的文本就是刚才在bash中查看得到的密钥，最后add key
## 测试是否配对成功
在bash运行```ssh -T git@github.com```   


输入yes并继续。
## 详细操作
1. 在github上新建一个repository，然后复制ssh地址(**注意**一定是ssh地址，不是https地址，不然会被方方老师惨骂)
2. 然后在本地执行命令```git remote add origin git@xxxxxxx```   在执行命令之前要确保代码已经被commit过，不然会发生错误。origin在行业内是第一个仓库，后面的仓库可以自己改名，可以通过```git remote -v ```来查看自己配置了哪些远程仓库。
3. 最后运行```git push -u origin master```,就可以在github上的仓库中看到自己的代码了。


# git基本操作
## pull 
通过```git pull```可以拉去远程仓库代码到本地仓库已有分支

此过程可能会发生冲突，可以通过```git stash``` ```git stash pop```来避免，前者可以将没有commit的文件隐藏起来，后者可以将隐藏的文件拿出来。可以通过```git stash list```查看隐藏了哪些文件。
## clone
1. git clone git@????/xxx.git
   
   
   
   会在当前目录下创建一个xxx目录；xxx/.git是本地目录；clone后记得接cd xxx
2. git clone git@????/xxx.git yyy

   会在本地新建yyy目录，内容一样；记得cd yyy
3. git clone git@????/xxx.git .


   最后一个字符是点，有空格。不会新建目录，使用当前目录容纳代码.git；当前目录一开始要是一新目录；下载前要先cd要容纳代码的目录。
## push
通过```git push```可以上传本地仓库的代码到远程仓库。



git push -u origin main(因为**master**被**github**改成**main**了)推送本地仓库的main分支到远程仓库的main分支


gir push -f 可以强制上传（但是会删除文件）
#  code ~/.bashrc
可以通过此方法来缩写命令，如```alias ga="git add"```
# 目前就在饥人谷里学到这些，感谢老师们和班主任的帮助
