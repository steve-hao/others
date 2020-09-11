# Class Diagram

## Relations between classes!



Relations between classes are defined using the following symbols :



|   |   |   |
|---|---|---|
| **Type** | **Symbol** | **Drawing** |
| Extension | `<|--` | ![](https://s.plantuml.com/img/extends01.png " ") |
| Composition | `*--` | ![](https://s.plantuml.com/img/sym03.png " ") |
| Aggregation | `o--` | ![](https://s.plantuml.com/img/sym01.png " ") |



It is possible to replace&nbsp;`--`&nbsp;by&nbsp;`..`&nbsp;to have a dotted line.



Knowing those rules, it is possible to draw the following drawings:



``` puml {hide=false}
@startuml
Class01 <|-- Class02
Class03 *-- Class04
Class05 o-- Class06
Class07 .. Class08
Class09 -- Class10
@enduml
```

![](https://s.plantuml.com/imgw/img-8a8566b64549ea0be3aa1766f826e18e.webp " ")







``` puml {hide=false}
@startuml
Class11 <|.. Class12
Class13 --> Class14
Class15 ..> Class16
Class17 ..|> Class18
Class19 <--* Class20
@enduml
```

![](https://s.plantuml.com/imgw/img-8b16298f44d24265c332e2486843ba16.webp " ")







``` puml {hide=false}
@startuml
Class21 #-- Class22
Class23 x-- Class24
Class25 }-- Class26
Class27 +-- Class28
Class29 ^-- Class30
@enduml
```

![](https://s.plantuml.com/imgw/img-bffef1e31fd78f56c967fa15a3ee81f8.webp " ")





## Label on relations!





It is possible to add a label on the relation, using&nbsp;`:`, followed by the text of the label.



For cardinality, you can use double-quotes&nbsp;`""`&nbsp;on each side of the relation.







``` puml {hide=false}
@startuml

Class01 "1" *-- "many" Class02 : contains

Class03 o-- Class04 : aggregation

Class05 --> "1" Class06

@enduml
```

![](https://s.plantuml.com/imgw/img-116949787ed3aef83fd1e728c7369456.webp " ")





You can add an extra arrow pointing at one object showing which object acts on the other object, using&nbsp;`<`&nbsp;or&nbsp;`>`&nbsp;at the begin or at the end of the label.







``` puml {hide=false}
@startuml
class Car

Driver - Car : drives >
Car *- Wheel : have 4 >
Car -- Person : < owns

@enduml
```

![](https://s.plantuml.com/imgw/img-42c68bf93aa2d82dc2e7d29c969412ad.webp " ")



## Adding methods!



To declare fields and methods, you can use the symbol&nbsp;`:`&nbsp;followed by the field's or method's name.



The system checks for parenthesis to choose between methods and fields.





``` puml {hide=false}
@startuml
Object <|-- ArrayList

Object : equals()
ArrayList : Object[] elementData
ArrayList : size()

@enduml
```

![](https://s.plantuml.com/imgw/img-f3bf564be8a5504cfd39fe815dbe5e04.webp " ")







It is also possible to group between brackets&nbsp;`{}`&nbsp;all fields and methods.



Note that the syntax is highly flexible about type/name order.







``` puml {hide=false}
@startuml
class Dummy {
  String data
  void methods()
}

class Flight {
   flightNumber : Integer
   departureTime : Date
}
@enduml
```

![](https://s.plantuml.com/imgw/img-87b86c3d490e759a636ebd51ccd45747.webp " ")





You can use&nbsp;`{field}`&nbsp;and&nbsp;`{method}`&nbsp;modifiers to override default behaviour of the parser about fields and methods.



``` puml {hide=false}
@startuml
class Dummy {
  {field} A field (despite parentheses)
  {method} Some method
}

@enduml
```

![](https://s.plantuml.com/imgw/img-01bf63a2c52762c7ef79c7b5a927ee0c.webp " ")





## Defining visibility!



When you define methods or fields, you can use characters to define the visibility of the corresponding item:



|   |   |   |   |
|---|---|---|---|
| **Character** | **Icon for field** | **Icon for method** | **Visibility** |
| `-` | ![](https://s.plantuml.com/img/private-field.png " ") | ![](https://s.plantuml.com/img/private-method.png " ") | private |
| `#` | ![](https://s.plantuml.com/img/protected-field.png " ") | ![](https://s.plantuml.com/img/protected-method.png " ") | protected |
| `~` | ![](https://s.plantuml.com/img/package-private-field.png " ") | ![](https://s.plantuml.com/img/package-private-method.png " ") | package private |
| `+` | ![](https://s.plantuml.com/img/public-field.png " ") | ![](https://s.plantuml.com/img/public-method.png " ") | public |





``` puml {hide=false}
@startuml

class Dummy {
 -field1
 #field2
 ~method1()
 +method2()
}

@enduml
```

![](https://s.plantuml.com/imgw/img-6088283dc83e2b7e5c90f98a0f04cb75.webp " ")







You can turn off this feature using the&nbsp;`skinparam classAttributeIconSize 0`&nbsp;command :







``` puml {hide=false}
@startuml
skinparam classAttributeIconSize 0
class Dummy {
 -field1
 #field2
 ~method1()
 +method2()
}

@enduml
```

![](https://s.plantuml.com/imgw/img-97677ab78769234abc5c78a0388b7baf.webp " ")





## Abstract and Static!







You can define static or abstract methods or fields using the&nbsp;`{static}`&nbsp;or&nbsp;`{abstract}`&nbsp;modifier.



These modifiers can be used at the start or at the end of the line. You can also use&nbsp;`{classifier}`&nbsp;instead of&nbsp;`{static}`.





``` puml {hide=false}
@startuml
class Dummy {
  {static} String id
  {abstract} void methods()
}
@enduml
```

![](https://s.plantuml.com/imgw/img-5646cfbf7f73f2fa087cd532607e218e.webp " ")





## Advanced class body!







By default, methods and fields are automatically regrouped by PlantUML. You can use separators to define your own way of ordering fields and methods. The following separators are possible :&nbsp;`--``..``==``__`.



You can also use titles within the separators:







``` puml {hide=false}
@startuml
class Foo1 {
  You can use
  several lines
  ..
  as you want
  and group
  ==
  things together.
  __
  You can have as many groups
  as you want
  --
  End of class
}

class User {
  .. Simple Getter ..
  + getName()
  + getAddress()
  .. Some setter ..
  + setName()
  __ private data __
  int age
  -- encrypted --
  String password
}

@enduml
```

![](https://s.plantuml.com/imgw/img-9489865cec397c11ab976e56b75061b3.webp " ")



## Notes and stereotypes!



Stereotypes are defined with the&nbsp;`class`&nbsp;keyword,&nbsp;`<<`&nbsp;and&nbsp;`>>`.



You can also define notes using&nbsp;`note left of`&nbsp;,&nbsp;`note right of`&nbsp;,&nbsp;`note top of`&nbsp;,&nbsp;`note bottom of`&nbsp;keywords.



You can also define a note on the last defined class using&nbsp;`note left`,&nbsp;`note right`,&nbsp;`note top`,&nbsp;`note bottom`.



A note can be also define alone with the&nbsp;`note`&nbsp;keywords, then linked to other objects using the&nbsp;`..`&nbsp;symbol.





``` puml {hide=false}
@startuml
class Object << general >>
Object <|--- ArrayList

note top of Object : In java, every class\nextends this one.

note "This is a floating note" as N1
note "This note is connected\nto several objects." as N2
Object .. N2
N2 .. ArrayList

class Foo
note left: On last defined class

@enduml
```

![](https://s.plantuml.com/imgw/img-d0f9999eaad1c65e000fbb4d7ef96ecc.webp " ")





## More on notes!





It is also possible to use few html tags like :



*  `<b>`
*  `<u>`
*  `<i>`
*  `<s>`,&nbsp;`<del>`,&nbsp;`<strike>`
*  `<font color="#AAAAAA">`&nbsp;or&nbsp;`<font color="colorName">`
*  `<color:#AAAAAA>`&nbsp;or&nbsp;`<color:colorName>`
*  `<size:nn>`&nbsp;to change font size
*  `<img src="file">`&nbsp;or&nbsp;`<img:file>`: the file must be accessible by the filesystem





You can also have a note on several lines.



You can also define a note on the last defined class using&nbsp;`note left`,&nbsp;`note right`,&nbsp;`note top`,&nbsp;`note bottom`.



``` puml {hide=false}
@startuml

class Foo
note left: On last defined class

note top of Object
  In java, <size:18>every</size> <u>class</u>
  <b>extends</b>
  <i>this</i> one.
end note

note as N1
  This note is <u>also</u>
  <b><color:royalBlue>on several</color>
  <s>words</s> lines
  And this is hosted by <img:sourceforge.jpg>
end note

@enduml
```

![](https://s.plantuml.com/imgw/img-82edb84b8711940fa7770c57f3e775f6.webp " ")





## Note on links!





It is possible to add a note on a link, just after the link definition, using&nbsp;`note on link`.



You can also use&nbsp;`note left on link`,&nbsp;`note right on link`,&nbsp;`note top on link`,&nbsp;`note bottom on link`&nbsp;if you want to change the relative position of the note with the label.





``` puml {hide=false}
@startuml

class Dummy
Dummy --> Foo : A link
note on link #red: note that is red

Dummy --> Foo2 : Another link
note right on link #blue
this is my note on right link
and in blue
end note

@enduml
```

![](https://s.plantuml.com/imgw/img-f24bf1baeb85b4e647be9aa7088fa252.webp " ")





## Abstract class and interface!





You can declare a class as abstract using&nbsp;`abstract`&nbsp;or&nbsp;`abstract class`&nbsp;keywords.



The class will be printed in&nbsp;_italic_.





You can use the&nbsp;`interface`,&nbsp;`annotation`&nbsp;and&nbsp;`enum`&nbsp;keywords too.





``` puml {hide=false}
@startuml

abstract class AbstractList
abstract AbstractCollection
interface List
interface Collection

List <|-- AbstractList
Collection <|-- AbstractCollection

Collection <|- List
AbstractCollection <|- AbstractList
AbstractList <|-- ArrayList

class ArrayList {
  Object[] elementData
  size()
}

enum TimeUnit {
  DAYS
  HOURS
  MINUTES
}

annotation SuppressWarnings

@enduml
```

![](https://s.plantuml.com/imgw/img-ef23d3004114e1e95de7433c0b8eff2a.webp " ")





## Using non-letters!





If you want to use&nbsp;[non-letters](https://plantuml.com/en/unicode)&nbsp;in the class (or enum...) display, you can either :

*  Use the&nbsp;`as`&nbsp;keyword in the class definition
*  Put quotes&nbsp;`""`&nbsp;around the class name





``` puml {hide=false}
@startuml
class "This is my class" as class1
class class2 as "It works this way too"

class2 *-- "foo/dummy" : use
@enduml
```

![](https://s.plantuml.com/imgw/img-cea7a88b81515bce7d05759ac0c0f962.webp " ")





## Hide attributes, methods...!



You can parameterize the display of classes using the&nbsp;`hide/show`&nbsp;command.



The basic command is:&nbsp;`hide empty members`. This command will hide attributes or methods if they are empty.



Instead of&nbsp;`empty members`, you can use:

*  `empty fields`&nbsp;or&nbsp;`empty attributes`&nbsp;for empty fields,
*  `empty methods`&nbsp;for empty methods,
*  `fields`&nbsp;or&nbsp;`attributes`&nbsp;which will hide fields, even if they are described,
*  `methods`&nbsp;which will hide methods, even if they are described,
*  `members`&nbsp;which will hide fields&nbsp;<u>and</u>&nbsp;methods, even if they are described,
*  `circle`&nbsp;for the circled character in front of class name,
*  `stereotype`&nbsp;for the stereotype.



You can also provide, just after the&nbsp;`hide`&nbsp;or&nbsp;`show`&nbsp;keyword:

*  `class`&nbsp;for all classes,
*  `interface`&nbsp;for all interfaces,
*  `enum`&nbsp;for all enums,
*  `<<foo1>>`&nbsp;for classes which are stereotyped with&nbsp;_foo1_,
*  an existing class name.



You can use several&nbsp;`show/hide`&nbsp;commands to define rules and exceptions.





``` puml {hide=false}
@startuml

class Dummy1 {
  +myMethods()
}

class Dummy2 {
  +hiddenMethod()
}

class Dummy3 <<Serializable>> {
String name
}

hide members
hide <<Serializable>> circle
show Dummy1 methods
show <<Serializable>> fields

@enduml
```

![](https://s.plantuml.com/imgw/img-311186e1cb2852661fddece831c6f4dd.webp " ")





## Hide classes!





You can also use the&nbsp;`show/hide`&nbsp;commands to hide classes.



This may be useful if you define a large&nbsp;[!included file](https://plantuml.com/en/preprocessing), and if you want to hide come classes after&nbsp;[file inclusion](https://plantuml.com/en/preprocessing).





``` puml {hide=false}
@startuml

class Foo1
class Foo2

Foo2 *-- Foo1

hide Foo2

@enduml
```

![](https://s.plantuml.com/imgw/img-ab306421202e8550ec2bed59f596a63a.webp " ")





## Use generics!





You can also use bracket&nbsp;`<`&nbsp;and&nbsp;`>`&nbsp;to define generics usage in a class.





``` puml {hide=false}
@startuml

class Foo<? extends Element> {
  int size()
}
Foo *- Element

@enduml
```

![](https://s.plantuml.com/imgw/img-e1271d2c136827abe010105d6964820a.webp " ")





It is possible to disable this drawing using&nbsp;`skinparam genericDisplay old`&nbsp;command.



## Specific Spot!



Usually, a spotted character (C, I, E or A) is used for classes, interface, enum and abstract classes.



But you can define your own spot for a class when you define the stereotype, adding a single character and a color, like in this example:





``` puml {hide=false}
@startuml

class System << (S,#FF7700) Singleton >>
class Date << (D,orchid) >>
@enduml
```

![](https://s.plantuml.com/imgw/img-9d4e9a5978e9aa847ffdc79ef7716fe8.webp " ")





## Packages!



You can define a package using the&nbsp;`package`&nbsp;keyword, and optionally declare a background color for your package (Using a html color code or name).



Note that package definitions can be nested.





``` puml {hide=false}
@startuml

package "Classic Collections" #DDDDDD {
  Object <|-- ArrayList
}

package net.sourceforge.plantuml {
  Object <|-- Demo1
  Demo1 *- Demo2
}

@enduml
```

![](https://s.plantuml.com/imgw/img-e1755d9248f6f79212e9b0daea612191.webp " ")





## Packages style!







There are different styles available for packages.



You can specify them either by setting a default style with the command :&nbsp;`skinparam packageStyle`, or by using a stereotype on the package:





``` puml {hide=false}
@startuml
scale 750 width
package foo1 <<Node>> {
  class Class1
}

package foo2 <<Rectangle>> {
  class Class2
}

package foo3 <<Folder>> {
  class Class3
}

package foo4 <<Frame>> {
  class Class4
}

package foo5 <<Cloud>> {
  class Class5
}

package foo6 <<Database>> {
  class Class6
}

@enduml
```

![](https://s.plantuml.com/imgw/img-c3c8574a897cd6dac3c7a7374d640d91.webp " ")







You can also define links between packages, like in the following example:





``` puml {hide=false}
@startuml

skinparam packageStyle rectangle

package foo1.foo2 {
}

package foo1.foo2.foo3 {
  class Object
}

foo1.foo2 +-- foo1.foo2.foo3

@enduml
```

![](https://s.plantuml.com/imgw/img-ee611ddf73072589a7ec8bf87641bca7.webp " ")





## Namespaces!



In packages, the name of a class is the unique identifier of this class. It means that you cannot have two classes with the very same name in different packages.



In that case, you should use&nbsp;[namespaces](http://en.wikipedia.org/wiki/Namespace_%28computer_science%29)&nbsp;instead of packages.



You can refer to classes from other namespaces by fully qualify them. Classes from the default namespace are qualified with a starting dot.



Note that you don't have to explicitly create namespace : a fully qualified class is automatically put in the right namespace.





``` puml {hide=false}
@startuml

class BaseClass

namespace net.dummy #DDDDDD {
    .BaseClass <|-- Person
    Meeting o-- Person

    .BaseClass <|- Meeting
}

namespace net.foo {
  net.dummy.Person  <|- Person
  .BaseClass <|-- Person

  net.dummy.Meeting o-- Person
}

BaseClass <|-- net.unused.Person

@enduml
```

![](https://s.plantuml.com/imgw/img-387825c3c16ba525776f2dbce3f65d87.webp " ")





## Automatic namespace creation!







You can define another separator (other than the dot) using the command :&nbsp;`set namespaceSeparator ???`.





``` puml {hide=false}
@startuml

set namespaceSeparator ::
class X1::X2::foo {
  some info
}

@enduml
```

![](https://s.plantuml.com/imgw/img-9342084355838acd6eaa3a6492d6821a.webp " ")





You can disable automatic package creation using the command&nbsp;`set namespaceSeparator none`.





``` puml {hide=false}
@startuml

set namespaceSeparator none
class X1.X2.foo {
  some info
}

@enduml
```

![](https://s.plantuml.com/imgw/img-0d28f5082d45fede0e56798b902ecf66.webp " ")





## Lollipop interface!





You can also define lollipops interface on classes, using the following syntax:

*  `bar ()- foo`
*  `bar ()-- foo`
*  `foo -() bar`





``` puml {hide=false}
@startuml
class foo
bar ()- foo
@enduml
```

![](https://s.plantuml.com/imgw/img-e461f528ae197feb3fb58cd55a965ed0.webp " ")





## Changing arrows direction!



By default, links between classes have two dashes&nbsp;`--`&nbsp;and are vertically oriented. It is possible to use horizontal link by putting a single dash (or dot) like this:





``` puml {hide=false}
@startuml
Room o- Student
Room *-- Chair
@enduml
```

![](https://s.plantuml.com/imgw/img-d8ef7b33a46692d80deca6af99a09e57.webp " ")





You can also change directions by reversing the link:





``` puml {hide=false}
@startuml
Student -o Room
Chair --* Room
@enduml
```

![](https://s.plantuml.com/imgw/img-06d78bdd0cd55b6ac311432946ad3470.webp " ")





It is also possible to change arrow direction by adding&nbsp;`left`,&nbsp;`right`,&nbsp;`up`&nbsp;or&nbsp;`down`&nbsp;keywords inside the arrow:





``` puml {hide=false}
@startuml
foo -left-> dummyLeft
foo -right-> dummyRight
foo -up-> dummyUp
foo -down-> dummyDown
@enduml
```

![](https://s.plantuml.com/imgw/img-746c8702a07ff53c5d1aabb92c722274.webp " ")





You can shorten the arrow by using only the first character of the direction (for example,&nbsp;`-d-`&nbsp;instead of&nbsp;`-down-`) or the two first characters (`-do-`).



Please note that you should not abuse this functionality :&nbsp;_Graphviz_&nbsp;gives usually good results without tweaking.



## Association classes!



You can define&nbsp;_association class_&nbsp;after that a relation has been defined between two classes, like in this example:



``` puml {hide=false}
@startuml
class Student {
  Name
}
Student "0..*" - "1..*" Course
(Student, Course) .. Enrollment

class Enrollment {
  drop()
  cancel()
}
@enduml
```

![](https://s.plantuml.com/imgw/img-d33cc870a64271c70583d88ad84dda99.webp " ")





You can define it in another direction:





``` puml {hide=false}
@startuml
class Student {
  Name
}
Student "0..*" -- "1..*" Course
(Student, Course) . Enrollment

class Enrollment {
  drop()
  cancel()
}
@enduml
```

![](https://s.plantuml.com/imgw/img-9f49aa75c28d92ebf3174920a4150254.webp " ")





## Skinparam!







You can use the&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;command to change colors and fonts for the drawing.



You can use this command :

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in the&nbsp;[command line](https://plantuml.com/en/command-line)&nbsp;or the&nbsp;[ANT task](https://plantuml.com/en/ant-task).





``` puml {hide=false}
@startuml

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

![](https://s.plantuml.com/imgw/img-d729b5fa89052b4fb4e7a697108cb00c.webp " ")





## Skinned Stereotypes!





You can define specific color and fonts for stereotyped classes.





``` puml {hide=false}
@startuml

skinparam class {
BackgroundColor PaleGreen
ArrowColor SeaGreen
BorderColor SpringGreen
BackgroundColor<<Foo>> Wheat
BorderColor<<Foo>> Tomato
}
skinparam stereotypeCBackgroundColor YellowGreen
skinparam stereotypeCBackgroundColor<< Foo >> DimGray

Class01 <<Foo>>
Class03 <<Foo>>
Class01 "1" *-- "many" Class02 : contains

Class03 o-- Class04 : aggregation

@enduml
```

![](https://s.plantuml.com/imgw/img-80c8e717a3535d2a8609d4fc37f6b3a0.webp " ")





## Color gradient!





It's possible to declare individual color for classes or note using the # notation.



You can use either&nbsp;[standard color name](https://plantuml.com/en/color)&nbsp;or RGB code.



You can also use color gradient in background, with the following syntax: two colors names separated either by:

*  `|`,
*  `/`,
*  `\`,
*  or&nbsp;`-`

depending the direction of the gradient.



For example, you could have:





``` puml {hide=false}
@startuml

skinparam backgroundcolor AntiqueWhite/Gold
skinparam classBackgroundColor Wheat|CornflowerBlue

class Foo #red-green
note left of Foo #blue\9932CC
  this is my
  note on this class
end note

package example #GreenYellow/LightGoldenRodYellow {
  class Dummy
}

@enduml
```

![](https://s.plantuml.com/imgw/img-736e7e3f3e79b7381951e00556a1bae6.webp " ")





## Help on layout!





Sometimes, the default layout is not perfect...



You can use&nbsp;`together`&nbsp;keyword to group some classes together : the layout engine will try to group them (as if they were in the same package).



You can also use&nbsp;`hidden`&nbsp;links to force the layout.



``` puml {hide=false}
@startuml

class Bar1
class Bar2
together {
  class Together1
  class Together2
  class Together3
}
Together1 - Together2
Together2 - Together3
Together2 -[hidden]--> Bar1
Bar1 -[hidden]> Bar2


@enduml
```

![](https://s.plantuml.com/imgw/img-745f3bf1eaf524b0d2545e971157db0e.webp " ")









## Splitting large files!



Sometimes, you will get some very large image files.



You can use the&nbsp;`page (hpages)x(vpages)`&nbsp;command to split the generated image into several files :



`hpages`&nbsp;is a number that indicated the number of horizontal pages, and&nbsp;`vpages`&nbsp;is a number that indicated the number of vertical pages.



You can also use some specific skinparam settings to put borders on splitted pages (see example).





``` puml {hide=false}
@startuml
' Split into 4 pages
page 2x2
skinparam pageMargin 10
skinparam pageExternalColor gray
skinparam pageBorderColor black

class BaseClass

namespace net.dummy #DDDDDD {
    .BaseClass <|-- Person
    Meeting o-- Person

    .BaseClass <|- Meeting

}

namespace net.foo {
  net.dummy.Person  <|- Person
  .BaseClass <|-- Person

  net.dummy.Meeting o-- Person
}

BaseClass <|-- net.unused.Person
@enduml
```

![](https://s.plantuml.com/imgw/img-00e163f05d3fdd1d2a6ff064b266c68d.webp " ")







## Extends and implements!



It is also possible to use&nbsp;`extends`&nbsp;and&nbsp;`implements`&nbsp;keywords.



``` puml {hide=false}
@startuml
class ArrayList implements List
class ArrayList extends AbstractList
@enduml
```