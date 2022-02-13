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