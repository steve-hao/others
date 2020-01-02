  
 
上次写这个的时候，VsCode是版本（V1.34），目前已经是（V1.41）了，尽管快捷键增加的不多，但是上次写的匆忙，有朋友反映还是看不太懂，所以这次再补写一些内容。  

文中的解释基本是靠实验和个人经验得到的，未必准确。请诸位指正。准确的解释应该却仔细研读Vscode的相关技术文档。    
 
###基本介绍  
 
Windows下的快捷键，主要包含了以下几种组合：  
 
- **F功能键**  
 
  定义为最常用的操作快捷方式 ,原本F1-F12这些功能键，用起来时最方便的了，所以会定义成一些常用功能。不过目前很多笔记本电脑，却需要同时按Fn键，建议经常用VsCode的朋友，无妨把那些功能恢复
 
- **Ctrl + key**  
 
  标准的控制组合键，Vscode在大多数操作都遵循了Windows的基本规范  
 
- **Alt + Key**  
 
  Alt单独组合字母键，首要作用是配合菜单内的选择，部分Alt+字母，以及大部分Alt+符号键均未占用，可用于定义自己的快捷键以及替换冲突的快捷键  
 
- **Shift + Key**  
 
  Shift可单独配合的肩比较少，Shift+方向键或配合鼠标基本用于选择，Shift+编辑键用于编辑  
 
- **Ctrl + Shift + Key**  
 
  Vscode 使用 Ctrl+Shift 组合最多，一是两个键靠得最近，按起来比较方便，另一个原因应该是其他软件多用Ctrl+Alt组合，因此可以较好的避免冲突  
 
- **Alt + Shift + Key**  
 
  Alt + Shift 是Vscode的次选组合，目前使用量并不是很大  
 
- **Ctrl + Alt+ Key**  
 
  Vscode使用的较少的组合，适合于自定义键以及替换冲突建  
 
- **Ctrl + K  key 或 Ctrl + key**    
 
  扩展组合键，继承了编辑器Ctrl+K的传统，Ctrl+K等于进入快捷键命令方式，可以用字母或者组合键进行下一步操作。目前Ctrl + K  key 基本定义为和文件有关的操作了，而Ctrl + K  Ctrl + key 多是和布局等有关的操作  
 
###通用功能 General  
 
  
 
- Ctrl + Shift + P，F1    
 
	显示命令面板 Show Command **P**alette   
 
> Ctrl + P 用于快速打开文件或其他操作，所以用这个组合或者F1实现命令  
> 这个按键我是很常用的，有些时候没有菜单，没有快捷键，就只能用命令了  
> 命令面板下，按 Backspace 会进入到 Ctrl+P 模式  
 
- Ctrl + P   
 
	 快速打开 Quick O**P**en 转到文件  
 
> 其实这也是一种命令面板，除了继续输入字符查找文件并打开外，还可以做很多其他事情，按一个问号就可以看到说明，举几个例子
> > 按>号，进入上面那个命令面板  
> > 按:号，可以转到文件中的某一行  
> > 按@号, 可以转到文件中的符号...
 
- Ctrl + Shift + N   
 
	 新窗口/实例 **N**ew window/instance   
 
>  是再启动一个Vscode，同时做两个项目可以使用  
 
- Ctrl + Shift + W   
 
	 关闭窗口/实例 Close window/instance   
 
>  Ctrl+N，Ctrl+W是一对，这两个也是，为何用W作为关闭，一是Ctrl+C被用于粘贴了，再一个早期都是用Ctrl+W用于存盘并关闭，W应该是**W**rite的的首字母  

- Ctrl + ,   
 
	 用户设置 User Settings   
 
>  用的不多，不必刻意记忆，不是Win10 ，和输入法冲突呢

- Ctrl + K Ctrl + S   
 
	 快捷键 **K**eyboard **S**hortcuts
   
 
>  记不住快捷键设置了，用这个去查。记住别按成 Ctrl + K S 了，这个是保存所有文件啊

 
###基础编辑 Basic editing  
 
  
- Ctrl + X   
 
	 剪切行（空选定） Cut line (empty selection)   
 
>  这个没啥可说的，为啥是X？长得像剪刀吧。 注意空选择的时候是对整行处理，也就是说，在没有文本被选择的时候，Ctrl + X可以帮我们删除一行文本，很方便啊  
 
- Ctrl + C   
 
	 复制行（空选定）**C**opy line (empty selection)   
 
>  和上面一样，有文本选择的时候是复制选择文本到剪贴版，如果选择为空，则可以复制整行啊  
 
- Ctrl  +Delete / Backspace   
 
	 删除右边、左边的字 delete Word Right/Left   
 
> 快速删掉不需要的部分  
 
- Alt + ↑ / ↓   
 
	 向上/向下移动行 Move line up/down   
 
>  非常好用的功能，尤其是配合下一项的复制使用。Ctrl + ↑ / ↓ 用于屏幕滚动一行了，所以用Alt组合使用，虽然叫“行”操作，但实际上有选择集的时候，对选择覆盖的各行进行操作，没有选择则对本行进行操作。  
 
- Shift + Alt + ↓ / ↑   
 
	 向上/向下复制行 Copy line up/down   
 
>  没明白为何不用Ctrl+Shift + ↓ / ↑ ，目前那个快捷和Shift + ↓ / ↑功能是一样的。和上面一样，虽然叫“行”操作，但实际上有选择集的时候，对选择覆盖的各行进行操作，没有选择则对本行进行操作。  
 
- Ctrl + Shift + K   
 
	 删除行 Delete line   
 
> 非常有用的功能，和Ctrl+X的差别是，这个删除不会进剪贴板。但是为什么用 Ctrl+Shift+K而不是Ctrl+Shift+L，导致非常难记，难道仅仅是为了和sublime保持一致？记这个，就把行当成bloc**K**吧  
 
- Ctrl + Enter   
 
	 在下面插入行 Insert line below   
 
>  与Enter的区别就是光标不需要移到行尾就能在下面插一新行，是不是很方便的快捷键，平时我们要在当前代码行下增加新的代码，都要先移到行尾，然后按回车键，有了这个就不必那么麻烦了  
 
- Ctrl + Shift + Enter   
 
	 在上面插入行 Insert line above   
 
>  哈哈，和上面那个快捷键一样的，而且更加常用，那就是在上面增加一个空行。一定要常用把他记住，太好用了啊  
 
- Ctrl + Shift + \   
 
	 跳到匹配的括号 Jump to matching bracket   
 
>  大中小括号都匹配，光标附近没有括号，就往后找第一个括号。  
> 这个真的也不好记忆，不知为什么不用 Ctrl+Shift+（,没关系，当成|吧，也有点像括号，用多一些自然就记住了。也是很好用的功能啊，尤其是大段代码或数据的时候  
 
- Ctrl + ] / [   
 
	 缩进/突出行 Indent/outdent line   
 
> 写Python程序最重要，对齐代码是关键啊，写其他的一样很有用，要记住这个快捷键啊。 
> 把[想象为Tab定位符，虽然叫“行”操作，但实际上有选择的时候，对选择覆盖的各行进行操作，没有选择则对本行进行操作。  
 
- Home   
 
	 转到行首 Go to beginning of line   
 
> 下面这几项就不需要多解释了  
 
- End	  
 
	 转到行尾 Go to end of line  
	  
- Ctrl + Home   
 
	 转到文件开头 Go to beginning of file  
 
- Ctrl + End   
 
	 转到文件末尾 Go to end of file  
 
- Ctrl + ← / →    
 
	 光标到字首/字尾 cursor word end right/start left

>  使用它，可以一个字一个字的跳， 很常用的快捷键啊 
 
- Ctrl + ↑ / ↓   
 
	 向上/向下滚动行 Scroll line up/down   
 
> 窗口小，有些东西就在上面或者，下面一点点，或者光标在屏幕的这个位置我看着不舒服，试着滚动一下屏幕吧,光标不动  
 
- Alt + PgUp / PgDown   
 
	 向上/向下滚动页面 Scroll page up/down   
 
>  和Pgup/PgDown的区别是，页面滚动当前光标并不随着移动，用于查看文档其它内容。不过上边滚动一行用Ctrl键组合，而滚动页面却用Alt组合，会让记忆混乱。建议把这个键和Ctrl+PgUp/PgDown互换，用Ctrl+控制屏幕的移动，而用Alt更换编辑器，也使得那个功能和Alt+1,2这些选择编辑器的功能一致  
 
- Ctrl + Shift + [   
 
	 折叠（折叠）区域 Fold (collapse) region   
 
>  把[读成{，我觉得更形象  
 
- Ctrl + Shift + ]   
 
	 展开（未折叠）区域 Unfold (uncollapse) region  
 
- Ctrl + K Ctrl + [   
 
	 折叠（未折叠）所有子区域 Fold (collapse) all subregions   
 
>  折叠所有的就用Ctrl + K 去扩展  
 
- Ctrl + K Ctrl + ]   
 
	 展开（未折叠）所有子区域 Unfold (uncollapse) all subregions  
 
- Ctrl + K Ctrl + 0   
 
	 折叠（折叠）所有区域 Fold (collapse) all regions   
 
> 这一对的设置很奇怪的，一个用0，一个用J，我一直未想明白，也很难记住  
 
- Ctrl + K Ctrl + J   
 
	 展开（未折叠）所有区域 Unfold (uncollapse) all regions  
 
- Ctrl + K Ctrl + C   
 
	 添加行注释 Add line **C**omment 

> 很好用的，和语言相关，不同语言都可以按照它的注释方法增加，这个和后面两个都是触发方式的，也就是说按一下加上，再按一下去掉，所以使用最后一个一个更好记的 Ctrl + / 吧
 
- Ctrl + K Ctrl + U   
 
	 删除行注释 Remove line comment   
 
>  记成**U**ncomment  
 
- Ctrl + /   
 
	 切换行注释 Toggle line comment   
 
>  很多语言注释都是用//开头的，所以不难记,而且有这个，上面两项基本就不需要了。另外和前面的行处理命令一样，选了多行就可以形成多行注释  
>  太好用的功能了，一定要用心记住啊
 
- Shift + Alt + A   
 
	 切换块注释 Toggle block comment   
 
>  不好记，不知道A如何关联，而且还用次一级的Shift+Alt组合。虽然叫切换，但实际上设置块注释容易，但是取消就很费劲我个人不记它，用的时候去菜单找  
 
- Alt + Z   
 
		切换换行 Toggle word wrap   
 
>  不好记忆，幸亏很少改变折行，真要想用了，去菜单找吧  
 
###导航 Navigation  
 
 
- Ctrl + T   
 
	 显示所有符号 Show all Symbols   
 
>  查找的是整个工作目录或者工作空间里所有当前相同的符号  
>  相当于按了Ctrl+P，然后输入#命令以及当前字符,符号记成**T**ag吧  
 
- Ctrl + G   
 
	 转到行... **G**o to Line...   
 
>  光标会跟着走  
 
- Ctrl + P   
 
		转到文件... Go to File...   
 
> 打开文件命令行，列表是最近打开的文件,上面已经介绍过了  
 
- Ctrl + Shift + O   
 
	 转到符号... Go to Symbol...   
 
>  相当于按了Ctrl+P，然后输入@命令，显示当前文件里的所有符号，包括变量和方法  
 
- Ctrl + Shift + M   
 
	 显示问题面板 Show Problems panel   
 
> 把M想象成**M**essage吧  
 
- F8   
 
	 转到下一个错误或警告 Go to next error or warning   
 
> 直接转到错误或警告的位置，未打开的文件也会自动打开，很方便  
 
- Shift + F8  
 
	转到上一个错误或警告 Go to previous error or warning   
 
> Shift配合找前一个错误或警告  
 
- Ctrl + Tab   
 
	 编辑器组最近使用的下一个编辑器 Navigate editor group history   
 
> 其实就是最近使用的两个编辑器互相切换，也会显示编辑器组历史记录  
 
- Ctrl + Shift + Tab   
 
	  编辑器组最近使用的上一个编辑器 Navigate editor group history   
 
>  这个没啥用，有前一个就够了  
 
- Alt + ← / →   
 
	 返回/前进 Go back / forward   
 
>  这个开始的时候没明白，为什么叫前进/后退，他不是操纵光标的，而是移动打开的窗口的。如果你把操作各窗口想象成在一个浏览器窗口里导航的话，这两个键就相当于浏览器的上向前和回退。换句话是就是在编辑器组历史记录里来回切换。所以上面的Ctrl + Tab基本失去意义了，可以定义为其他功能  
 
- Ctrl + M   
 
	 切换选项卡移动焦点 Toggle Tab moves focus   
 
>  没什么用，占了这么一个快捷键好可惜啊，以后有什么自定义的可以覆盖这个。当然，如果鼠标坏了，这个功能就起作用了，他可以用Tab键去遍历整个窗口。  
 
###搜索和替换 Search and replace  
 
 
- Ctrl + F   
 
	 查找 **F**ind   
 
>  标准的键定义  
 
- Ctrl + H   
 
	 替换 Replace   
 
>  用Ctrl+ H 或者 Ctrl+ G，Ctrl+ R都很常见，特点就是离F键比较近，似乎没什么特别的意义。  
 
- F3 / Shift + F3   
 
	 查找下一个/上一个 Find next/ previous  
 
>  F3在查找到的内容间切换  
 
- Alt + Enter	  
 
	 选择查找匹配的所有出现 Select all occurences of Find match   
 
>  这个快捷键只在查找替换的时候起作用，把查找的结果加上多光标，然后就可以同步修改了  
 
- Ctrl + D   
 
	将选择添加到下一个查找匹配 Add selection to next Find match   
 
>  上一个键是吧你查找的内容全部选择，并加上多光标，便于批量处理。但是只能在Ctrl+F进行搜索的时候使用  
> 而Ctrl + D是往下一个个的把随后的与当前选择的文字相同的的，一个个加入选择集，并且增加多光标。  
> 如果当前未选择任何文字,则选择当前文字,!!! 你知道了么,选择当前Word的快捷键就是 Ctrl+D,记成wor**D**  
 
- Ctrl + K Ctrl + D   
 
	 将最后一个选择移至下一个查找匹配项 Move last selection to next Find match   
 
>  看起来很像F3的查找下一个功能，但实际是有差别的：F3仅仅是到下一个查找位置，这个会选择上那个匹配的内容。F3不管你光标在哪里，总是查找最后一次查找的关键字，而这个功能会把当前的字作为关键字  
 
- Alt + C / R / W   
 
	 切换区分大小写/正则表达式/整个词 Toggle **c**ase-sensitive / **r**egex / **w**hole word   
 
>  用于进行查询时,查询选项的更改  
 
###多光标和选择 Multi-cursor and selection  
 
 
- Alt + 单击   
 
	 插入光标 Insert cursor   
 
>  按住Alt键，可以插入多个光标,按ESC可以取消多光标  
 
- Ctrl + Alt + ↑ / ↓	  
 
	 在上/下插入光标 Insert cursor above / below   
 
>  用在行首或者列表插入内容很好用,不成用的话就不要特别记忆了,菜单里有  
 
- Ctrl + U    
 
	 撤消上一个光标操作 **U**ndo last cursor operation   
 
>  光标回退，回到前几个位置，但不影响操做过的内容  

- Ctrl + Shift + J    
 
	 撤消上一个光标操作 redoes the previously undone cursor state change   
 
>  恢复上面被Undo的光标，但不影响操做过的内容  

- Shift + Alt + I	  

	 在选定的每一行的末尾插入光标 **I**nsert cursor at end of each line selected  
 
 >  用在每行行尾插入内容，但要小心你选择区域结束的位置，他不会把光标放在行尾

- Ctrl + L   
 
	 选择当前行 Select current **l**ine   
 
> 选择一行，连续按就可以选择多行，这个又是很常用的命令啊，方便极了  
 
- Ctrl + Shift + L   
 
	 选择当前选择的所有出现 Select all occurrences of current selection   
 
>  前面搜索里那个Alt+ Enter只有在搜索框存在的时候才起作用，而这个命令会把当前的字的所有搜索结果选择。而这个是组合在一起了
>  当你要批量改变文件里某一个变量的名字的时候，这个有时候更好用，特别是仅仅增加几个字符的时候，比下一个方法更好用  
 
- Ctrl + F2   
 
	 选择当前字的所有出现 Select all occurrences of current word   
 
>  这个和上一项效果看起来类似，但调用的不是同一个功能。这个相对的按键更少一些 
 
- Shift + Alt + →	  
 
	 展开选择 Expand selection   
 
>  Shift + → 是一个字一个字向前增加，而这个是往两边扩展，扩展遵循了一定的规则，通过尝试大约是，字边界，各种括号，行，全部文件  
>  用扩展选择的功能，可以选择一个列表、函数、字典等所有内容，需要使用的时候，还是个不错的选择的。  
 
- Shift + Alt + ←	  
 
	 缩小选择 Shrink selection   
 
> 类似上面  
 
- Shift + Alt + （拖动鼠标）   
 
	 列（框）选择 Column (box) selection   
 
>  按住Alt键，用鼠标选择就是矩形块，或者按住鼠标滚轮拖动进行选择  
 
- Ctrl + Shift + Alt +（箭头键）  
 
	 列（框）选择 Column (box) selection   
 
>  好多键啊，用键盘做块选择，就要按全部键  
 
- Ctrl + Shift + Alt + PgUp / PgDown   
 
	 列（框）选择页上/下 Column (box) selection page up/down  
 
###富语言编辑 Rich languages editing  
 
 
- Ctrl + 空格   
 
	 触发建议 Trigger suggestion   
 
>  在非Win10系统系，此键和输入法冲突，可考虑修改为 Alt+空格键，或者替换Ctrl+Tab  
 
- Ctrl + Shift + Space   
 
	 触发器参数提示 Trigger parameter hints   
 
>  同上  
 
- Shift + Alt + F   
 
	 格式化文档 **F**ormat document   
 
- Ctrl + K Ctrl + F   
 
	 格式选定区域 **F**ormat selection  
 
- F12	转到定义   
 
	 Go to Definition  
 
- Alt + F12   
 
	 Peek定义 Peek Definition   
 
>  上面的F12会打开包含定义的文件或者光标移动到定义处，而这个会打开一个Peek窗口来查看  
 
- Ctrl + K F12   
 
	 打开定义到边 Open Definition to the side   
 
>  放在新的分栏，可以不影响目前  
 
- Ctrl + .   
 
	 快速解决 Quick Fix   
 
> 对发现了拼写错误的快速进行修复  
> 如果用微软的lint库写Python，他甚至可以查找一个函数在那个包里，然后把选择的包的import语句，自动的加进来，很方便啊  
 
- Shift + F12   
 
	 显示引用 Show References   
 
>  同样是打开了一个Peek窗口，将项目里的所有对变量或者方法的引用列出来  
 
- F2   
 
	 重命名符号 Rename Symbol   
 
	可以在项目里，一次修改成新的变量名  
 
- Ctrl + Shift + . /，  
 
	 替换为下一个/上一个值 Replace with next/previous value   
 
>  首先,和.我们应该看作‘<’和‘>’，功能我还没搞明白，在我这里Ctrl + Shift + .会调用上面的那个多层列表，和定义里完全不同，Ctrl + Shift + , 倒是可以用，他应该是从一个可迭代里取下一个，如果是True，他会替换成Flase，如果光标处是数字，会往上累加1  
 
- Ctrl + K Ctrl + X   
 
	修剪尾随空格 Trim trailing whitespace   
 
>  挺好的功能，但不好记  
 
- Ctrl + K M   
 
	 更改文件语言 Change file language   
 
>  注意后面是M，而不是Ctrl+M，这两种方法是俩功能。搞的太复杂了吧  
 
###编辑器管理 Editor management  
 
- Ctrl + F4, Ctrl + W   
 
	 关闭编辑器 Close editor   
 
>  关闭当前的编辑器  
 
- Ctrl + K F   
 
	 关闭文件夹 Close **f**older   
 
> 关闭打开的文件夹  
 
- Ctrl + \   
 
	 拆分编辑器 Split editor   
 
>  把\ 看成竖线就好记了  
 
- Ctrl+ 1 / 2 / 3   
 
	 聚焦到第1，第2或第3编辑器组 Focus into 1st, 2nd or 3rd editor group   
 
>  Alt+数字用于编辑器，Ctrl+数字用于编辑器组  
 
- Ctrl + K Ctrl + ← / →   
 
	 聚焦到上一个/下一个编辑器组 Focus into previous/next editor group   
 
>  不同的组切换焦点，没有鼠标的时候更方便些  
 
- Ctrl + Shift + PgUp / PgDown   
 
	 向左/向右移动编辑器 Move editor left/right   
 
>  这个不好记忆，用处也不大  
 
- Ctrl + K ← / →   
 
	 移动活动编辑器组 Move active editor group   
 
>  编辑器组交换位置  
 
###文件管理 File management  
 
- Ctrl + N   
 
	 新文件 **N**ew File  
 
- Ctrl + O   
 
	 打开文件... **O**pen File...  
 
- Ctrl + S   
 
	 保存 **S**ave  
 
- Ctrl + Shift + S   
 
	 另存为... **S**ave As...  
 
- Ctrl + K S   
 
	 全部保存 Save All   
 
	 保存全部放在了Ctrl+K子命令下  
 
- Ctrl + F4   
 
	 关闭 Close  
 
- Ctrl + K Ctrl + W   
 
	 关闭所有 Close All   
 
>  为何不和全部保存统一了呢  
 
- Ctrl + Shift + T   
 
	 重新打开关闭的编辑器 Reopen closed editor   
 
>  只对最后一次关闭的有效，可是不好记，不过Chrome里也是这个快捷  
>  不过这个却是值得记忆的一个快捷键，比较常用
 
- Ctrl + K Enter   
 
	 保持预览模式编辑器打开 Keep preview mode editor open   
 
>  搞了很久才明白他是做什么用的，一般单击或者回车打开的文件，都是预览模式，如果希望这个文件保持在编辑器里，就用这个快捷键  
 
- Ctrl + Tab   
 
	 打开下一个 Open next   
 
>  这一对的使用场景是在文件列表里，可以打开前一个或后一个文件  
 
- Ctrl + Shift + Tab   
 
	 打开上一个 Open previous  
 
- Ctrl + K P   
 
	 复制活动文件的路径 Copy **p**ath of active file  
 
- Ctrl + K R   
 
	 在资源管理器中显示当前文件 **R**eveal active file in Explorer   
 
>  会打开资源管理器  
 
- Ctrl + K O   
 
	 在新窗口/实例中显示当前文件 Show active file in new window/instance   
 
>  O是Open，新打开一个VsCode  
 
###显示 Display  
 
F11   
 
	 切换全屏 Toggle full screen  
 
- Shift + Alt + 0   
 
	 切换编辑器布局 Toggle editor layout   
 
>  横竖布局互换  
 
- Shift + Alt + 1	  
 
	 把编辑器中文件放到第一组 Move Editor To FirstGroup   
 
- Ctrl + = / -   
 
	 放大/缩小 Zoom in/out   
 
> 记忆程Ctrl加上+ - 键  
 
- Ctrl + B   
 
	 切换侧栏可见性 Toggle Sidebar visibility   
 
> 打开关闭侧边栏，我只好把他记忆成**B**order，下面都是此类操作  
> 屏幕小的时候，这个快捷还是很常用的 
 
- Ctrl + Shift + E   
 
	 显示文件浏览器/切换焦点 Show **E**xplorer / Toggle focus   
 
>  显示侧边栏文件浏览  
 
- Ctrl + Shift + F   
 
	 显示搜索 Show Search   
 
>  **F**ind  
 
- Ctrl + Shift + G   
 
	 显示Git Show **G**it  
 
- Ctrl + Shift + D   
 
	 显示调试 Show **D**ebug  
 
- Ctrl + Shift + X   
 
	 显示扩展 Show E**x**tensions  
 
- Ctrl + Shift + H   
 
	 替换文件 Replace in files   
 
>   替换是Ctrl+H  
 
- Ctrl + Shift + J   
 
	 切换搜索详细信息 Toggle Search details   
 
>  侧边栏的搜索，会在工作区或者文件夹下进行，这个键会打开增加文件限制条件的选项  
 
- Ctrl + Shift + C   
 
	 打开新命令提示符/终端 Open new **c**ommand prompt/terminal   
 
>  会在系统里，新打开一个Command窗口  
 
- Ctrl + Shift + U   
 
	 显示输出面板 Show O**u**tput panel   
 
>  为啥不用O却用U，实际这个键也可以控制下面面板的显示与不显示，实际上是个 Toggle  
 
- Ctrl + Shift + V   
 
	 切换Markdown预览 Toggle Markdown pre**v**iew  
 
- Ctrl + K V   
 
	 从旁边打开Markdown预览 Open Markdown preview to the side  

- Ctrl + K Z   
 
	 Zen 模式 Zen Mode  
>  Zen 模式，专注模式、禅模式，没有多余的东西，专注写作，按两次ESC退出
 
###调试 Debug  
 
- F9   
 
	 切换断点 Toggle breakpoint  
 
- F5   
 
	 开始/继续 Start/Continue  
 
- Shift + F5   
 
	 停止 Stop  
 
- F11 / Shift + F11	  
 
	 步入/步出 Step into/out  
 
- F10   
 
	 单步跳过 Step over  
 
- Ctrl + K Ctrl + I   
 
	 显示悬停 Show hover   
 
>  这个键当你想要复制Hover里的内容的时候，就会发现他很有用了  
 
###集成终端 Integrated terminal  
 
- Ctrl + `   
 
	 显示集成终端 Show integrated terminal   
 
> 来回切换  
 
- Ctrl + Shift + `   
 
	 创建新终端 Create new terminal  
 
- Ctrl + C   
 
	 复制选定 Copy selection  
 
- Ctrl + V   
 
	 粘贴到活动终端 Paste into active terminal  
> 点击右键也可以粘贴哟
 
- Ctrl + Delete / Backspace   
 
	 删除右边、左边的字符 delete Word Right/Left   
 
>  快速删掉不需要的部分  
 
- Ctrl + Alt + PgUp / PgDown   
 
	 向上/向下滚动 Scroll up/down   
 
>  上下滚动一行，因为在终端里，上下箭头已经定义为显示上一/下一命令了  
 
- Shift + PgUp / PgDown   
 
	 向上/向下滚动页面 Scroll page up/down   
 
>  上下滚动一页  
 
- Ctrl + Home / End	  
 
	 滚动到顶部/底部 Scroll to top/bottom  
 
- Shift + Enter   
 
	在终端里执行选择的语句 python exec Selection In Terminal   
 
>  这个是Python专用的，可以打开Python终端，执行选择的内容,不过要小心，不要选全行，这会报缩进错误，这时候Alt+Shift+→ 去扩展选择往往有效  
>  Jupyter就是用Shift+Enter啊


 
  
 
  
 
  