@[TOC]
>git是一个分布式版本控制工具。

### 安装与配置

1. 安装

   [git官方下载地址](https://git-scm.com/downloads)

2. 配置

   > 在使用 git 前，需要告诉 git 你是谁，在向 git 仓库中提交时需要用到。

   * 配置姓名(命令提示符|git Bash)

     ```bash
     git config --global user.name shiqi #shiqi 名字
     ```

   * 配置邮箱

     ```bash
     git config --global user.email shiqiverycool@163.com 
     ```

   * 查看配置信息

     ```bash
     git config --list 
     ```

3. git的工作流程

   > 工作区→暂存区→仓库区

   * 工作区：平时存放项目代码的地方
   * 暂存区：用于临时存放你的改动
   * 仓库区：安全存放数据的位置，里面有提交的所有版本的数据。

### git的使用

#### 本地仓库命令

1. 初始化git仓库

   ```bash
   git init
   ```

2. 查看文件状态

   ```bash
   git status
   ```

3. 将文件添加到暂存区

   ```bash
   git add index.js #指定文件
   git add .        #所有文件 注意符号.
   ```

4. 将暂存区的文件提交到仓库

   ```bash
   git commit -m '提交描述'
   ```

5. 查看提交记录

   ```bash
   git log
   ```

6. 版本回退

   ```bash
   git reset --hard 版本id
   ```

#### 分支命令

> 使用分支，可以让我们从开发主线上分离出来，以免影响开发主线

* 主分支（master）：第一次向 git 仓库中提交更新记录时自动产生的一个分支。
* 开发分支（develop）：作为开发的分支，基于 master 分支创建。
* 功能分支（feature）：作为开发具体功能的分支，基于开发分支创建

1. 查看分支

   ```bash
   git branch
   ```

2. 创建分支

   ```bash
   git branch 分支名
   ```

3. 切换分支

   ```bash
   git branch 分支名
   ```

4. 分支合并

   ```bash
   git merge 分支名
   ```

5. 删除分支

   ```bash
   git branch -d 分支名
   ```

#### 远程仓库命令

1. 克隆仓库

   ```bash
   git clone 仓库地址
   ```

2. 推送分支

   ```bash
   git push 仓库地址 分支名
   ```

3. 拉取分支

   ```bash
   git pull 仓库地址 
   ```

4. 创建仓库别名

   ```bash
   git remote add 仓库别名 仓库地址  #创建仓库别名
   ```

5. 记忆仓库地址与分支(之后提交可简写为git push)

   ```bash
   git push -u 仓库地址或仓库别名 分支名
   ```

6. 强制推送

   ```bash
   git push -f 仓库地址 分支名
   ```

7. 克隆指定分支

   ```bash
   git clone -b 分支名 仓库地址
   ```

### SSH密匙

> 请确保已经配置git中的``user.name``与``user.email``。

1. 生成ssh密匙

   ```bash
   ssh-keygen -t rsa -C shiqiverycool@163.com
   ```

   * 生成的密匙文件在``C盘→用户→.ssh文件夹``中。
   * ``id_rsa``：私有密匙 ``id_rsa.pub``：公有密匙

2. 将ssh密匙添加到远程仓库(一般为设置→安全设置)

   * 打开``id_rsa.pub``(公有密匙)，将内容放在远程仓库新建的ssh密匙中即可

### GIT忽略清单

> 将不需要被git管理的文件名字添加到此文件中，在执行git命令的时候，git就会忽略这些文件。

git忽略清单文件名称：**.gitignore**

| 忽略规则     | 解释                                           |
| ------------ | ---------------------------------------------- |
| ``*.a``      | 忽略所有以``.a``为扩展名的文件 \| 文件夹       |
| ``!index.a`` | 不忽略名为``index.a``的文件，即使设置了``*.a`` |
| ``/a/``      | 忽略``a``文件夹                                |
| ``dist.zip`` | 忽略``dist.zip``文件                           |