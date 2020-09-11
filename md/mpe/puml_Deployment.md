# Deployment Diagram



## Declaring element!


``` puml {hide=false}
@startuml
actor actor
agent agent
artifact artifact
boundary boundary
card card
cloud cloud
component component
control control
database database
entity entity
file file
folder folder
frame frame
interface  interface
node node
package package
queue queue
stack stack
rectangle rectangle
storage storage
usecase usecase
@enduml
```

![](https://s.plantuml.com/imgw/img-2765b6f63840739993ef0e1553086814.webp " ")





You can optionaly put text using bracket&nbsp;`[]`&nbsp;for a long description.





``` puml {hide=false}
@startuml
folder folder [
This is a <b>folder
----
You can use separator
====
of different kind
....
and style
]

node node [
This is a <b>node
----
You can use separator
====
of different kind
....
and style
]

database database [
This is a <b>database
----
You can use separator
====
of different kind
....
and style
]

usecase usecase [
This is a <b>usecase
----
You can use separator
====
of different kind
....
and style
]

card card [
This is a <b>card
----
You can use separator
====
of different kind
....
and style
<i><color:blue>(add from V1.2020.7)</color></i>
]
@enduml
```

![](https://s.plantuml.com/imgw/img-99b73a69ff67bc2bd388b9572db75186.webp " ")



## Linking!



You can create simple links between elements with or without labels:



``` puml {hide=false}
@startuml

node node1
node node2
node node3
node node4
node node5
node1 -- node2 : label1
node1 .. node3 : label2
node1 ~~ node4 : label3
node1 == node5

@enduml
```

![](https://s.plantuml.com/imgw/img-f28185d21a8e081fa83335762757227f.webp " ")







It is possible to use several types of links:





``` puml {hide=false}
@startuml

artifact artifact1
artifact artifact2
artifact artifact3
artifact artifact4
artifact artifact5
artifact artifact6
artifact artifact7
artifact artifact8
artifact artifact9
artifact artifact10
artifact1 --> artifact2
artifact1 --* artifact3
artifact1 --o artifact4
artifact1 --+ artifact5
artifact1 --# artifact6
artifact1 -->> artifact7
artifact1 --0 artifact8
artifact1 --^ artifact9
artifact1 --(0 artifact10

@enduml
```

![](https://s.plantuml.com/imgw/img-f76fba39c57a04b2c85dd56a1843ee32.webp " ")





You can also have the following types:





``` puml {hide=false}
@startuml

cloud cloud1
cloud cloud2
cloud cloud3
cloud cloud4
cloud cloud5
cloud1 -0- cloud2
cloud1 -0)- cloud3
cloud1 -(0- cloud4
cloud1 -(0)- cloud5

@enduml
```

![](https://s.plantuml.com/imgw/img-9c0be41f04404ca41396e4087b0ca0b7.webp " ")





## Packages!

_There is a limit of three levels._



``` puml {hide=false}
@startuml
artifact Foo1 {
  folder Foo2
}

folder Foo3 {
  artifact Foo4
}

frame Foo5 {
  database Foo6
}

cloud vpc {
  node ec2 {
    stack stack
  }
}

@enduml
```

![](https://s.plantuml.com/imgw/img-14d4e8057e06cbbabe7160fa5ccb1e67.webp " ")







``` puml {hide=false}
@startuml
node Foo1 {
 cloud Foo2
}

cloud Foo3 {
  frame Foo4
}

database Foo5  {
  storage Foo6
}

storage Foo7 {
  storage Foo8
}
@enduml
```

![](https://s.plantuml.com/imgw/img-8b09f3457fa4b897ca93b9092499b324.webp " ")





## Round corner!



``` puml {hide=false}
@startuml
skinparam rectangle {
    roundCorner<<Concept>> 25
}

rectangle "Concept Model" <<Concept>> {
rectangle "Example 1" <<Concept>> as ex1
rectangle "Another rectangle"
}
@enduml
```

![](https://s.plantuml.com/imgw/img-e6bc472b7ac51eb6be777e01e83e22a0.webp " ")