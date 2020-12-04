# git命令

**git bash模拟的是Linux操作环境**

#### **基础Linux操作命令**

````linux
cd 进入当前打开gitbush的根目录
cd /盘符 进入那个盘
cd filaname 进入文件夹
mkdir 创建问价夹
ls 显示当前列表. .赢藏文件默认不显示
ls -a 显示隐藏文件
ll 显示所有文件, 包括目录和文件
rm -rf 文件名   删除文件夹 
rm  -rf * 删除所有文件 不会删除.git
touch 文件名称 建立新文件
vim filename linux内置编辑模式,i输入,esc退出编辑 然后输入: wq 保存文件,退出编辑模式  
cat filename 可以查看文件内的内容
````

#### **第一次使用配置用户名**

告诉项目经理代码提交者信息

```git
#配置用户名
git config --global user.name "zhongxin"
#配置邮箱
git config --global user.email "352730038@qq.com"
#查看配置列表
git config --list
# 代表注释
q #结束
clear #清屏
```

#### **使用git管理项目**

本地操作空间 : 电脑上保存代码的文件夹

暂存区 : 内存

本地仓库 : 只有本地仓库能和网络仓库连接

```git
新建项目
git init #把文件夹初始化为本地仓库
管理老项目
git clone #地址
git status #查看哪些文件没有放入暂存区 红色状态是没有放入的
#将没有放入暂存区的文件放入暂存区 成功以后文件时绿色状态
git add 文件名 #一次往暂存区添加一个文件
git add . #将所有没有加入暂存区的文件加入进去
```

#### **忽略文件,设置不想提交到本地仓库的文件**

````linux
code .gitignore 直接使用vscode创建文件
在.gitignore中写 文件名称, 该文件不会进入working space就是修改了也不会被提交
a.html 改文件不会被提交
*.html *代表所有 所有html文件不会被提交 命令是从上往下执行
!a.html 除了a.html以外所有的文件都不会被提交
/foldername 忽略文件下的文件
````

#### **commit提交到本地仓库**

````
git commit -m 解释说明 #把暂存区的文件加入到本地仓库
删除本地仓库的文件
git rm filename 删除本地仓库的文件, 默认会把本地文件夹的文件也一起删除
git rm --cached filename   !!!!!版本库放错文件了, 但是本地不上删除
修改本地仓库的文件的名称
git mv oldfilename new filename 将版本库文件名修改, 默然也会将本地文件夹的文件名称修改了
````

#### **查看记录**

````linux
git log #查看提交过的版本信息
git log -p 查看提交版本修改过的详细信息
git log -p 数字 显示第几次提交的信息
git log --oneline log信息只显示一hang
git log --name-only 只显示每次log更改的文件名
git log --name-status 只显示更改的文件的名称和更改类型
````

#### **修改日志提交信息**

````linux
修改最新一次已经提交的信息
git commit --amend 进入编辑模式后 修改后保存
进行的新操作保存在最新一次的提交信息内
git commit --amend 
````

#### **管理暂存区的文件**

````linux
当我们第一次将文件提交到暂存区又后悔的时候, 返回到working状态
"git rm --cached <file>..." to unstage
第二次的时候
git reset HEAD a.php
git restore --staged <file>..." to unstage 有提示
希望回到上一次提交到本地仓库的文件状态
"git restore <file>..." to discard changes in working directory
git restore 是对checkout 的新划分, 
````

#### **alias命名别名提高工作效率**

还可以配置系统别名 

````linux
 git config --global alias.a add
可以将git a代替 git add使用
````

#### **分支**

````linux
git branch 查看分支
切换分支
git cheackout branchName 或者
git switch branchName
创建并切换到新分支
git switch -c 新分支名称 或者
git checkout -b 新分支名称
````

#### **分支的合并和删除**

````linux
git merge 分支名称 合并分支
git branch -d ask 分支合并以后就没有意义了, 用该删除分支, 需要在主分支上执行
````

#### **冲突**

````linux
不同的分支同时修改了相同的文件, 合并的时候回产生冲突
vim 产生冲突的文件 人为修改以后:wq保存 , 冲突解决
修改冲突文件后再 add . git commit -m 分支就合并完成了
````

#### **分支的其它命令**

````linux
git branch --merge 查看已经合并的分支
git branch --no-merged 查看没有合并的分支
已经合并的分支可以直接删除, 没有合并的分支不再继续使用,yong-d删除会提醒没有合并, 坚持删除用git branch -D 
````

#### **git 的工作流**

 一般情况是master稳定创建一个develop分支, 再在devolop分支创建其它工作分支, 最终merge 到master分支上

与github进行网络交互管理**

#### stash**临时储存区**

当一个分支的文件已经 add 提交到stating工作区, 但是还没有commit的时候, 不能切换到其它分支,实际开发中, 就是现在这个开发到一半, 现在需要暂时去操作其它更重要分支的工作

````linux
git stash 暂存
git stash apply 恢复暂存
git stash apply stash@{n} 恢复第几个缓存
git stash list 查看缓存区
git stash drop stash@{n} 删除缓存区
git stash pop 恢复列表最新的一个缓存并删除缓存
````

#### TAG声明项目阶段

````linux
就某一个阶段的总结, 是相对稳定的版本
git tag
````

#### 生成zip代码发布压缩包

````linux
git archive(归档) master --predix='hd/(打包的文件目录)' --forma=zip > hdcms.zip(打包的文件名称)
````

#### 远程推送

```git
# 把网络仓库的连接放入别名origin中
git remote add origin https://github.com/Xinzhong52033/2007-1.git
#查看但那个钱origin值
git remote show origin
# 修改origin
git remote rm origin 先移除
git remote add origin xxx 再添加  或者
git remote set-url origin  新的地址
# 把本地仓库的文件推送到网络仓库
git push -u origin master 
#-u 初次使用-u 可以记录origin master 之后就可以直接使用git push 代替git push -u ....
#在本地没有仓库的情况下 把网络仓库克隆
git clone https://github.com/Xinzhong52033/2007-1.git
#有本地仓库, 拿代码
git pull 网络库地址
```

**ssh创建连接**



#### 本地分支与远程分支同步

创建本地分支成功后, 推送远程仓库会有自动创建新分支

#### 新加入下载项目进入分支

````linux
查看本地和远程所有分支
git branch -a
首先下载整个文件
git clone https://github.com/Xinzhong52033/xinNote.git
然后拉分支
git pull origin 分支名:分支名
````

#### 远程分支的合并

在本地完成merge后, 再push一次就可以

#### 删除远程分支

````linux
git push origin --delete 分支名称 删除远程分支
git branch -d 分支名称 删除本地分支
````

