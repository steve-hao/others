# [Diagrams that mermaid can render:](https://mermaid-js.github.io/mermaid/#/README?id=diagrams-that-mermaid-can-render)

### [Flowchart](Mermaid_Flowchart.md)

``` Mermaid {hide=false}
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```


### [Sequence diagram](Mermaid_Sequence.md)

```  Mermaid {hide=false}
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```
### [Class diagram ](Mermaid_Class.md)


```   Mermaid {hide=false}
classDiagram
Class01 <|-- AveryLongClass : Cool
Class03 *-- Class04
Class05 o-- Class06
Class07 .. Class08
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
Class08 <--> C2: Cool label
```

### [State diagrams](Mermaid_State.md)

``` Mermaid {hide=false}
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

### [Entity Relationship Diagram ](Mermaid_Entity.md)

```  Mermaid {hide=false}
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

### [User Journey Diagram](Mermaid_Journey.md)

```  Mermaid {hide=false}
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```


### [Gantt diagram](Mermaid_Gantt.md)

```   Mermaid {hide=false}
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram to mermaid
excludes weekdays 2014-01-10

section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2               :         des4, after des3, 5d
```

### [Pie chart diagrams](Mermaid_Pie.md)

``` Mermaid {hide=false}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```

### [Git graph ](https://mermaid-js.github.io/mermaid/#/README?id=git-graph-exclamation-experimental)

``` 
gitGraph:
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```

![Git graph](https://mermaid-js.github.io/mermaid/img/git.png " ")

### [Directives](Mermaid_Directives.md)