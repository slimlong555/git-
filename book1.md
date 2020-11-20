# git本地仓库的操作
## git的配置
一般来说就只有六行代码需要配置一下
```
git config --global user.name 你的英文名
git config --global user.email 你的邮箱
git config --global push.default simple
git config --global core.quotepath false
git config --global core.editor "code --wait"
git config --global core.autocrlf input
```
**注意**：上面的英文名和邮箱跟 GitHub 没有关系。
可以跟 GitHub 的用户名和邮箱保持一致



# git新建代码库
## git init
在当前目录新建一个Git代码库

## git init [project-name]
新建一个目录，将其初始化为Git代码库
# 增加和删除文件
## git add + 路径
选择哪些变动是需要提交的；路径可以是绝对路径，相对路径，.和*，不标记是无法被提交的。

## git add [file1] [file2] ...
添加指定文件到暂存区
## git add [dir]
添加指定目录到暂存区，包括子目录
## git add .
添加当前目录的所有文件到暂存区
## git mv [file-original] [file-renamed]
改名文件，并且将这个改名放入暂存区
## git rm [file1] [file2] ...
删除工作区文件，并且将这次删除放入暂存区
# 代码的提交
## git commit -m +提交的原因 
提交并说明提交的理由，**注意**：理由里面有空格的要用引号包起来。
## git commit -v 
可以帮助我回顾我刚刚改了什么东西而且会迫使我吧提交理由写的跟更详细一些。可以通过git log查看。
### **多次提交的方法**:
1. git add .
2. git commit -v 

每次重复着两个操作即可，不要少写.和不要少写空格
# 其他操作
## git status 
查看改变的东西有没有提交
## git reset --hard ?????? 回滚版本
??????是提交号的前六位
**注意**：请一定要确保所有的代码都commit了，因为这个操作会使没有commit的自动消失。没有add过的文件不会被删除
## git reflog
查看所有历史，可以帮助返回之前的版本
## git merge 
可以将另一个分支合并到当前分支
# 分支
## git branch
列出所有本地分支
## git branch -r
列出所有远程分支
## git branch -a
列出所有本地分支和远程分支
## git branch X（X可以是任意单词）
新建一个分支，但依然停留在当前分支
在哪个分支，代码就会存放在哪个分支
## git checkout X
切换到指定分支，并更新工作区
# 代码冲突
1. 在合并时会发现**conflict**提示
2. 使用 git status -sb可以查看哪些文件冲突了
3. 依次打开文件
4. 搜索四个等于号
5. 可在上下两部分选择要保留的代码，可以都选，删除不要的代码，删除{====,<<<<,>>>>}这些标记符号
6. git add 对应文件
7. 依次解决文件，没有问题之后，commit




