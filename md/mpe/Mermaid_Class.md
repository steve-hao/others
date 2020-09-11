# [Class diagrams](http://mermaid-js.github.io/mermaid/#/classDiagram?id=class-diagrams)

> "In software engineering, a class diagram in the Unified Modeling Language (UML) is a type of static structure diagram that describes the structure of a system by showing the system's classes, their attributes, operations (or methods), and the relationships among objects." Wikipedia

The class diagram is the main building block of object-oriented modeling. It is used for general conceptual modeling of the structure of the application, and for detailed modeling translating the models into programming code. Class diagrams can also be used for data modeling. The classes in a class diagram represent both the main elements, interactions in the application, and the classes to be programmed.

Mermaid can render class diagrams.

``` Mermaid {hide=false}
classDiagram
      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }
```



## [Syntax](http://mermaid-js.github.io/mermaid/#/classDiagram?id=syntax)

### [Class](http://mermaid-js.github.io/mermaid/#/classDiagram?id=class)

UML provides mechanisms to represent class members, such as attributes and methods, and additional information about them. A single instance of a class in the diagram contains three compartments:

*  The top compartment contains the name of the class. It is printed in bold and centered, and the first letter is capitalized. It may also contain optional annotation text describing the nature of the class.
*  The middle compartment contains the attributes of the class. They are left-aligned and the first letter is lowercase.
*  The bottom compartment contains the operations the class can execute. They are also left-aligned and the first letter is lowercase.

``` Mermaid {hide=false}
classDiagram
    class BankAccount
    BankAccount : +String owner
    BankAccount : +Bigdecimal balance
    BankAccount : +deposit(amount)
    BankAccount : +withdrawl(amount)
```



## [Define a class](http://mermaid-js.github.io/mermaid/#/classDiagram?id=define-a-class)

There are two ways to define a class:

*  Explicitly defining a class using keyword&nbsp;**class**&nbsp;like&nbsp;`class Animal`. This defines the Animal class
*  Define two classes via a&nbsp;**relationship**&nbsp;between them&nbsp;`Vehicle <|-- Car`. This defines two classes Vehicle and Car along with their relationship.

``` Mermaid {hide=false}
classDiagram
    class Animal
    Vehicle <|-- Car
```



Naming convention: a class name should be composed of alphanumeric (unicode allowed) and underscore characters.

## [Defining Members of a class](http://mermaid-js.github.io/mermaid/#/classDiagram?id=defining-members-of-a-class)

UML provides mechanisms to represent class members, such as attributes and methods, and additional information about them.

Mermaid distinguishes between attributes and functions/methods based on if the&nbsp;**parenthesis**&nbsp;`()`&nbsp;are present or not. The ones with&nbsp;`()`&nbsp;are treated as functions/methods, and others as attributes.

There are two ways to define the members of a class, and regardless of whichever syntax is used to define the members, the output will still be same. The two different ways are :

*  Associate a member of a class using&nbsp;**:**&nbsp;(colon) followed by member name, useful to define one member at a time. For example:
    
    ``` Mermaid {hide=false}
    classDiagram
      class BankAccount
      BankAccount : +String owner
      BankAccount : +BigDecimal balance
      BankAccount : +deposit(amount)
      BankAccount : +withdrawal(amount)
    ```
*  Associate members of a class using&nbsp;**{}**&nbsp;brackets, where members are grouped within curly brackets. Suitable for defining multiple members at once. For example:
    
    ``` Mermaid {hide=false}
    classDiagram
      class BankAccount{
      +String owner
      +BigDecimal balance
      +deposit(amount) bool
      +withdrawl(amount)
    }
    ```

#### [Return Type](http://mermaid-js.github.io/mermaid/#/classDiagram?id=return-type)

Optionally you can end the method/function definition with the data type that will be returned (note: there must be a space between the final&nbsp;`)`&nbsp;of the method definition and return type example:

``` Mermaid {hide=false}
classDiagram
  class BankAccount{
    +String owner
    +BigDecimal balance
    +deposit(amount) bool
    +withdrawl(amount) int
}
```



#### [Generic Types](http://mermaid-js.github.io/mermaid/#/classDiagram?id=generic-types)

Members can be defined using generic types, such as&nbsp;`List<int>`, for fields, parameters and return types by enclosing the type within&nbsp;`~`&nbsp;(**tilde**). Note:&nbsp;**nested**&nbsp;type declarations (such as&nbsp;`List<List<int>>`) are not currently supported

This can be done as part of either class definition method:

``` Mermaid {hide=false}
classDiagram
class Square~Shape~{
    int id
    List~int~ position
    setPoints(List~int~ points)
    getPoints() List~int~
}

Square : -List~string~ messages
Square : +setMessages(List~string~ messages)
Square : +getMessages() List~string~
```



#### [Return Type](http://mermaid-js.github.io/mermaid/#/classDiagram?id=return-type-1)

Optionally you can end the method/function definition with the data type that will be returned

#### [Visibility](http://mermaid-js.github.io/mermaid/#/classDiagram?id=visibility)

To specify the visibility of a class member (i.e. any attribute or method), these notations may be placed before the member's name, but it is optional:

*  `+`&nbsp;Public
*  `-`&nbsp;Private
*  `#`&nbsp;Protected
*  `~`&nbsp;Package/Internal

> _note_&nbsp;you can also include additional&nbsp;_classifers_&nbsp;to a method definition by adding the following notations to the end of the method, i.e.: after the&nbsp;`()`:
> 
> *  `*`&nbsp;Abstract e.g.:&nbsp;`someAbstractMethod()*`
> *  `$`&nbsp;Static e.g.:&nbsp;`someStaticMethod()$`

## [Defining Relationship](http://mermaid-js.github.io/mermaid/#/classDiagram?id=defining-relationship)

A relationship is a general term covering the specific types of logical connections found on class and object diagrams.

``` 
[classA][Arrow][ClassB]:LabelText
```

There are different types of relations defined for classes under UML which are currently supported:

| Type | Description |
|------|-------------|
| &lt;\|-- | Inheritance |
| *-- | Composition |
| o-- | Aggregation |
| --&gt; | Association |
| -- | Link (Solid) |
| ..&gt; | Dependency |
| ..\|&gt; | Realization |
| .. | Link (Dashed) |

``` Mermaid {hide=false}
classDiagram
classA <|-- classB
classC *-- classD
classE o-- classF
classG <-- classH
classI -- classJ
classK <.. classL
classM <|.. classN
classO .. classP
```



We can use the labels to describe nature of relation between two classes. Also, arrowheads can be used in opposite directions as well :

``` Mermaid {hide=false}
classDiagram
classA --|> classB : Inheritance
classC --* classD : Composition
classE --o classF : Aggregation
classG --> classH : Association
classI -- classJ : Link(Solid)
classK ..> classL : Dependency
classM ..|> classN : Realization
classO .. classP : Link(Dashed)
```



## [Labels on Relations](http://mermaid-js.github.io/mermaid/#/classDiagram?id=labels-on-relations)

It is possible to add a label text to a relation:

``` 
[classA][Arrow][ClassB]:LabelText
```

``` Mermaid {hide=false}
classDiagram
classA <|-- classB : implements
classC *-- classD : composition
classE o-- classF : association
```



## [Cardinality / Multiplicity on relations](http://mermaid-js.github.io/mermaid/#/classDiagram?id=cardinality-multiplicity-on-relations)

Multiplicity or cardinality in class diagrams indicates the number of instances of one class linked to one instance of the other class. For example, one company will have one or more employees, but each employee works for just one company.

Multiplicity notations are placed near the ends of an association.

The different cardinality options are :

*  `0..1`&nbsp;Zero or one
*  `1`&nbsp;Only 1
*  `0..1`&nbsp;Zero or One
*  `1..*`&nbsp;One or more
*  `*`&nbsp;Many
*  `n`&nbsp;n {where n&gt;1}
*  `0..n`&nbsp;zero to n {where n&gt;1}
*  `1..n`&nbsp;one to n {where n&gt;1}

Cardinality can be easily defined by placing cardinality text within qoutes&nbsp;`"`&nbsp;before(optional) and after(optional) a given arrow.

``` 
[classA] "cardinality1" [Arrow] "cardinality2" [ClassB]:LabelText
```

``` Mermaid {hide=false}
classDiagram
    Customer "1" --> "*" Ticket
    Student "1" --> "1..*" Course
    Galaxy --> "many" Star : Contains
```



## [Annotations on classes](http://mermaid-js.github.io/mermaid/#/classDiagram?id=annotations-on-classes)

It is possible to annotate classes with a specific marker text which is like meta-data for the class, giving a clear indication about its nature. Some common annotations examples could be:

*  `<<Interface>>`&nbsp;To represent an Interface class
*  `<<abstract>>`&nbsp;To represent an abstract class
*  `<<Service>>`&nbsp;To represent a service class
*  `<<enumeration>>`&nbsp;To represent an enum

Annotations are defined within the opening&nbsp;`<<`&nbsp;and closing&nbsp;`>>`. There are two ways to add an annotation to a class and regardless of the syntax used output will be same. The two ways are :

*  In a&nbsp;**_separate line_**&nbsp;after a class is defined. For example:
    
    ``` Mermaid {hide=false}
    classDiagram
    class Shape
    <<interface>> Shape
    ```



*  In a&nbsp;**_nested structure_**&nbsp;along with class definition. For example:

``` Mermaid {hide=false}
classDiagram
class Shape{
    <<interface>>
    noOfVertices
    draw()
}
class Color{
    <<enumeration>>
    RED
    BLUE
    GREEN
    WHITE
    BLACK
}
```



## [Comments](http://mermaid-js.github.io/mermaid/#/classDiagram?id=comments)

Comments can be entered within a class diagram, which will be ignored by the parser. Comments need to be on their own line, and must be prefaced with&nbsp;`%%`&nbsp;(double percent signs). Any text after the start of the comment to the next newline will be treated as a comment, including any class diagram syntax

``` Mermaid {hide=false}
classDiagram
%% This whole line is a comment classDiagram class Shape <<interface>>
class Shape{
    <<interface>>
    noOfVertices
    draw()
}
```

## [Interaction](http://mermaid-js.github.io/mermaid/#/classDiagram?id=interaction)

It is possible to bind a click event to a node, the click can lead to either a javascript callback or to a link which will be opened in a new browser tab.&nbsp;**Note**: This functionality is disabled when using&nbsp;`securityLevel='strict'`&nbsp;and enabled when using&nbsp;`securityLevel='loose'`.

You would define these actions on a separate line after all classes have been declared.

``` 
action className "reference" "tooltip"
```

*  _action_&nbsp;is either&nbsp;`link`&nbsp;or&nbsp;`callback`, depending on which type of interaction you want to have called
*  _className_&nbsp;is the id of the node that the action will be associated with
*  _reference_&nbsp;is either the url link, or the function name for callback. (note: callback function will be called with the nodeId as parameter).
*  (_optional_) tooltip is a string to be displayed when hovering over element (note: The styles of the tooltip are set by the class .mermaidTooltip.)

### [Examples:](http://mermaid-js.github.io/mermaid/#/classDiagram?id=examples)

_URL Link:_

``` Mermaid {hide=false}
classDiagram
class Shape
link Shape "http://www.github.com" "This is a tooltip for a link"
```

_Callback:_

``` Mermaid {hide=false}
classDiagram
class Shape
callback Shape "callbackFunction" "This is a tooltip for a callback"
```

``` 
<script>
    var callbackFunction = function(){
        alert('A callback was triggered');
    }
<script>
```



> **Success**&nbsp;The tooltip functionality and the ability to link to urls are available from version 0.5.2.

Beginners tip, a full example using interactive links in an html context:

``` 
<body>
  <div class="mermaid">
    classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
      +String beakColor
      +swim()
      +quack()
      }
    class Fish{
      -int sizeInFeet
      -canEat()
      }
    class Zebra{
      +bool is_wild
      +run()
      }

        callback Duck callback "Tooltip"
        click Zebra "http://www.github.com" "This is a link"
  </div>

  <script>
      var callback = function(){
        alert('A callback was triggered');
    }
    var config = {
      startOnLoad:true,
      securityLevel:'loose',
    };

    mermaid.initialize(config);
  </script>
</body>
```

## [Styling](http://mermaid-js.github.io/mermaid/#/classDiagram?id=styling)

Styling of the class diagram is done by defining a number of css classes. During rendering these classes are extracted from the file located at src/themes/class.scss

### [Styling Classes used](http://mermaid-js.github.io/mermaid/#/classDiagram?id=styling-classes-used)

| Class | Description |
|-------|-------------|
| g.classGroup text | Styles for general class text |
| classGroup .title | Styles for general class title |
| g.classGroup rect | Styles for class diagram rectangle |
| g.classGroup line | Styles for class diagram line |
| .classLabel .box | Styles for class label box |
| .classLabel .label | Styles for class label text |
| composition | Styles for componsition arrow head and arrow line |
| aggregation | Styles for aggregation arrow head and arrow line(dashed or solid) |
| dependency | Styles for dependency arrow head and arrow line |

### [Sample stylesheet](http://mermaid-js.github.io/mermaid/#/classDiagram?id=sample-stylesheet)

``` 
body {
    background: white;
}

g.classGroup text {
  fill: $nodeBorder;
  stroke: none;
  font-family: 'trebuchet ms', verdana, arial;
  font-family: var(--mermaid-font-family);
  font-size: 10px;

  .title {
    font-weight: bolder;
  }
}

g.classGroup rect {
  fill: $nodeBkg;
  stroke: $nodeBorder;
}

g.classGroup line {
  stroke: $nodeBorder;
  stroke-width: 1;
}

.classLabel .box {
  stroke: none;
  stroke-width: 0;
  fill: $nodeBkg;
  opacity: 0.5;
}

.classLabel .label {
  fill: $nodeBorder;
  font-size: 10px;
}

.relation {
  stroke: $nodeBorder;
  stroke-width: 1;
  fill: none;
}

@mixin composition {
  fill: $nodeBorder;
  stroke: $nodeBorder;
  stroke-width: 1;
}

#compositionStart {
  @include composition;
}

#compositionEnd {
  @include composition;
}

@mixin aggregation {
  fill: $nodeBkg;
  stroke: $nodeBorder;
  stroke-width: 1;
}

#aggregationStart {
  @include aggregation;
}

#aggregationEnd {
  @include aggregation;
}

#dependencyStart {
  @include composition;
}

#dependencyEnd {
  @include composition;
}

#extensionStart {
  @include composition;
}

#extensionEnd {
  @include composition;
}
```

## [Configuration](http://mermaid-js.github.io/mermaid/#/classDiagram?id=configuration)

`Coming soon`<scrpt src="//unpkg.com/docsify/lib/plugins/ga.min.js" style='-webkit-font-smoothing: antialiased; -webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-size-adjust: none; box-sizing: border-box; color: rgb(52, 73, 94); font-family: "Source Sans Pro", "Helvetica Neue", Arial, sans-serif; font-size: 15px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; white-space: normal; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; text-decoration-style: initial; text-decoration-color: initial;'></scrpt>