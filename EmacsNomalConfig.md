# 1. Eslip语法

#### concat 连接字符串

#### global-set-key 绑定M-x命令到按键
(global-set-key [f1] 'whitespace-newline-mode)  显示行末的空格

#### load 加载配置文件

#### require 加载配置模块（即配置文件中有provide xxx 来声明模块）

#### setenv getenv 设置和获得环境变量的值

#### setq   setq-default  setf
setq用于给symbol的reference设置，而setf用于设置list或者array的reference.    
(setq default-tab-width 4)  `设置tab的默认长度为4个空格`    
如果一个变量是“buffer-local”的，setq只是修改当前buffer的，setq-default修改global的，如果这个变量不是“buffer-local”的，作用一样。    
(setq-default indent-tabs-mode nil)

#### t 表示true，即此选项选中的意思。
(global-linum-mode t)  `全局行号设置打开`  
(linum-relative-global-mode t)

# 2. 集成插件，与第三方软件结合
#### 1. gnu global
1. 安装：sudo apt-get install global
2. `(setenv "PATH" (concat "/path/to/global/bin;" (getenv "PATH")))`  设置环境变量，上一步安装完已经设置了PATH
3. 安装 gtags.el
    * 也可以用 elpa 安装 gtags.el. `package-install RET ggtags`
    * 准备好 gtags.el 之后，在 .emacs 或是 .emacs.d/init.el 中加入 
    `(setq gtags-suggested-key-mapping t)` 以使用建议的键绑定。 
4. 生成代码索引文件。 
    * 打开在代码目录下执行 gtags ，将生成索引，生成GPATH, GTAGS, GRTAGS。 
    * 如果想看详细输出，用 gtags -v ，能看到哪些文件被索引了。 
5. 在Emacs中打开一个源文件，`M-x ggtags-mode`，如果 gtags.el 正确安装了，就会启动 gtags minor-mode。 
6. 然后就可以使用gtags的按键绑定了。我常用的按键如下： 

    操作 | 作用
    -- | --
    C-c v | 告诉Emacs项目的根目录，即到哪里去找GTAGS等文件。这一步不要跳过，否则你查找符号时Emacs会问你去哪里查找tags。 
    M-. |跳转到符号定义。 
    C-t |返回。 
    C-c g | 在代码中用grep查找符号。 
    C-c s | 搜索某个符号。 
    C-c r | 看一个函数在哪些地方被引用。 

#### 2. minimap 生成缩略图侧边栏
1. 安装 `package-install RET minimap`
2. 使用 `M-x minimap`
