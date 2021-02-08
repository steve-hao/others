定义后面跟 #red 改变颜色

关系后面跟 :后面的是关系的标注

连接线中间加[#xxx]可修改线的颜色，加 [hidden]可以隐藏线，（其它：bold, dashed, dotted, hidden ,plain）  

* old method [#color;style]
* new method #color;line.[bold|dashed|dotted];text:color

使用 title 关键词增加标题

使用 header 关键词增加页眉

使用 footer 关键词增加页脚

消息后面添加 note left 或者 note right 关键词来给消息添加注释

note left of，note right of 或 note over 在节点 (participant) 的相对位置放置注释

你可以使用 hnote 和 rnote 这两个关键字来修改备注框的形状。(only 时序图)

在定义链接之后，你可以用 note on link 给链接添加注释,可以用 note left on link，note right on link，note bottom on link。

可以使用 together 关键词将某些类进行分组：布局引擎会尝试将它们捆绑在一起（如同在一个包(package) 内)

加一个allow_mixing ，可以混合其他的图 

:开始，;号结束多行文字