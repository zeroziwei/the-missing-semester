## Date model 

​	

### 一、Git 与 GitHub 的来历

Linux 之父 Linus 在 1991 年创建开源的 Linux 操作系统之后，多年来依靠全世界广大热心志愿者的共同建设，经过长足发展，现已成为世界上最大的服务器系统。系统创建之初，代码贡献者将源码文件发送给 Linus，由其手动合并。这种方式维持多年后，代码量已经庞大到人工合并难以为继，于是深恶集中式版本控制系统的 Linus 选择了一个分布式商业版本控制系统 BitKeeper，不过 Linux 社区的建设者们可以免费使用它。BitKeeper 改变了 Linus 对版本控制的认识，同时 Linus 发现 BitKeeper 有一些不足，而且有个关键性的问题使之不能被广泛使用，就是不开源。

在 2005 年，BitKeeper 所在公司发现 Linux 社区有人企图破解它，BitKeeper 决定收回 Linux 社区的免费使用权。Linus 对此事调解数周无果，找遍了当时已知的各种版本控制系统，没有一个看上眼的，一怒之下决定自己搞一个。Linus 花了十天时间用 C 语言写好了一个开源的版本控制系统，就是著名的 Git。

2007 年旧金山三个年轻人觉得 Git 是个好东西，就搞了一个公司名字叫 GitHub，第二年上线了使用 Ruby 编写的同名网站 GitHub，这是一个基于 Git 的免费代码托管网站（有付费服务）。十年间，该网站迅速蹿红，击败了实力雄厚的 Google Code，成为全世界最受欢迎的代码托管网站。2018 年 6 月，GitHub 被财大气粗的 Microsoft 收购。2019 年 1 月 GitHub 宣布用户可以免费创建私有仓库。根据 2018 年 10 月的 GitHub 年度报告显示，目前有 3100 万开发者创建了 9600 万个项目仓库，有 210 万企业入驻

### 二、获取 Git 仓库

#### 1. 从目录新建

> git init

从根本上来讲 Git 是一个内容寻址（content-addressable）文件系统，并在此之上提供了一个版本控制系统的用户界面。

#### 2. 克隆现有的仓库

克隆仓库的命令是 git clone <url> 。 比如，要克隆 Git 的链接库 libgit2，可以用下面的命令：

> git clone https://github.com/libgit2/libgit2

如果你想在克隆远程仓库的时候，自定义本地仓库的名字，你可以通过额外的参数指定新的目录名

```shell
$ git clone https://github.com/libgit2/libgit2 mylibgit
```

当我们在 GitHub 上创建一个仓库时，同时生成了仓库的默认主机名 origin，并创建了默认分支 master。GitHub 可以看成是免费的 Git 服务器，在 GitHub 上创建仓库，会自动生成一个仓库地址，主机就是指代这个仓库，主机名就等于这个仓库地址。克隆一个 GitHub 仓库（也叫远程仓库）到本地，本地仓库则会自动关联到这个远程仓库，执行 `git remote -v` 命令可以查看本地仓库所关联的远程仓库信息：

> git remote -v 查看远程主机

![](/home/orange/图片/2022-07-21 23-50-49 的屏幕截图.png)

### 三、 仓库的三大区域

![此处输入图片的描述](https://doc.shiyanlou.com/document-uid310176labid9805timestamp1548755776759.png)

### 4、配置个人信息

- `user.email`：写入你自己注册 GitHub 账号的邮箱
- `user.name`：你自己的 GitHub 账号名字

> git config -l 查看配置信息

![img](https://doc.shiyanlou.com/document-uid310176labid9805timestamp1548755913772.png)

完成后，系统自动生成 Git 的配置文件，就是主目录中的隐藏文件 `.gitconfig` 

### 

### 5、记录每次更新到仓库

> git add 建立对文件的追踪

​	现在我们的机器上有了一个 真实项目 的 Git 仓库，并从这个仓库中检出了所有文件的 工作副本通常，你会对这些文件做些修改，每当完成了一个阶段的目标，想要将记录下它时，就将它提交到仓库。

​	工作目录下的每一个文件都不外乎这两种状态：**已跟踪** 或 **未跟踪**。 已跟踪的文件是指那些被纳入了版本控制的文件，在上一次快照中有它们的记录，在工作一段时间后， 它们的状态可能是未修改，已修改或已放入暂存区。

| 已跟踪 | 未修改 | 已修改 | 放入暂存区 |
| ------ | ------ | ------ | ---------- |
| 未跟踪 |        |        |            |



### 6、检查当前文件状态	

可以用 `git status` 命令查看哪些文件处于什么状态。 如果在克隆仓库后立即使用此命令，会看到类似这样的输出：

```she
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```

### 7、提交暂存区的修改

> git commit -m "Message"

![](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722004948367.png)



> git log 查看提交记录

![img](https://doc.shiyanlou.com/document-uid310176labid9805timestamp1548755946170.png)

提交后，暂存区的修改被清空，执行 `git log` 查看提交记录，紫色框中的十六进制序列号就是提交版本号，这是很重要的信息，每个提交都有自己单独的版本号，就像公民身份证号一样：

> git branch -avv  查看全部分支信息：

![image-20220722005311071](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722005311071.png)

> git push 推送 需要下载的就是SSH的版本

### 8、版本回退

> git reset --soft HEAD^ 撤销最近的一次提交，将修改还原到暂存区
>
> `--soft` 表示软退回，对应的还有 `--hard` 硬退回
>
> `HEAD^` 表示撤销一次提交，`HEAD^^` 表示撤销两次提交，撤销 n 次可以简写为 `HEAD~n`。

软退回一个提交后执行 `git branch -avv` 命令查看分支信息：![image-20220722011405648](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722011405648.png)

从版本号可知 提交到远程服务器版本的并没有发生回退，本地的版本回退了。

执行 `git status` 查看仓库状态，果然上一个提交中的修改全部扔回了暂存区：

![image-20220722011659636](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722011659636.png)

然后你可以再次修改提交了

### 9、处理 commit 时间线分叉

执行 `git status` 和 `git branch -avv` 查看仓库状态和分支状态

![image-20220722013029818](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722013029818.png)

![image-20220722013059979](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722013059979.png)

> git push -f 

可以看到本地仓库的 master 分支与远程仓库的 origin/master 分支在提交版本上有了冲突，又叫做提交时间线分叉。因为刚才的提交操作不是基于远程仓库 origin/master 分支的最新提交版本，而是撤回了一个版本。这种情况下也是可以将本地 master 分支推送到远程仓库的，需要加一个选项 `-f` ，它是 `--force` 的简写，这就是强制推送:

![image-20220722013203398](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722013203398.png)

执行 `git branch -avv` 看一下分支信息，本地 master 与远程 master 的版本号一致，

![image-20220722013340453](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722013340453.png)

![image-20220722013411867](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722013411867.png)

> git reflog 

![image-20220722013546874](/home/orange/snap/typora/57/.config/Typora/typora-user-images/image-20220722013546874.png)

> git relog --hard [版本号] / HEAD@{num}

如果记不清版本号，也可以根据上图第 3 行的信息，执行 `git reset --hard HEAD@{2}` 命令，其中 `HEAD@{2}` 就是上图第 3 行第 2 列所示，这个命令的意思是回到当前分支最近两次提交版本变化前：

### 为 Git 命令设置别名

有些命令的重复度极高，比如 `git status` 和 `git branch -avv` 等，Git 可以对这些命令设置别名，以便简化对它们的使用，设置别名的命令是 `git config --global alias.[别名] [原命令]`，如果原命令中有选项，需要加引号。别名是自定义的，可以随意命名，设置后，原命令和别名具有同等作用。操作如下：