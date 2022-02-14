# 安装
百度找教程
# 创建仓库
百度
# 上传代码到github
- 1、在项目中新建.gitignore文件配置上传时候需要忽略的的文件
![图片1](/img/1.png)
- 2、打开终端输入以下命令
初始化git项目
```
git init
```
把项目文件提交到栈存区
```
git add .
```
```
git commit -m 第一次上传文件
```
```
git branch -M main
```
其中 <<Your token>Your token>:是github上生成的认证身份token
```
git remote add origin https://<Your token>@github.com/Your Name/study-git.git
```
把项目远程推送到git仓库
```
git push -u origin main
```

# 怎么找到所有的操作记录

查看所有的提交日志
```
git log
```
查看某个人的改动记录
```
git log --author='MrLiPeter'
```
![图片2](/img/2.png)

# 配置用户名邮箱
```
git config --global user.user.name 'MrLiPeter'
```
```
git config --global user.email '599490688@qq.co'
```
查看是否配置成功
```
git config --global --list
```
# 如何修改项目中的文件
查看当前项目的状态
```git
git status
```
![图片2](/img/3.png)
```
git add .
```
```
git commit -m 修改文件测试
```
# 如何删除项目中不需要的文件
```
git rm demo2.html
```
删除后把项目文件添加到暂存区，再commit

# 如何给文件重命名
把demo3.html 重命名为home.html
```
git mv demo3.html home.html
```
# 移动文件
把demo4.html移动到shop文件夹下面
```
git mv demo4.html shop
```
把demo4.html移动到shop文件夹下面,并重命名为shop.html
```
git mv demo4.html shop/shop.html
```
# 查看文件前后变化
- 查看某个文件的前后变化
```
git log -p shop/demo4.html
```
- 先查询出前一次提交的commiItD再查看修改了哪些内容
```
git log --pretty=oneline shop/demo4.html
```
执行后会看到一串commiItD:a5a7e670a08dc9926e2ed6813a45d4ba6c80a659
```
git show a5a7e670a08dc9926e2ed6813a45d4ba6c80a659
```
# 误操作的情况下进行一键还原
还原到上一次提交的状态
```
git checkout -- shop/demo4.html
```
找到与最后一次提交不同的地方
```
git diff
```
# 不再追踪时如何实现撤销追踪操作
执行了git add .后文件会提交到暂存区，git会对文件进行追踪
```
git reset HEAD shop/demo4.html
```
# 版本回退
- 整个项目回退
方法一：回退到上一个版本,一个^代表回退一个版本，两个代表回退两个
```
git reset --hard HEAD^
```
方法二：通过git log 拿到所有的commitID制定回退到某个版本
```
git reset --hard commitID
```
- 只回退某个文件
```
git checkout commitID -- version.html
```
# 标签管理
在本地创建标签(默认加载最新一次的commit)
```
git tag v1.0
```
检查标签是否创建成功
```
git tag
```
```
git log
```
给指定的某次commit添加标签
```
git tag v0.5 commitId
```
删除标签
```
git tag -d v0.5
```
把标签推送到远程仓库
```
git push origin v1.0
```
# 新建、切换、删除分支
新建分支
```
git branch dev
```
查看有多少分支
```
git branch
```
切换分支
```
git checkout dev
```
删除分支
```
git branch -d test
```
注意：**无法删除当前所在分支**
    **分支有commit操作无法删除(但能被强行删除)**

创建新分支并切换到新分支
```
git checkout -b test
```
强行删除分支
```
git branch -D test
```
# 合并分支
