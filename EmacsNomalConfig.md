# 1. Eslip语法
#### 1. t 表示true，即此选项选中的意思。
(global-linum-mode t)  `全局行号设置打开`  
(linum-relative-global-mode t)
#### 2. setq   setq-default  setf
setq用于给symbol的reference设置，而setf用于设置list或者array的reference.    
(setq default-tab-width 4)  `设置tab的默认长度为4个空格`    
如果一个变量是“buffer-local”的，setq只是修改当前buffer的，setq-default修改global的，如果这个变量不是“buffer-local”的，作用一样。    
(setq-default indent-tabs-mode nil)

#### 3. global-set-key 绑定M-x命令到按键
(global-set-key [f1] 'whitespace-newline-mode)  显示行末的空格
