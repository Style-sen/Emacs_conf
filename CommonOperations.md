[1.光标移动](#1)    
[2.删除](#2)    
[3.标记](#3)    
[4.查找与替换](#4)    
[5.“神器”宏操作](#5)    
[6.排序](#6)    
[7.大小写转换](#7)    
[8.执行shell命令](#8)    
[9.常用M-x命令](#9)      
[10.常用列操作](#10)    

<h2 id="1">1.光标移动</h2>    

### 1.1.一次执行n次移动:(1)C-u n或M-n 重复执行n次后继命令 (2)执行移动命令;
| 移动命令 | 作用 |
| -- | -- |
| C-f     | 光标前进一个字符       | 
| C-b     | 光标后退一个字符       | 
| C-p     | 上移一行               | 
| C-n     | 下移一行               | 
| M-f     | 前进一个单词           | 
| M-b     | 后退一个单词           | 
| C-a     | 行首                   | 
| C-e     | 行尾                   | 
| M-a     | 句首                   | 
| M-e     | 句尾                   | 
| M-{     | 上一个段落             | 
| M-}     | 下一个段落             | 
| C-v     | 屏幕上卷一个屏         | 
| M-v     | 屏幕下卷一个屏         | 
| C-M-v   | 另一个窗口下卷一个屏幕 | 
| C-M-V   | 另一个窗口上卷一个屏幕 | 
| M-<     | 文件头                 | 
| M->     | 文件尾                 | 
| M-g g   | 跳到指定行 |
| M-g p   | 跳到上一个错误，配合rgrep使用，跳到上一个引用 |
| M-g n   | 跳到下一个错误，配合rgrep使用，跳到下一个引用 |
| C-l     | 将当前行移动到屏幕中间or最上方or最下方 |
| C-u C-@ | 跳回到上一次光标的位置   |

<h2 id="2">2.删除</h2>

### 2.1.一次执行ｎ次删除:(1)C-u n或M-n 重复执行n次后继命令 (2)执行删除命令;    
| 删除命令 | 作用 |
| -- | -- |
| C-d           | 删除光标上的字符     |
| DEL           | 删除光标前的字符     |
| M-d           | 删除光标后的单词     |
| M-DEL         | 删除光标前的单词     |
| C-k           | 从光标位置删除到行尾 |
| C-Backspace   | 删除光标前的单词 同M-DEL  |
| C-S-Backspace |  删除当前行          |
| C-y           |  恢复删除最近的一个  |
| M-y           |  循环恢复删除上一个  |
<h2 id="3">3.标记</h2> 

| 标记命令 | 作用 |
| -- | -- |
| C-@     | 标记文本块的开始  |
| C-x C-x | 互换插入点和文本标记的位置 | 
| M-h     | 标记整个段落               | 
| C-x C-p | 标记整个页面               | 
| C-x h   | 标记整个缓冲区             | 
<h2 id="4">4.查找与替换</h2>  

### 4.1. 简单查找替换    
***注意:C-q C-j是换行符***

| 查找替换命令 | 作用 |
| -- | -- |
| C-s            | 向前递增查找                                |  
| C-r           | 反向递增查找                                 | 
| C-s C-w        |向前递增查找，把光标所在的单词作为查找对象   | 
| C-r C-w        | 反向递增查找，把光标所在的单词作为查找对象  | 
| replace-string |  查找替换光标后所有的内容                   | 
| M-%            |   查询替换操作                              | 
* 对于M-%，需要注意的是其相关的一些操作:    

| 命令 | 作用 |
| -- | -- |
| SPACE或y  |  用新字符串替换原来的，并进入下一个位置          |
| DEL或n    |  不替换，进入下一个位置 |
| .         | 在当前位置做替换后退出查询－替换操作 | 
| ,         | 替换，并显示替换情况（再按空格或y进入下一个位置） |
| !         | 对后面的内容全部进行替换，不再提问 |
| ^         | 返回上一个替换了的位置 |
| RETURN或q |  退出查询替换操作 |
| C-r       | 进入递归编辑状态 |
| C-w       | 删除此处内容并进入递归编辑状态（好进行其他修改） |
| M-C-c     | 退出递归编辑状态，继续完成查询－替换操作 |
| C-]       | 退出递归编辑状态和查询替换操作 |
### 4.2. 正则表达式查找与替换   
| 查找替换命令 | 作用 |
| -- | -- |
| C-M-s Return           | 向前查找正则表达式        |
| C-M-r Return           | 反向查找正则表达式 |
| C-M-s                  | 向前递归查找正则表达式 |
| C-M-r                  | 反向递归查找正则表达式 |
| query-replace-regexp   | 查询-替换正则表达式 |
| replace-regexp         | 无条件替换正则表达式（慎用） |
* 正则表达式中的字符：

| 字符 | 作用 |
| -- | -- |
| ^          | 匹配行首 |
| $          | 匹配行尾 |
| .          | 匹配任意单个字符 |
| .*         | 匹配任意个字符 |
| \<         | 匹配单词的开头 |
| \>         | 匹配单词的结尾 |
| []         | 匹配[]中的任何一个字符，如[a-z]匹配任何一个小写字母 |

<h2 id="5">5.“神器”键盘宏</h2>

参考[17 Keyboard Macros](https://www.gnu.org/software/emacs/manual/html_node/emacs/Keyboard-Macros.html#Keyboard-Macros)    
### 基本使用

#### 5.1. 快捷键

| 快捷键 | 作用 |
| -- | -- |
| F3 | 开始录制宏，如果已经开始录制就插入计数器 |
| F4 | 如果正在录制宏就结束录制，否则就执行最近的一次宏 |
| C-x ( | 开始录制宏 |
| C-x ) | 录制结束 |
| C-x e | 如果正在录制宏，会立即结束录制并执行一次。否则执行一次，"C-u 执行次数 C-x e" 将会执行设定的次数遍，也可以用 "C-执行次数 C-x e"|
| C-x C-k r | 在区域中每行执行最后一次宏 |
    
#### 5.2. 宏计数器
    每个宏都会关联一个从0开始的计数器，这个计数器允许插入一个数字，根据宏执行次数递增。

| 快捷键 | 作用 |
| -- | -- |
| C-x C-k C-i | 缓冲区中插入计数，作用类似F3，但是在录制以外也可加入计数 |
| C-x C-k C-c | 设置计数器开始值 |
| C-x C-k C-a | 设置计数器前缀 |
| C-x C-k C-f | 设置格式 |

#### 5.3. 
#### 5.4. 宏命令命名
* 执行完毕后，可以用 “M-x name-last-kbd-macro”为最后一次的宏命令命名，
再有，可以将宏命令，保存下来，设定到 emacs 的加载文件中，这样以后打开软件就可以使用这个宏了。
(load-file "~/macros")
打开 "~/macros" 文件，移动到末尾，执行“M-x insert-kbd-macro”输入刚才命名的名字，就将录制的宏命令保存下来了。

<h2 id="6">6.排序</h2>

```
默认情况下Emacs排序时是大小写敏感的,要让Emacs排序时忽略大小写,需要设置变量'sort-fold-case'为t
```
1. sort-lines
* 按字典顺序对行进行排序
2. sort-regexp-fields
* 通过该命令,你可以只对一行的某个部分进行排序,而剩下的部分还保留原顺序.
* 该命令首先提示你输入一个正则表达式用于标明哪些部分的内容参与排序,该正则表达式被称为record regexp,Emacs只对该正则表达式匹配的内容作顺序重排,而一行的其他内容不做变化
* 然后提示你输入一个正则表达式用于说明根据哪些部分的内容进行排序,该正则表达式被称为key regexp,若该表达式为空,默认为\&,表示record regexp所匹配的所有内容,可用以用\数字来表示record regexp中的分组
3. sort-columns
* 根据选定列作为key来对行进行排序,所谓选定列是由mark和光标位置指定的列
4. sort-fields
* 所谓field是由空格或TAB分隔的单元.
* 若直接用调用sort-fields,则表示根据第一个field来排序.
* 可用使用使用C-u 数字参数来指定根据第几个field来排序(从1开始计算),若数字为负数,则从后往前数
5. sort-numeric-fields
* 类似sort-fields,但是排序时把指定的field当成数字来排序
* Emacs会自动推测指定field的进制,若field以0x开始表示是16进制,以0开头的表示是而进行,默认为十进制(由变量`sort-numeric-base`决定)
6. sort-pages
* 根据字段顺序对页进行排序,所谓页是由 form feed character 即^L
7. sort-paragraphs
* 根据字典顺序对段落进行排序.
* 段落的定义不同的mode下定义不同,但默认情况下是由一个或多个换行来划分的. 具体参见变量`paragraph-start`和`paragraph-separate`

<h2 id="7">7.大小写转换</h2>    

1. 从光标位置开始，处理单词后半部分
* capitalize-word (M-c) -- 首字母改为大写
* upcase-word (M-u) -- 全部改为大写
* downcase-word (M-l) -- 全部改为小写
2. 从光标位置开始，处理单词前半部分
* negtive-argument; capitalize-word (M-- M-c)
* negtive-argument; upcase-word (M-- M-u)
* negtive-argument; downcase-word (M-- M-l)
3. 改变选定区域的大小写
* downcase-region (C-x C-l) -- 选定区域全部改为小写
* upcase-region (C-x C-u) -- 选定区域全部改为大写

<h2 id="8">8.执行shell命令</h2>    

* `M-! cmd RET`：打开一个名为"*Shell Command Output*"的窗口，并把该命令的执行结果显示在其中。按下”C-x 1“组合键可以关闭这个窗口。由于Shell命令的输出是在一个编辑缓冲区里，因此我们可以对它进行编辑、保存等操作。
* `M-| cmd RET`：运行Shell命令，并使用编辑窗口中选定的区域作为该Shell命令的输入，然后可以选择是否用该Shell命令的输出来替换编辑窗口中选中的区域。
* `C-u M-! cmd RET`：执行一条Shell命令，并将其输出放到编辑区中光标所在的位置处，而不将其输出到"*Shell Command Output*"窗口。
* `M-x shell`：运行一个子Shell，该子Shell对应于emacs中的一个名为"*Shell*"的缓冲区，此后，我们就可以交互式的运行Shell命令了。
* `M-x term`：运行一个子Shell，该子Shell对应于emacs中的一个名为"*Terminal*"的缓冲区。使用该命令获得的子Shell是一个完整的Shell的模拟，与我们直接在Shell中操作没有什么差别。
```shell
The terminal emulator uses Term mode, which has two input modes. In line mode, Term basically acts like Shell mode (see Shell Mode). In char mode, each character is sent directly to the subshell, except for the Term escape character, normally C-c.
To switch between line and char mode, use these commands:
C-c C-j
Switch to line mode (term-line-mode). Do nothing if already in line mode.
C-c C-k
Switch to char mode (term-char-mode). Do nothing if already in char mode.
The following commands are only available in char mode:
C-c C-c
Send a literal C-c to the sub-shell. 
C-c char
This is equivalent to C-x char in normal Emacs. For example, C-c o invokes the global binding of C-x o, which is normally ‘other-window’.
Term mode has a page-at-a-time feature. When enabled, it makes output pause at the end of each screenful:
C-c C-q
Toggle the page-at-a-time feature. This command works in both line and char modes. When the feature is enabled, the mode-line displays the word ‘page’, and each time Term receives more than a screenful of output, it pauses and displays ‘**MORE**’ in the mode-line. Type <SPC> to display the next screenful of output, or ? to see your other options. The interface is similar to the more program.
```
* `M-x eshell`：运行emacs shell。该Shell为emacs自己实现的一个shell，而前面运行的shell都为系统中的shell程序(例如：/bin/csh等）。我们可以通过设置变量shell-file-name来设置emacs所使用的默认shell

<h2 id="9">9.常用M-x命令</h2>    
    C-x Esc Esc返回上一条M-x命令
    
| 操作 | 作用 |
|-- |-- |
| delete-trailing-whitespace | 删除行末空格 |
| delete-blank-lines | 删除空白行 |
| json-pretty-print-buffer | 格式化json文件 |
| whitespace-newline-mode | 显示行末空格 |
| whitespace-cleanup | 自动清除行末空格 |
| revert-buffer | 刷新缓冲区 |

<h2 id='10'>10.常用列操作</h2>

| 操作 | 作用 |
|-- |-- |
| C-@ 标记起点，移动光标，标记终点，组成一个选择区域 | 划定列区域 |
| S-方向键 | 划定列区域 |
| C-x r t [插入的字符] | 在每一行插入相同的字符串 |
| C-x r k | 删除选中的列内容 |
