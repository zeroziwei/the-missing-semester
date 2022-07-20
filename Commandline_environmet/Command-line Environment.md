## Command-line Environment

### First. Job control

​	how to stop a program 

1. ctrl c : send  a SINGINT 
2. ctrl  \ : send a SIGTERM
3. SIGUP : hang up  if ssh teminal
4. ctrl z : SIGSTOP
5. you can also man signal

### Second. Teminal Multplexeis

tmux 终端多路复用器

session 

​	windows 就是浏览器中的一个tab

​		panes

ctrl + b + c  create a new window

ctrl+ b + p  go up to previous windows(在windows之间游走)

ctrl + b + n 				next

ctrl + b + nums

ctrl + b + " 垂直分割窗格

ctrl + b + % 左右分割窗格

> - `Ctrl+b ,`：窗口重命名。

ctrl + b + 方向建  在panes之间游走

ctrl + b + z zoom 



### There. Dotfiies

shell 是基于点文件来配置他自己的

其实vim 也是  .vimrc 在启动时应加载的说明，以便保留所需

### Four Remote Machines

### alias 

映射短字符为长字符

> alias ll="ll -lah"

> alias mv="mv -i "

> alias mv 