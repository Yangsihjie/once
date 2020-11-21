# GIT : 分布式版本控制软件

## 1.分布式版本控制

##### 1.1 IT行业最为广泛使用。程序员,方便控制版本，更好的开发

```
安装window  Mac等~~

查看是否安装成功输入：$git  --version

如何利用git帮助我们做版本控制

1--进入要管理的文件夹

​    1.1--命令 Git init 进入初始化

​    1.2--Git status  检测当前文件夹里文件状态   红色为：新增的文件/修改了的原始文件  绿色为已经开始管理  

​    1.3--Git add 要管理的文件

​    1.4--Git add . 管理当前文件下所有文件

​    1.5--Git commit -m '引号内为描述信息'

​    1.6--当文件发生变化时  通过Git status 来检测

​    1.7--继续通过Git add 重新管理

​    1.8--然后Git commit 重新提交

​    1.9--Git log  查看历史版本

2--初始化（提名）

​     2.1--Git init

3--管理

​     3.1--Git status

4--生成版本

​      4.1--Git commit -m '引号内为描述信息'

5--配置个人信息邮箱等
```

#### 1.2 可以利用版本控制--来做版本回滚

```
1.0--回到之前版本
        --命令 Git reset --hard版本号  //回到修改之前版本
1.1--Git reflog //回滚到之后版本
        --命令 Git reset --hard版本号  //回到修改之后版本
1.2--回到修改前
        --命令 Git checkout 回到修改前
        
```

# 2.分支

```
2.1 Git branch //查看当前所在分支
2.2 Git branch 分支名称  //创建分支
2.3 Git checkout 分支名称 //切换分支
2.4 Git merge 要合并的分支 //分支合并（注意：切换分支在合并）
2.5 Git branch -d 分支名称 //删除分支
```

# 3.Github

* 3.1 远程仓库起别名

```
Git remote add 地址命 远程仓库地址
```

* 3.2  向远程仓库推送代码

```
Git push -u 地址命 分支
```

* 3.3 克隆远程仓库代码

```
Git clone 远程仓库地址（内部已实现 Git remote add 地址命 远程仓库地址）
```

* 3.4 切换分支

```
Git checkout 分支
```

* 3.5 切换分支

```
Git checkout 分支名
```

* 合并分支

```
Git merge 分支名
```

* 修改代码

* 提交代码

```
Git add .
Git commit -m 'XXXX'
Git push 仓库名 分支
```

* 下载代码更新

```
Git checkout （分支名）
Git pull 地址名 （分支名）
继续开发
提交代码
Git add .
Git commit -m '项目描述'
Git push 地址名 （分支名）
```

* liunx操作命令

  ```
  进入目录:cd 目录名称        返回上级目录:cd ..
  查看目录内容:ls            查看隐藏内容:ls -a
  创建文件夹:mkdir 文件名称      创建文件:touch 文件名
  删除文件或文件夹:vm -rf 文件名或文件夹 
  查看文件所在目录:pwd
  查看本地与远程仓库连接:git remote -v
  初始化git文件:git init        提交文件:git commit
  添加暂存区:git add (.是全部文件 文件名是单个)
  查看分支:git branch        c创建分支:git branch 分支名
  切换分支:git checkout       合并分支:git merge
  删除分支:git branch -d 分支
  ```

  



