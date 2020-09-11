## Usecases!

Use cases are enclosed using between parentheses (because two parentheses looks like an oval).



You can also use the&nbsp;`usecase`&nbsp;keyword to define a usecase. And you can define an alias, using the&nbsp;`as`&nbsp;keyword. This alias will be used later, when defining relations.


``` puml {hide=false}
@startuml

(First usecase)
(Another usecase) as (UC2)
usecase UC3
usecase (Last\nusecase) as UC4

@enduml
```

![](https://s.plantuml.com/imgw/img-e61b9eee50160c816925bc6d43f7717b.webp " ")



## Actors!



Actor are enclosed using between two points.



You can also use the&nbsp;`actor`&nbsp;keyword to define an actor. And you can define an alias, using the&nbsp;`as`&nbsp;keyword. This alias will be used latter, when defining relations.



We will see later that the actor definitions are optional.



``` puml {hide=false}
@startuml

:First Actor:
:Another\nactor: as Men2
actor Men3
actor :Last actor: as Men4

@enduml
```

![](https://s.plantuml.com/imgw/img-cd1037cddb63993f47ce5e7bb1fe385f.webp " ")





## Usecases description!





If you want to have description on several lines, you can use quotes.



You can also use the following separators:&nbsp;`--``..``==``__`. And you can put titles within the separators.





``` puml {hide=false}
@startuml

usecase UC1 as "You can use
several lines to define your usecase.
You can also use separators.
--
Several separators are possible.
==
And you can add titles:
..Conclusion..
This allows large description."

@enduml
```

![](https://s.plantuml.com/imgw/img-b145036676f1f9ac9b09ed86e7ae20fb.webp " ")





## Use package!



You can use packages to group actors or use cases.





``` puml {hide=false}
@startuml
left to right direction
actor "Food Critic" as fc
package Restaurant {
  usecase "Eat Food" as UC1
  usecase "Pay for Food" as UC2
  usecase "Drink" as UC3
}
fc --> UC1
fc --> UC2
fc --> UC3
@enduml
```

![](https://s.plantuml.com/imgw/img-3c31dc8f7addbec5e4e9c13507d17f50.webp " ")







You can use&nbsp;`rectangle`&nbsp;to change the display of the package.





``` puml {hide=false}
@startuml
left to right direction
actor "Food Critic" as fc
rectangle Restaurant {
  usecase "Eat Food" as UC1
  usecase "Pay for Food" as UC2
  usecase "Drink" as UC3
}
fc --> UC1
fc --> UC2
fc --> UC3
@enduml
```

![](https://s.plantuml.com/imgw/img-2ab899c177d4c66e2278f31205787a32.webp " ")



## Basic example!





To link actors and use cases, the arrow&nbsp;`-->`&nbsp;is used.



The more dashes&nbsp;`-`&nbsp;in the arrow, the longer the arrow. You can add a label on the arrow, by adding a&nbsp;`:`&nbsp;character in the arrow definition.



In this example, you see that&nbsp;_User_&nbsp;has not been defined before, and is used as an actor.



``` puml {hide=false}
@startuml

User -> (Start)
User --> (Use the application) : A small label

:Main Admin: ---> (Use the application) : This is\nyet another\nlabel

@enduml
```

![](https://s.plantuml.com/imgw/img-8c206464481f69d71b82a0da80df338c.webp " ")







## Extension!



If one actor/use case extends another one, you can use the symbol&nbsp;`<|--`.





``` puml {hide=false}
@startuml
:Main Admin: as Admin
(Use the application) as (Use)

User <|-- Admin
(Start) <|-- (Use)

@enduml
```

![](https://s.plantuml.com/imgw/img-136bb393a785f71c1afbbe582615fcb0.webp " ")





## Using notes!



You can use the&nbsp;`note left of`&nbsp;,&nbsp;`note right of`&nbsp;,&nbsp;`note top of`&nbsp;,&nbsp;`note bottom of`&nbsp;keywords to define notes related to a single object.



A note can be also define alone with the&nbsp;`note`&nbsp;keywords, then linked to other objects using the&nbsp;`..`&nbsp;symbol.





``` puml {hide=false}
@startuml
:Main Admin: as Admin
(Use the application) as (Use)

User -> (Start)
User --> (Use)

Admin ---> (Use)

note right of Admin : This is an example.

note right of (Use)
  A note can also
  be on several lines
end note

note "This note is connected\nto several objects." as N2
(Start) .. N2
N2 .. (Use)
@enduml
```

![](https://s.plantuml.com/imgw/img-26013365a8de406e03b58632daa37c6f.webp " ")





## Stereotypes!



You can add stereotypes while defining actors and use cases using&nbsp;`<<`&nbsp;and&nbsp;`>>`.





``` puml {hide=false}
@startuml
User << Human >>
:Main Database: as MySql << Application >>
(Start) << One Shot >>
(Use the application) as (Use) << Main >>

User -> (Start)
User --> (Use)

MySql --> (Use)

@enduml
```

![](https://s.plantuml.com/imgw/img-3bad7df2db4d7392b5cf54324a140de2.webp " ")





## Changing arrows direction!



By default, links between classes have two dashes&nbsp;`--`&nbsp;and are vertically oriented. It is possible to use horizontal link by putting a single dash (or dot) like this:





``` puml {hide=false}
@startuml
:user: --> (Use case 1)
:user: -> (Use case 2)
@enduml
```

![](https://s.plantuml.com/imgw/img-e6636c5788b9f9e3f07e71d4d0ef4efa.webp " ")





You can also change directions by reversing the link:





``` puml {hide=false}
@startuml
(Use case 1) <.. :user:
(Use case 2) <- :user:
@enduml
```

![](https://s.plantuml.com/imgw/img-f3cfda53e2b0a564581772af162898cb.webp " ")





It is also possible to change arrow direction by adding&nbsp;`left`,&nbsp;`right`,&nbsp;`up`&nbsp;or&nbsp;`down`&nbsp;keywords inside the arrow:





``` puml {hide=false}
@startuml
:user: -left-> (dummyLeft)
:user: -right-> (dummyRight)
:user: -up-> (dummyUp)
:user: -down-> (dummyDown)
@enduml
```

![](https://s.plantuml.com/imgw/img-9fbf57fdf0d000baf6511711c363054c.webp " ")





You can shorten the arrow by using only the first character of the direction (for example,&nbsp;`-d-`&nbsp;instead of&nbsp;`-down-`) or the two first characters (`-do-`).



Please note that you should not abuse this functionality :&nbsp;_Graphviz_&nbsp;gives usually good results without tweaking.



## Splitting diagrams!



The&nbsp;`newpage`&nbsp;keywords to split your diagram into several pages or images.



``` puml {hide=false}
@startuml
:actor1: --> (Usecase1)
newpage
:actor2: --> (Usecase2)
@enduml
```

![](https://s.plantuml.com/imgw/img-af5d88565d1e6dfaef02d17d61534369.webp " ")





## Left to right direction!



The general default behavior when building diagram is&nbsp;**top to bottom**.



``` puml {hide=false}
@startuml
'default
top to bottom direction
user1 --> (Usecase 1)
user2 --> (Usecase 2)

@enduml
```

![](https://s.plantuml.com/imgw/img-abd23f318b799cbe36aaf6e75eb539a1.webp " ")

You may change to&nbsp;**left to right**&nbsp;using the&nbsp;`left to right direction`&nbsp;command. The result is often better with this direction.





``` puml {hide=false}
@startuml

left to right direction
user1 --> (Usecase 1)
user2 --> (Usecase 2)

@enduml
```

![](https://s.plantuml.com/imgw/img-45a1ba0300e1109e3f7c86502973574a.webp " ")





## Skinparam!





You can use the&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;command to change colors and fonts for the drawing.



You can use this command :

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in&nbsp;[the command line](https://plantuml.com/en/command-line)&nbsp;or&nbsp;[the ANT task](https://plantuml.com/en/ant-task).



You can define specific color and fonts for stereotyped actors and usecases.





``` puml {hide=false}
@startuml
skinparam handwritten true

skinparam usecase {
BackgroundColor DarkSeaGreen
BorderColor DarkSlateGray

BackgroundColor<< Main >> YellowGreen
BorderColor<< Main >> YellowGreen

ArrowColor Olive
ActorBorderColor black
ActorFontName Courier

ActorBackgroundColor<< Human >> Gold
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

![](https://s.plantuml.com/imgw/img-5808dfcf6367f10d46b2e76df2b6716f.webp " ")





## Complete example!







``` puml {hide=false}
@startuml
left to right direction
skinparam packageStyle rectangle
actor customer
actor clerk
rectangle checkout {
  customer -- (checkout)
  (checkout) .> (payment) : include
  (help) .> (checkout) : extends
  (checkout) -- clerk
}
@enduml
```