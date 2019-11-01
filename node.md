# 第一天  git和github

- git:版本控制工具

- github：网站、远程代码管理仓库、贵圈基友平台


## 集中式  分布式
     集中式缺点：
          必须联网、比较慢、都是用一个中央服务器，有可能会造成数据丢失
     
     分布式：
          不用联网就能进行版本控制，速度快


## 初始化版本控制状态
1. 找到要控制的文件目录
2. 鼠标右键，找到git bash here
3. 打开控制台，输入git init

     版本控制都是基于.git这个隐藏文件的，如果不小心把.git文件删除，就不能进行版本控制

     查看git状态
          git status
     通过Tab键补全文件

     通过ll或者ls查看目录的文件

     通过上下键去切换刚才输入的命令

     工作区到暂存区
         
          git add  指定文件名
          git add . 把当前目录所有文件都放到暂存区
     暂存区到版本区
         
          git commit -m '注释(你能直接识别的注释即可)'     
     快速把工作区到版本区（已经被管理过的文件）

          git commit -a -m ''
     注意：
          上面这个命令，前提条件是文件已经提交过一次才可以使用

     查看版本：
          git log
          git reflog （操作的多的用这个）
     
     查看每个区域的不同点：
          工作区和暂存区的区别：
               git diff
          工作区和版本区的区别
               git diff master
          暂存区跟版本区的区别：
               git diff --cached

## 设置作者信息

- 设置邮箱   git config --global user.name "你的名字(英文的)"
- 设置用户名  git config --global user.email "你的邮箱(能够收到右键的邮箱)"

## 创建过滤指定文件
- 创建一个.gitignore的文件
- touch .gitignore (创建文件) 
- 配置过滤项 
      /create.txt
      node_modules/

     - 如果说配置不起作用，可以先把之前的操作清除一下，在操作
         
          清楚命令
          git rm -r --cached 

     撤销回滚：
          git reset --hard 版本ID 
     
## github


     1.在github上创建一个项目
     2.绑定密钥
          ssh-keygen -t rsa -C "your_email@example.com"
          检测是否绑定（在联网的情况下）
          ssh -T git@github.com

     3.确定版本库是最新的（没有东西可提交了）
     4.查看远程仓库
          git remote -v (使用git init的时候是查不出东西的)
     5.添加远程仓库
          git remote add origin(这个名字是可以改变的)
     
     6.git pull origin master(保证能够成功上传，进行远程和本地相合并)

     7.git push origin master 上传（第一次会出现让你输入用户名和密码）

第二种方式     
     1.先在远程仓库中创建一个项目
     2.git clone 项目的地址
     3.git add .      git commit -m ''
     4.git push origin master  
## node
     NPM 跟着node安装一起安装下来的模块

     NPM 是目前时间上最大的资源管理平台

     Yran 最快的资源管理平台

     创建项目 
          npm init -y 会生成一个package.json的文件，这个文件里面放的是所有的项目配置依赖

     如何下载资源？
          npm install 资源名
               -g 全局安装
               -S 项目依赖
     下载下来的时候会自动生成一个node_modules的文件夹，文件夹中放的就是你需要的资源

      npm uninstall 删除安装程序       

