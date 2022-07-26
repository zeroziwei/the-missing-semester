## VIM 使用教程

### 1、使用帮助文件📕

在linux 中你必然要学会是，哪里不会help哪里，哪里不会man哪里

- 进入 `vim` 之后，我们面对的是正常模式

- 输入半角 : 进入 `命令行` 模式

- 什么不会，就

   

  ```
  :help
  ```

   

  什么

  - 比如说 `:qa` 不会
  - 就 `:help` 这个 `:qa`
  - 输入 `:help :qa`
  - `:help` 的对象是 `:qa`，中间留了一个空格
  - 回车 之后执行命令

2、vim 6种基本模式

- 正常模式 (Normal mode)
  - 也叫默认模式。
  - 进入 vim 时默认的模式所有输入的键都直接对应着命令
  - 也被叫做命令模式.
- 插入模式 (Insert mode)
  - 任何键盘录入都会插入到当前文档

* 可视模式 (Visual mode)
  * 很像正常模式
  * 但是移动命令会改变选中的一块高亮区域
  * 执行的命令会对选定范围进行
* 选择模式 (Select mode)
  * 可以用鼠标或光标键高亮选择文本
  * 任何输入都会替换选择的高亮文本
  * 并进入插入模式
* 命令行模式 (Command-Line mode)
  * 可以窗口下方执行一条命令 
  * 一般是通过 : 执行单行命令
  * 通过 / 和 ? 进行搜索
* Ex mode (多行命令执行模式)
  * Ex 指的是 Execute
  * 在 Normal 正常模式下使用 gQ 进入
  * 使用 :visual 退出

### 一些manual用法

- 帮助文件的正确打开方式
  - `:h`
  - :h CTRL-C ctrl快捷键都是这样的
- 在文档中使用鼠标
  - `set mouse=a`
  - 建议不用鼠标
- 使用全键盘方式跳入跳出超链接
  - ctrl+]
  - ctrl+o
- 帮助文件的两种手册
  - 用户帮助手册
  - 引用帮助手册

### 插入模式

- 我们这次深入了i命令
  - i 在当前的光标之前插入
  - I 在本行文本的最前面插入
- 还有一些常用的编辑命令
  - . 重做
  - u 撤销
  - ctrl+r 还原