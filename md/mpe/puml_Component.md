# Component Diagram

Let's have few examples :

## Components!

Components must be bracketed.



You can also use the&nbsp;`component`&nbsp;keyword to define a component. And you can define an alias, using the&nbsp;`as`&nbsp;keyword. This alias will be used later, when defining relations.



``` puml {hide=false}
@startuml

[First component]
[Another component] as Comp2
component Comp3
component [Last\ncomponent] as Comp4

@enduml
```

![](https://s.plantuml.com/imgw/img-d38b34471458304f1b23a9ccf903b644.webp " ")



## Interfaces!



Interface can be defined using the&nbsp;`()`&nbsp;symbol (because this looks like a circle).



You can also use the&nbsp;`interface`&nbsp;keyword to define an interface. And you can define an alias, using the&nbsp;`as`&nbsp;keyword. This alias will be used latter, when defining relations.



We will see latter that interface definition is optional.



``` puml {hide=false}
@startuml

() "First Interface"
() "Another interface" as Interf2
interface Interf3
interface "Last\ninterface" as Interf4

@enduml
```

![](https://s.plantuml.com/imgw/img-33f282bb05dfd5441993d2477dcf78c7.webp " ")





## Basic example!







Links between elements are made using combinations of dotted line (`..`), straight line (`--`), and arrows (`-->`) symbols.



``` puml {hide=false}
@startuml

DataAccess - [First Component]
[First Component] ..> HTTP : use

@enduml
```

![](https://s.plantuml.com/imgw/img-5363532f7dbebb37e38b608fd2c3f088.webp " ")



## Using notes!



You can use the&nbsp;`note left of`&nbsp;,&nbsp;`note right of`&nbsp;,&nbsp;`note top of`&nbsp;,&nbsp;`note bottom of`&nbsp;keywords to define notes related to a single object.





A note can be also define alone with the&nbsp;`note`&nbsp;keywords, then linked to other objects using the&nbsp;`..`&nbsp;symbol.





``` puml {hide=false}
@startuml

interface "Data Access" as DA

DA - [First Component]
[First Component] ..> HTTP : use

note left of HTTP : Web Service only

note right of [First Component]
  A note can also
  be on several lines
end note

@enduml
```

![](https://s.plantuml.com/imgw/img-acdf42c2140ee45f14d28290a901f387.webp " ")





## Grouping Components!



You can use several keywords to group components and interfaces together:

*  `package`
*  `node`
*  `folder`
*  `frame`
*  `cloud`
*  `database`





``` puml {hide=false}
@startuml

package "Some Group" {
  HTTP - [First Component]
  [Another Component]
}

node "Other Groups" {
  FTP - [Second Component]
  [First Component] --> FTP
}

cloud {
  [Example 1]
}


database "MySql" {
  folder "This is my folder" {
    [Folder 3]
  }
  frame "Foo" {
    [Frame 4]
  }
}


[Another Component] --> [Example 1]
[Example 1] --> [Folder 3]
[Folder 3] --> [Frame 4]

@enduml
```

![](https://s.plantuml.com/imgw/img-e8d1d91b290d3f0aa6415a4104fb6df1.webp " ")



## Changing arrows direction!





By default, links between classes have two dashes&nbsp;`--`&nbsp;and are vertically oriented. It is possible to use horizontal link by putting a single dash (or dot) like this:





``` puml {hide=false}
@startuml
[Component] --> Interface1
[Component] -> Interface2
@enduml
```

![](https://s.plantuml.com/imgw/img-c85826d7379c7603b28c7bef9d2a0ddc.webp " ")





You can also change directions by reversing the link:





``` puml {hide=false}
@startuml
Interface1 <-- [Component]
Interface2 <- [Component]
@enduml
```

![](https://s.plantuml.com/imgw/img-01659347735112df0fb5d25bdbf42f95.webp " ")





It is also possible to change arrow direction by adding&nbsp;`left`,&nbsp;`right`,&nbsp;`up`&nbsp;or&nbsp;`down`&nbsp;keywords inside the arrow:





``` puml {hide=false}
@startuml
[Component] -left-> left
[Component] -right-> right
[Component] -up-> up
[Component] -down-> down
@enduml
```

![](https://s.plantuml.com/imgw/img-8bdcabe9ba63fa69bd2726459b45e9e9.webp " ")





You can shorten the arrow by using only the first character of the direction (for example,&nbsp;`-d-`&nbsp;instead of&nbsp;`-down-`) or the two first characters (`-do-`).



Please note that you should not abuse this functionality :&nbsp;_Graphviz_&nbsp;gives usually good results without tweaking.



## Use UML2 notation!



By default&nbsp;_(from v1.2020.13-14)_, UML2 notation is used.





``` puml {hide=false}
@startuml

interface "Data Access" as DA

DA - [First Component]
[First Component] ..> HTTP : use

@enduml
```

![](https://s.plantuml.com/imgw/img-a85d5cd78511b899e15aee33728b0015.webp " ")



## Use UML1 notation!



The&nbsp;`skinparam componentStyle uml1`&nbsp;command is used to switch to UML1 notation.



``` puml {hide=false}
@startuml
skinparam componentStyle uml1

interface "Data Access" as DA

DA - [First Component]
[First Component] ..> HTTP : use

@enduml
```

![](https://s.plantuml.com/imgw/img-fd594f319d331a18146647f02086426b.webp " ")



## Use rectangle notation (remove UML notation)!



The&nbsp;`skinparam componentStyle rectangle`&nbsp;command is used to switch to rectangle notation&nbsp;_(without any UML notation)_.



``` puml {hide=false}
@startuml
skinparam componentStyle rectangle

interface "Data Access" as DA

DA - [First Component]
[First Component] ..> HTTP : use

@enduml
```

![](https://s.plantuml.com/imgw/img-da319ccd3d5a9d40d955d798ff92c677.webp " ")



## Long description!

It is possible to put description on several lines using square brackets.



``` puml {hide=false}
@startuml
component comp1 [
This component
has a long comment
on several lines
]
@enduml
```

![](https://s.plantuml.com/imgw/img-20800318e78b7cda312ff2c1097ae76c.webp " ")



## Individual colors!





You can specify a color after component definition.



``` puml {hide=false}
@startuml
component  [Web Server] #Yellow
@enduml
```

![](https://s.plantuml.com/imgw/img-f84e8e62cbb9d7bfdc5cfd66b7d13e02.webp " ")



## Using Sprite in Stereotype!

You can use sprites within stereotype components.



``` puml {hide=false}
@startuml
sprite $businessProcess [16x16/16] {
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFF0FFFFF
FFFFFFFFFF00FFFF
FF00000000000FFF
FF000000000000FF
FF00000000000FFF
FFFFFFFFFF00FFFF
FFFFFFFFFF0FFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
FFFFFFFFFFFFFFFF
}


rectangle " End to End\nbusiness process" <<$businessProcess>> {
 rectangle "inner process 1" <<$businessProcess>> as src
 rectangle "inner process 2" <<$businessProcess>> as tgt
 src -> tgt
}
@enduml
```

![](https://s.plantuml.com/imgw/img-e2ac56a26786b9e0d70582c76a8ac408.webp " ")





## Skinparam!







You can use the&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;command to change colors and fonts for the drawing.



You can use this command :

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in the&nbsp;[command line](https://plantuml.com/en/command-line)&nbsp;or the&nbsp;[ANT task](https://plantuml.com/en/ant-task).



You can define specific color and fonts for stereotyped components and interfaces.





``` puml {hide=false}
@startuml

skinparam interface {
  backgroundColor RosyBrown
  borderColor orange
}

skinparam component {
  FontSize 13
  BackgroundColor<<Apache>> Red
  BorderColor<<Apache>> #FF6655
  FontName Courier
  BorderColor black
  BackgroundColor gold
  ArrowFontName Impact
  ArrowColor #FF6655
  ArrowFontColor #777777
}

() "Data Access" as DA

DA - [First Component]
[First Component] ..> () HTTP : use
HTTP - [Web Server] << Apache >>

@enduml
```

![](https://s.plantuml.com/imgw/img-6c26a60ac330b6a215737304d61db4c5.webp " ")







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

![](https://s.plantuml.com/imgw/img-aeda069cc7461754cd240925e09f10a6.webp " ")