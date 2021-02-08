## 23 Skinparam 命令

你可以使用 skinparam 命令来改变绘图的颜色和字体。

示例: skinparam backgroundColor transparent

### 23.1 使用

你可以（以以下方式）使用本命令：
* 在图 (diagram) 的定义中，和其他命令类似
* 在一个包含文件中
* 在一个配置文件中，提供给命令行或者 ANT 任务使用。

### 23.2 内嵌


为了避免重复 (xxxx 的部分），允许内嵌（相关的）定义。
因此，如下的定义：
```
skinparam xxxxParam1 value1
skinparam xxxxParam2 value2
skinparam xxxxParam3 value3
skinparam xxxxParam4 value4
```
严格等价于: 
```
skinparam xxxx {
Param1 value1
Param2 value2
Param3 value3
Param4 value4
}
```

### 23.3 黑白 (Black and White)


你可以强制使用黑白输出格式，通过 skinparam monochrome true 命令。

``` puml {hide=false}
@startuml
skinparam monochrome true
actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C
User -> A: DoWork
activate A
A -> B: Create Request
activate B
B -> C: DoWork
activate C
C --> B: WorkDone
destroy C
B --> A: Request Created
deactivate B
A --> User: Done
deactivate A
@enduml
```

### 23.4 Shadowing

You can disable the shadowing using the skinparam shadowing false command.

``` puml {hide=false}
@startuml
left to right direction
skinparam shadowing<<no_shadow>> false
skinparam shadowing<<with_shadow>> true
actor User
(Glowing use case) <<with_shadow>> as guc
(Flat use case) <<no_shadow>> as fuc
User -- guc
User -- fuc
@enduml
```

### 23.5 颜色翻转 (Reverse colors)


可以通过 skinparam monochrome reverse 命令，强制使用黑和白的输出，在黑色背景的环境下，尤其适用。


``` puml {hide=false}
@startuml
skinparam monochrome reverse
actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C
User -> A: DoWork
activate A
A -> B: Create Request
activate B
B -> C: DoWork
activate C
C --> B: WorkDone
destroy C
B --> A: Request Created
deactivate B
A --> User: Done
deactivate A
@enduml
```

### 23.6 颜色 (Colors)


你可以使用标准颜色名称或者 RGB 码


``` puml {hide=false}
@startuml
colors
@enduml
```

transparent 只能用于图片背景


### 23.7 字体颜色、名称、大小 (Font color, name and size)


可以通过使用 xxxFontColor, xxxFontSize , xxxFontName 三个参数，来修改绘图中的字体 (颜色、大小、
名称）。

示例:
```
skinparam classFontColor red
skinparam classFontSize 10
skinparam classFontName Aapex
```
也可以使用 skinparam defaultFontName 命令, 来修改默认的字体。

Example:
```
skinparam defaultFontName Aapex
```
请注意：字体名称高度依赖于操作系统，因此不要过度使用它，当你考虑到可移植性时。Helvetica and
Courier 应该是全平台可用。

还有更多的参数可用，你可以通过下面的命令打印它们：
```
java -jar plantuml.jar -language
```

### 23.8 文本对齐 (Text Alignment)


通过 left, right or center, 可以设置文本对齐.

也可以 sequenceMessageAlign 指令赋值为 direction 或 reverseDirection 以便让文本对齐与箭头方
向一致。

Param name | Default value | Comment
--|--|--
sequenceMessageAlign | left | 用于时序图中的消息 (message)
sequenceReferenceAlign | center | 在时序图中用于 ref over

``` puml {hide=false}
@startuml
skinparam sequenceMessageAlign center
Alice -> Bob : Hi
Alice -> Bob : This is very long
@enduml
```

### 23.9 Examples

``` puml {hide=false}
@startuml
skinparam backgroundColor #EEEBDC
skinparam handwritten true
skinparam sequence {
ArrowColor DeepSkyBlue
ActorBorderColor DeepSkyBlue
LifeLineBorderColor blue
LifeLineBackgroundColor #A9DCDF
ParticipantBorderColor DeepSkyBlue
ParticipantBackgroundColor DodgerBlue
ParticipantFontName Impact
ParticipantFontSize 17
ParticipantFontColor #A9DCDF
ActorBackgroundColor aqua
ActorFontColor DeepSkyBlue
ActorFontSize 17
ActorFontName Aapex
}
actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C
User -> A: DoWork
activate A
A -> B: Create Request
activate B
B -> C: DoWork
activate C
C --> B: WorkDone
destroy C
B --> A: Request Created
deactivate B
A --> User: Done
deactivate A
@enduml
```


``` puml {hide=false}
@startuml
skinparam handwritten true
skinparam actor {
BorderColor black
FontName Courier
BackgroundColor<< Human >> Gold
}
skinparam usecase {
BackgroundColor DarkSeaGreen
BorderColor DarkSlateGray
BackgroundColor<< Main >> YellowGreen
BorderColor<< Main >> YellowGreen
ArrowColor Olive
}
User << Human >>
:Main Database: as MySql << Application >>
(Start) << One Shot >>
(Use the application) as (Use) << Main >>
User -> (Start)
User --> (Use)
MySql --> (Use)
@enduml
```

``` puml {hide=false}
@startuml
skinparam roundcorner 20
skinparam class {
BackgroundColor PaleGreen
ArrowColor SeaGreen
BorderColor SpringGreen
}
skinparam stereotypeCBackgroundColor YellowGreen
Class01 "1" *-- "many" Class02 : contains
Class03 o-- Class04 : aggregation
@enduml
```

``` puml {hide=false}
@startuml
skinparam interface {
backgroundColor RosyBrown
borderColor orange
}
skinparam component {
FontSize 13
BackgroundColor<<Apache>> LightCoral
BorderColor<<Apache>> #FF6655
FontName Courier
BorderColor black
BackgroundColor gold
ArrowFontName Impact
ArrowColor #FF6655
ArrowFontColor #777777
}
() "Data Access" as DA
[Web Server] << Apache >>
DA - [First Component]
[First Component] ..> () HTTP : use
HTTP - [Web Server]
@enduml
```

``` puml {hide=false}
@startuml
[AA] <<static lib>>
[BB] <<shared lib>>
[CC] <<static lib>>
node node1
node node2 <<shared node>>
database Production
skinparam component {
backgroundColor<<static lib>> DarkKhaki
backgroundColor<<shared lib>> Green
}
skinparam node {
borderColor Green
backgroundColor Yellow
backgroundColor<<shared node>> Magenta
}
skinparam databaseBackgroundColor Aqua
@enduml
```


### 23.10 所有 skinparam 的参数列表 (List of all skinparam parameters)


本文档并不总能保持最新，你可以使用下面命令查看完成的参数列表
```
java -jar plantuml.jar -language
```
或者可以使用命令，产生一幅有所有 skinparam 参数的图: 

结果如下: 

``` puml {hide=false}
@startuml
help skinparams
@enduml
```

你也可以在https://plantuml-documentation.readthedocs.io/en/latest/formatting/all-skin-params.html查看’‘skin-param’‘的参数.
