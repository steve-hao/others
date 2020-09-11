# State Diagram

[State diagrams](https://en.wikipedia.org/wiki/State_diagram)&nbsp;are used to give an abstract description of the behavior of a system. This behavior is represented as a series of events that can occur in one or more possible states.



## Simple State!

You can use&nbsp;`[*]`&nbsp;for the starting point and ending point of the state diagram.



Use&nbsp;`-->`&nbsp;for arrows.





``` puml {hide=false}
@startuml

[*] --> State1
State1 --> [*]
State1 : this is a string
State1 : this is another string

State1 -> State2
State2 --> [*]

@enduml
```

![](https://s.plantuml.com/imgw/img-8a17c5b01aa7a73b2f241c9b46af1ca9.webp " ")





## Change state rendering!



You can use&nbsp;`hide empty description`&nbsp;to render state as simple box.





``` puml {hide=false}
@startuml
hide empty description
[*] --> State1
State1 --> [*]
State1 : this is a string
State1 : this is another string

State1 -> State2
State2 --> [*]
@enduml
```

![](https://s.plantuml.com/imgw/img-905b934bba13511c7d0172830789b140.webp " ")





## Composite state!





A state can also be composite. You have to define it using the&nbsp;`state`&nbsp;keywords and brackets.





``` puml {hide=false}
@startuml
scale 350 width
[*] --> NotShooting

state NotShooting {
  [*] --> Idle
  Idle --> Configuring : EvConfig
  Configuring --> Idle : EvConfig
}

state Configuring {
  [*] --> NewValueSelection
  NewValueSelection --> NewValuePreview : EvNewValue
  NewValuePreview --> NewValueSelection : EvNewValueRejected
  NewValuePreview --> NewValueSelection : EvNewValueSaved

  state NewValuePreview {
     State1 -> State2
  }

}
@enduml
```

![](https://s.plantuml.com/imgw/img-b02475ff56873044ec56bb47e36f880a.webp " ")



## Long name!





You can also use the&nbsp;`state`&nbsp;keyword to use long description for states.





``` puml {hide=false}
@startuml
scale 600 width

[*] -> State1
State1 --> State2 : Succeeded
State1 --> [*] : Aborted
State2 --> State3 : Succeeded
State2 --> [*] : Aborted
state State3 {
  state "Accumulate Enough Data\nLong State Name" as long1
  long1 : Just a test
  [*] --> long1
  long1 --> long1 : New Data
  long1 --> ProcessData : Enough Data
}
State3 --> State3 : Failed
State3 --> [*] : Succeeded / Save Result
State3 --> [*] : Aborted

@enduml
```

![](https://s.plantuml.com/imgw/img-82d36e45121c0b70854bb98f2aefc4ec.webp " ")



## History!



You can use [H] for the history and [H*] for the deep history of a substate





``` puml {hide=false}
@startuml
[*] -> State1
State1 --> State2 : Succeeded
State1 --> [*] : Aborted
State2 --> State3 : Succeeded
State2 --> [*] : Aborted
state State3 {
  state "Accumulate Enough Data" as long1
  long1 : Just a test
  [*] --> long1
  long1 --> long1 : New Data
  long1 --> ProcessData : Enough Data
  State2 --> [H]: Resume
}
State3 --> State2 : Pause
State2 --> State3[H*]: DeepResume
State3 --> State3 : Failed
State3 --> [*] : Succeeded / Save Result
State3 --> [*] : Aborted
@enduml
```

![](https://s.plantuml.com/imgw/img-c6994b79f791e0db1aa6471c95ea4b1e.webp " ")



## Fork!





You can also fork and join using the&nbsp;`<<fork>>`&nbsp;and&nbsp;`<<join>>`&nbsp;stereotypes.







``` puml {hide=false}
@startuml

state fork_state <<fork>>
[*] --> fork_state
fork_state --> State2
fork_state --> State3

state join_state <<join>>
State2 --> join_state
State3 --> join_state
join_state --> State4
State4 --> [*]

@enduml
```

![](https://s.plantuml.com/imgw/img-309beb61e946396a274e509100a2f30e.webp " ")





## Concurrent state!





You can define concurrent state into a composite state using either&nbsp;`--`&nbsp;or&nbsp;`||`&nbsp;symbol as separator.



``` puml {hide=false}
@startuml
[*] --> Active

state Active {
  [*] -> NumLockOff
  NumLockOff --> NumLockOn : EvNumLockPressed
  NumLockOn --> NumLockOff : EvNumLockPressed
  --
  [*] -> CapsLockOff
  CapsLockOff --> CapsLockOn : EvCapsLockPressed
  CapsLockOn --> CapsLockOff : EvCapsLockPressed
  --
  [*] -> ScrollLockOff
  ScrollLockOff --> ScrollLockOn : EvCapsLockPressed
  ScrollLockOn --> ScrollLockOff : EvCapsLockPressed
}

@enduml
```

![](https://s.plantuml.com/imgw/img-5961cad95e91cfa1e53afa053e0b4361.webp " ")





## Conditional!



The stereotype&nbsp;`<<choice>>`&nbsp;can be used to use conditional state.





``` puml {hide=false}
@startuml
state "Req(Id)" as ReqId <<sdlreceive>>
state "Minor(Id)" as MinorId
state "Major(Id)" as MajorId
 
state c <<choice>>
 
Idle --> ReqId
ReqId --> c
c --> MinorId : [Id <= 10]
c --> MajorId : [Id > 10]
@enduml
```

![](https://s.plantuml.com/imgw/img-84fcba68b3502bc65dc09b256b6b3a93.webp " ")



## Arrow direction!



You can use&nbsp;`->`&nbsp;for horizontal arrows. It is possible to force arrow's direction using the following syntax:

*  `-down->`&nbsp;(default arrow)
*  `-right->`&nbsp;or&nbsp;`->`
*  `-left->`
*  `-up->`





``` puml {hide=false}
@startuml

[*] -up-> First
First -right-> Second
Second --> Third
Third -left-> Last

@enduml
```

![](https://s.plantuml.com/imgw/img-802bab12672a31322de3195db8905a48.webp " ")

You can shorten the arrow by using only the first character of the direction (for example,&nbsp;`-d-`&nbsp;instead of&nbsp;`-down-`) or the two first characters (`-do-`).



Please note that you should not abuse this functionality :&nbsp;_Graphviz_&nbsp;gives usually good results without tweaking.



## Note!



You can also define notes using&nbsp;`note left of`,&nbsp;`note right of`,&nbsp;`note top of`,&nbsp;`note bottom of`&nbsp;keywords.



You can also define notes on several lines.



``` puml {hide=false}
@startuml

[*] --> Active
Active --> Inactive

note left of Active : this is a short\nnote

note right of Inactive
  A note can also
  be defined on
  several lines
end note

@enduml
```

![](https://s.plantuml.com/imgw/img-3b33c87aee6e0f8f3e0d890d65dccf2c.webp " ")







You can also have floating notes.



``` puml {hide=false}
@startuml

state foo
note "This is a floating note" as N1

@enduml
```

![](https://s.plantuml.com/imgw/img-503dcc04a447e27e239a5e9de10da21c.webp " ")





## Note on link!



You can put notes on state-transition or link, with&nbsp;`note on link`&nbsp;keyword.





``` puml {hide=false}
@startuml
[*] -> State1
State1 --> State2
note on link 
  this is a state-transition note 
end note
@enduml
```

![](https://s.plantuml.com/imgw/img-421e5b425a5670ce5a53b0285a2b232a.webp " ")



## More in notes!





You can put notes on composite states.



``` puml {hide=false}
@startuml

[*] --> NotShooting

state "Not Shooting State" as NotShooting {
  state "Idle mode" as Idle
  state "Configuring mode" as Configuring
  [*] --> Idle
  Idle --> Configuring : EvConfig
  Configuring --> Idle : EvConfig
}

note right of NotShooting : This is a note on a composite state

@enduml
```

![](https://s.plantuml.com/imgw/img-60f9c87808c06d6590c55cf527b5d37a.webp " ")





## Skinparam!





You can use the&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;command to change colors and fonts for the drawing.



You can use this command :

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in the&nbsp;[command line](https://plantuml.com/en/command-line)&nbsp;or the&nbsp;[ANT task](https://plantuml.com/en/ant-task).

You can define specific color and fonts for stereotyped states.





``` puml {hide=false}
@startuml
skinparam backgroundColor LightYellow
skinparam state {
  StartColor MediumBlue
  EndColor Red
  BackgroundColor Peru
  BackgroundColor<<Warning>> Olive
  BorderColor Gray
  FontName Impact
}

[*] --> NotShooting

state "Not Shooting State" as NotShooting {
  state "Idle mode" as Idle <<Warning>>
  state "Configuring mode" as Configuring
  [*] --> Idle
  Idle --> Configuring : EvConfig
  Configuring --> Idle : EvConfig
}

NotShooting --> [*]
@enduml
```

![](https://s.plantuml.com/imgw/img-0df4575fcfd96c54b87b7c54f6a574f8.webp " ")