## [ELPY插件](https://github.com/jorgenschaefer/elpy)
#### 1.安装
1. 安装一些依赖包
```shell
# Either of these
pip install rope
pip install jedi
# flake8 用来检查语法错误
pip install flake8
# importmagic 用来自动引入需要的包
pip install importmagic
# autopep8 用来检查PEP8规范
pip install autopep8
# yapf 用来格式化代码
pip install yapf
```
2. 编辑~/.emacs
* 增加
```lisp
(require 'package)
(add-to-list 'package-archives
             '("melpa-stable" . "https://stable.melpa.org/packages/"))
```
* `M-x package-refresh-contents`
* emacs中执行:`M+x list-package\在列表中C+s搜索elpy\install`
* 增加
```lisp
(package-initialize)
(elpy-enable)
```
#### 2.使用
1. C+c C+c运行当前脚本;
2. M-x pyvenv-activate 使用虚拟环境;
3. M-x pyvenv-deactivate 关闭虚拟环境;
4. M-x elpy-config 输出调试信息.

## 更好的语法检查
默认情况下，安装了Elpy插件的Emacs提供一个名叫Flymake的语法检查插件。但是，我们还可以选择另外一个名叫Flycheck的插件，后者支持 *实时语法* 检查。幸运地是，从Flymake切换至Flycheck非常简单：
```lisp
(defvar myPackages
  '(better-defaults
    elpy
    flycheck ;; add the flycheck package
    material-theme))
```
以及
```lisp
(when (require 'flycheck nil t)
  (setq elpy-modules (delq 'elpy-module-flymake elpy-modules))
  (add-hook 'elpy-mode-hook 'flycheck-mode))
```

## 遵循PEP8规范
autopep8插件就是解决之道,这个插件与Emacs无缝集成，因此当你保存文件时——C-x C-s——autopep8插件就会自动格式化代码，并纠正所有不符合PEP8标准的错误（排除你不希望检查的错误）。

首先，autopep8这个Python工具包，然后添加下面的Emacs配置代码：
```lisp
(defvar myPackages
  '(better-defaults
    elpy
    flycheck
    material-theme
    py-autopep8)) ;; add the autopep8 package
```
以及
```lisp
(require 'py-autopep8)
(add-hook 'elpy-mode-hook 'py-autopep8-enable-on-save)
```
现在我们保存Python文件，Autopep8插件就会自动纠正出现的错误.

## 参考
[Emacs：最好的Python编辑器？](https://segmentfault.com/a/1190000004165173)
