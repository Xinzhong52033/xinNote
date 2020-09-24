# git命令

1.第一次使用配置用户名

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

2.使用git管理本地项目

本地操作空间 : 电脑上保存代码的文件夹

暂存区 : 内存

本地仓库 : 只有本地仓库能和网络仓库连接

```git
git init #把文件夹初始化为本地仓库
git status #查看哪些文件没有放入暂存区 红色状态是没有放入的
#将没有放入暂存区的文件放入暂存区 成功以后文件时绿色状态
git add 文件名 #一次往暂存区添加一个文件
git add . #将所有没有加入暂存区的文件加入进去
git mit -m 解释说明 #把暂存区的文件加入到本地仓库
git log #查看当前版本之前的所有版本
git checkout 文件名称 #将暂存空间的文件覆盖本地操作空间的文件
git reset --hard id #回滚到提交版本的状态
git reflog #查看所有本地本库操作记录
#使用开发软件创建.gitignore 文件. 在文件中写上.gitignore 换行 和其它的不想上传的文件名
```

3.与github进行网络交互管理

```git
# 把网络仓库的连接放入别名origin中
git remote add origin https://github.com/Xinzhong52033/2007-1.git
# 把本地仓库的文件推送到网络仓库
 git push -u origin master
#在本地没有仓库的情况下 把网络仓库克隆
git clone https://github.com/Xinzhong52033/2007-1.git
#有本地仓库, 拿代码
git pull 网络库地址
```

4.分支

```
git branch #查看所有分支
git branch ucol(新分支名称) #创建新分支
git checkout ucol(分支名称) #进入分支
在当前分支账号下只能看到当前分支创建的文件
git merge #分支名称 当前分支合并另一个分支
git branch -d 分支名称 #删除已被合并的分支
git branch -D 分支名称 #不管分支是否被合并, 都删除
```

