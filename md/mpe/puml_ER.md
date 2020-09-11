# Entity Relationship Diagram

*  [Information Engineering Relations](https://plantuml.com/zh/ie-diagram#a33822c778959028)
*  [Entities](https://plantuml.com/zh/ie-diagram#ea995898864fb0ea)
*  [Complete Example](https://plantuml.com/zh/ie-diagram#06a40b5d1c1792ac)



Based on the Information Engineering notation.



This is an extension to the existing&nbsp;[Class Diagram](https://plantuml.com/zh/class-diagram). This extension adds:



*  Additional relations for the Information Engineering notation.
*  An&nbsp;`entity`&nbsp;alias that maps to the class diagram&nbsp;`class`.
*  An additional visibility modifier&nbsp;`*`&nbsp;to identify mandatory attributes.



Otherwise, the syntax for drawing diagrams is the same as for class diagrams. All other features of class diagrams are also supported.


## Information Engineering Relations


|   |   |
|---|---|
| **Type** | **Symbol** |
| Zero or One | `|o--` |
| Exactly One | `||--` |
| Zero or Many | `}o--` |
| One or Many | `}|--` |



Examples:

``` puml {hide = false}
@startuml
Entity01 }|..|| Entity02
Entity03 }o..o| Entity04
Entity05 ||--o{ Entity06
Entity07 |o--|| Entity08
@enduml
```

![](https://s.plantuml.com/imgw/img-fb96d1c2fb60783af7fd451305a8369b.png " ")





## Entities

```  puml {hide = false}
@startuml
entity Entity01 {
  * identifying_attribute
  --
  * mandatory_attribute
  optional_attribute
}
@enduml
```

![](https://s.plantuml.com/imgw/img-6d90c1a8f24e3b8946b8c1e2f729bb18.png " ")





Again, this is the normal class diagram syntax (aside from use of&nbsp;`entity`&nbsp;instead of&nbsp;`class`). Anything that you can do in a class diagram can be done here.



The&nbsp;`*`&nbsp;visibility modifier can be used to identify mandatory attributes. A space can be used after the modifier character to avoid conflicts with the creole bold:





```  puml {hide = false}
@startuml
entity Entity01 {
   optional attribute
   **optional bold attribute**
   * **mandatory bold attribute**
}
@enduml
```

![](https://s.plantuml.com/imgw/img-8a81864c82773e1a280b1ed70a4d3cb3.png " ")





## Complete Example

```  puml {hide = false}
@startuml

' hide the spot
hide circle

' avoid problems with angled crows feet
skinparam linetype ortho

entity "Entity01" as e01 {
  *e1_id : number <<generated>>
  --
  *name : text
  description : text
}

entity "Entity02" as e02 {
  *e2_id : number <<generated>>
  --
  *e1_id : number <<FK>>
  other_details : text
}

entity "Entity03" as e03 {
  *e3_id : number <<generated>>
  --
  e1_id : number <<FK>>
  other_details : text
}

e01 ||..o{ e02
e01 |o..o{ e03

@enduml
```

![](https://s.plantuml.com/imgw/img-1813044cb8a612aa1072e444ceee311e.png " ")