---
tags: []
created: 2020-09-04T03:37:40.436Z
modified: 2020-09-04T06:41:40.863Z
---
# Skinparam command

You can change colors and font of the drawing using the&nbsp;`skinparam`&nbsp;command.

``` 
skinparam backgroundColor transparent
```

You can use this command :

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in the&nbsp;[command line](https://plantuml.com/en/command-line)&nbsp;or the&nbsp;[ANT task](https://plantuml.com/en/ant-task).


To avoid repetition, it is possible to nest definition. So the following definition :

``` 
skinparam xxxxParam1 value1
skinparam xxxxParam2 value2
skinparam xxxxParam3 value3
skinparam xxxxParam4 value4
```
is strictly equivalent to:

``` 
skinparam xxxx {
    Param1 value1
    Param2 value2
    Param3 value3
    Param4 value4
}
```

## Black and White

You can force the use of a black&white output using&nbsp;`skinparam monochrome true`&nbsp;command.
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

## Shadowing

You can disable the shadowing using the&nbsp;`skinparam shadowing false`&nbsp;command.

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

![](https://s.plantuml.com/imgw/img-d302ef37c7218df6c3658e5051349f05.png " ")

You can force the use of a black&white output using&nbsp;`skinparam monochrome reverse`&nbsp;command. This can be useful for black background environment.

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

## Colors

You can use either&nbsp;[standard color name](https://plantuml.com/en/color)&nbsp;or RGB code.

``` puml {hide=false}
@startuml
colors
@enduml
```


`transparent`&nbsp;can only be used for background of the image.


## Font color, name and size

You can change the font for the drawing using&nbsp;`xxxFontColor`,&nbsp;`xxxFontSize`&nbsp;and&nbsp;`xxxFontName`&nbsp;parameters.

``` 
skinparam classFontColor red
skinparam classFontSize 10
skinparam classFontName Aapex
```

You can also change the default font for all fonts using&nbsp;`skinparam defaultFontName`.

``` 
skinparam defaultFontName Aapex
```

Please note the fontname is highly system dependent, so do not over use it, if you look for portability.&nbsp;`Helvetica`&nbsp;and&nbsp;`Courier`&nbsp;should be available on all system.

A lot of parameters are available. You can list them using the following command:


``` colo
java -jar plantuml.jar -language
```

## Text Alignment

Text alignment can be set up to&nbsp;`left`,&nbsp;`right`&nbsp;or&nbsp;`center`. You can also use&nbsp;`direction`&nbsp;or&nbsp;`reverseDirection`&nbsp;values for&nbsp;`sequenceMessageAlign`&nbsp;which align text depending on arrow direction.

| **Param name** | **Default value** | **Comment** |
|---|---|---|
| sequenceMessageAlign | left | Used for messages in sequence diagrams |
| sequenceReferenceAlign | center | Used for&nbsp;`ref over`&nbsp;in sequence diagrams |

``` puml {hide=false}
@startuml
skinparam sequenceMessageAlign center
Alice -> Bob : Hi
Alice -> Bob : This is very long
@enduml
```

## Examples

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

![](https://s.plantuml.com/imgw/img-ab0c2808251a3cd0c664adc48f2b7e7b.png " ")

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

![](https://s.plantuml.com/imgw/img-26c5018c0e5d925d3056102e62971b0a.png " ")

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

![](https://s.plantuml.com/imgw/img-7ce6460ac7ecd8d142307925ca655482.png " ")

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

![](https://s.plantuml.com/imgw/img-b225bc95f0919debb286fd228ee3bd50.png " ")


Since the documentation is not always up to date, you can have the complete list of parameters using this command:



``` colo
java -jar plantuml.jar -language
```

Or you can generate a "diagram" with a list of all the skinparam parameters using:

That will give you the following result:

``` puml {hide=false}
@startuml
help skinparams
@enduml
```

You can also view each skinparam parameters with its results displayed at&nbsp;[https://plantuml-documentation.readthedocs.io/en/latest/formatting/all-skin-params.html](https://plantuml-documentation.readthedocs.io/en/latest/formatting/all-skin-params.html).


