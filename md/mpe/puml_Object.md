# Object Diagram


## Definition of objects!



You define instance of objects using the&nbsp;`object`&nbsp;keywords.





``` puml {hide=false}
@startuml
object firstObject
object "My Second Object" as o2
@enduml
```

![](https://s.plantuml.com/imgw/img-ae6c98cbd3cf700780a83a960a4a3253.webp " ")





## Relations between objects!



Relations between objects are defined using the following symbols :



|   |   |   |
|---|---|---|
| **Type** | **Symbol** | **Image** |
| Extension | `<|--` | ![](https://s.plantuml.com/img/extends01.png " ") |
| Composition | `*--` | ![](https://s.plantuml.com/img/sym03.png " ") |
| Aggregation | `o--` | ![](https://s.plantuml.com/img/sym01.png " ") |



It is possible to replace&nbsp;`--`&nbsp;by&nbsp;`..`&nbsp;to have a dotted line.



Knowing those rules, it is possible to draw the following drawings.



It is possible a add a label on the relation, using&nbsp;`:`&nbsp;followed by the text of the label.



For cardinality, you can use double-quotes&nbsp;`""`&nbsp;on each side of the relation.







``` puml {hide=false}
@startuml
object Object01
object Object02
object Object03
object Object04
object Object05
object Object06
object Object07
object Object08

Object01 <|-- Object02
Object03 *-- Object04
Object05 o-- "4" Object06
Object07 .. Object08 : some labels
@enduml
```

![](https://s.plantuml.com/imgw/img-1d4b5bd3694ae89a540fbd8b8bdde536.webp " ")



## Adding fields!



To declare fields, you can use the symbol&nbsp;`:`&nbsp;followed by the field's name.





``` puml {hide=false}
@startuml

object user

user : name = "Dummy"
user : id = 123

@enduml
```

![](https://s.plantuml.com/imgw/img-d56acbdd7e5512c97ec566d6889d54bc.webp " ")





It is also possible to group all fields between brackets&nbsp;`{}`.





``` puml {hide=false}
@startuml

object user {
  name = "Dummy"
  id = 123
}

@enduml
```

![](https://s.plantuml.com/imgw/img-a6b63fe169d36f1cbcf459b2c225b450.webp " ")



## Common features with class diagrams!



*  [Hide attributes, methods...](https://plantuml.com/en/class-diagram#Hide)
*  [Defines notes](https://plantuml.com/en/class-diagram#Notes)
*  [Use packages](https://plantuml.com/en/class-diagram#Using)
*  [Skin the output](https://plantuml.com/en/class-diagram#Skinparam)