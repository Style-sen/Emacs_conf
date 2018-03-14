## ELPY插件
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
(add-to-list 'package-archives '("elpy" . "https://jorgenschaefer.github.io/packages/"))
```
* emacs中执行:M+x list-package\在列表中C+s搜索elpy\install
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
