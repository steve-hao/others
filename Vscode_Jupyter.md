Vscode 从去年开始，在他的Python扩展里，开始完整的支持Jupyter Notebook, 经过几个月的改进和完善，目前已经处于一个非常不错的情况。

> 本文支持的环境，vscode Version 1.41 ，python extension Version 2020.1.0

相比之下，Vscode的Jupyter支持环境，整体内存和CPU开销都不小（今年的第一个版本，采用了Python daemon技术，提升了不少的性能，建议大家更新一下），我们为什么还要使用Vscode来使用Jupyter Notebook呢？

至少对我来说，我觉得有以下的几点好处：

* 写py代码和使用Notebook经常同时进行，在Notebook里进行一些尝试，记录一些状态等等，所以在一个环境下进行非常方便
* Vscode很好的文件管理、Git管理功能
* Vscode的IntelliSense功能，包括自动补全、智能代码完成，语法检查这些青大的功能，使得我们写代码更加的方便
* 使用Vscode的强大编辑功能

目前Vscode尚未完整的支持Jupyter Notebook的全部环境和命令。这篇文字主要通过我自己的尝试，描述一下在目前版本下，我们可以使用那些Jupyter Notebook的命令以及Vscode自己的编辑命令

### Cell命令模式目前支持的Jupyter Notebook快捷

* Enter : 转入编辑模式
* Shift-Enter : 运行本单元，选中或插入（最后一个Cell的时候）下个单元
* Ctrl-Enter : 运行本单元
* Alt-Enter : 运行本单元，在其下插入新单元
* Y : 单元转入代码状态
* M :单元转入markdown状态  （目前尚不支持R 原生状态）
* Up : 选中上方单元
* K : 选中上方单元
* Down : 选中下方单元
* J : 选中下方单元
* A : 在上方插入新单元
* B : 在下方插入新单元
* D,D : 删除选中的单元
* L : 转换行号
* Shift-Space : 向上滚动
* Space : 向下滚动

可以对于Cell的复制、粘贴、多选、合并、拆分等功能目前尚未支持，等待今后的版本吧

### Cell编辑模式下支持的Vscode快捷键（只描述与编辑相关的那些快捷键）
* Ctrl + X ：剪切/剪切行（空选定）    
* Ctrl + C : 复制/复制行（空选定）
* Ctrl  + Delete / Backspace :删除右边、左边的字
* Alt + ↑ / ↓ :向上/向下移动行
* Shift + Alt + ↓ / ↑ : 向上/向下复制行
* Ctrl + Shift + K : 删除行
* Ctrl + Shift + \ : 跳到匹配的括号
* Ctrl + ] / [ :  缩进/突出行
* Ctrl + ← / →  : 光标到字首/字尾
* Ctrl + / : 切换行注释
* Shift + Alt + A : 切换块注释
* Ctrl + H  : 查找/替换   
  Vscode的查找快捷键 Ctrl + F 目前在Cell里不能用，但是替换快捷键可以使用，因此可以替代原本的查找功能
* Ctrl + D : 选择一个/多个（相同）词
* Alt + 单击 : 插入多个光标
* Ctrl + Alt + ↑ / ↓ :	在上/下插入光标
* Ctrl + U : 撤消上一个光标操作
* Shift + Alt + I : 在选定的每一行的末尾插入光标
* Ctrl + L : 选择当前行
* Ctrl + Shift + L : 选择当前词的所有出现
* Ctrl + F2 ：选择当前字的所有出现
* Shift + Alt + → / Shift + Alt + ←: 展开/缩小选择
* Shift + Alt + （拖动鼠标） : 矩形块选择  
* Ctrl + K Ctrl + X  : 修剪尾随空格

原有Vscod的其他非编辑相关快捷键，大部分也都可以使用，想了解的朋友，可以去看我的相关文章[VSCode快捷键的分析和助记（Windows）](https://zhuanlan.zhihu.com/p/66826924)