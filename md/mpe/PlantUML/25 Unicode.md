## 25 Unicode

The PlantUML language use letters to define actor, usecase and soon.

But letters are not only A-Z latin characters, it could be any kind of letter from any language.

### 25.1 Examples

``` puml {hide=false}
@startuml
skinparam handwritten true
skinparam backgroundColor #EEEBDC
actor 使用者
participant "頭等艙" as A
participant "第二類" as B
participant "最後一堂課" as 別的東西
使用者 -> A: 完成這項工作
activate A
A -> B: 創建請求
activate B
B -> 別的東西: 創建請求
activate 別的東西
別的東西 --> B: 這項工作完成
destroy 別的東西
B --> A: 請求創建
deactivate B
A --> 使用者: 做完
deactivate A
@enduml
```

``` puml {hide=false}
@startuml
(*) --> "膩平台"
--> === S1 ===
--> 鞠躬向公眾
--> === S2 ===
--> 這傢伙波武器
--> (*)
skinparam backgroundColor #AAFFFF
skinparam activityStartColor red
skinparam activityBarColor SaddleBrown
skinparam activityEndColor Silver
skinparam activityBackgroundColor Peru
skinparam activityBorderColor Peru
@enduml
```

``` puml {hide=false}
@startuml
skinparam usecaseBackgroundColor DarkSeaGreen
skinparam usecaseArrowColor Olive
skinparam actorBorderColor black
skinparam usecaseBorderColor DarkSlateGray
使用者 << 人類 >>
"主數據庫" as 數據庫 << 應用程式 >>
(草創) << 一桿 >>
"主数据燕" as (贏余) << 基本的 >>
使用者 -> (草創)
使用者 --> (贏余)
數據庫 --> (贏余)
@enduml
```

``` puml {hide=false}
@startuml
() "Σωκράτηςψεύτης" as Σωκράτης
Σωκράτης - [Πτηνά πολεμοχαρής]
[Πτηνά πολεμοχαρής] ..> () Αθήνα : Αυτές οι φράσειςσημαίνουν τίποτα
@enduml
```

### 25.2 Charset


The default charset used when reading the text files containing the UML text description is system dependent.

Normally, it should just be fine, but in some case, you may want to the use another charset. For example, with the command line:
```
java -jar plantuml.jar -charset UTF-8 files.txt
```
Or, with the ant task:
```
<!-- Put images in c:/images directory -->
<target name="main">
<plantuml dir="./src" charset="UTF-8" />
```
Depending of your Java installation, the following charset should be available: ISO-8859-1, UTF-8, UTF-16BE,UTF-16LE, UTF-16.
