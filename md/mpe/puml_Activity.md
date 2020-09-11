# Activity Diagram

## Simple Action!



You can use&nbsp;`(*)`&nbsp;for the starting point and ending point of the activity diagram.



In some occasion, you may want to use&nbsp;`(*top)`&nbsp;to force the starting point to be at the top of the diagram.





Use&nbsp;`-->`&nbsp;for arrows.





``` puml {hide=false}
@startuml

(*) --> "First Action"
"First Action" --> (*)

@enduml
```

![](https://s.plantuml.com/imgw/img-d55ad6874afb6ec1ab916840c66bcdc3.webp " ")



## Label on arrows!







By default, an arrow starts at the last used activity.



You can put a label on an arrow using brackets&nbsp;`[`&nbsp;and&nbsp;`]`&nbsp;just after the arrow definition.



``` puml {hide=false}
@startuml

(*) --> "First Action"
-->[You can put also labels] "Second Action"
--> (*)

@enduml
```

![](https://s.plantuml.com/imgw/img-eb56b7c043c5760e6b98cfd8537c4097.webp " ")



## Changing arrow direction!





You can use&nbsp;`->`&nbsp;for horizontal arrows. It is possible to force arrow's direction using the following syntax:

*  `-down->`&nbsp;(default arrow)
*  `-right->`&nbsp;or&nbsp;`->`
*  `-left->`
*  `-up->`





``` puml {hide=false}
@startuml

(*) -up-> "First Action"
-right-> "Second Action"
--> "Third Action"
-left-> (*)

@enduml
```

![](https://s.plantuml.com/imgw/img-485e6442b49e18e57381717bc82b145e.webp " ")



## Branches!





You can use&nbsp;`if/then/else`&nbsp;keywords to define branches.





``` puml {hide=false}
@startuml
(*) --> "Initialization"

if "Some Test" then
  -->[true] "Some Action"
  --> "Another Action"
  -right-> (*)
else
  ->[false] "Something else"
  -->[Ending process] (*)
endif

@enduml
```

![](https://s.plantuml.com/imgw/img-33b1a166d0e9b68cbdb910c08ba18ffe.webp " ")





Unfortunately, you will have to sometimes repeat the same activity in the diagram text:



``` puml {hide=false}
@startuml
(*)  --> "check input"
If "input is verbose" then
--> [Yes] "turn on verbosity"
--> "run command"
else
--> "run command"
Endif
-->(*)
@enduml
```

![](https://s.plantuml.com/imgw/img-7b1e8489f29ef78b8e60ba741dc2a327.webp " ")



## More on Branches!





By default, a branch is connected to the last defined activity, but it is possible to override this and to define a link with the&nbsp;`if`&nbsp;keywords.



It is also possible to nest branches.





``` puml {hide=false}
@startuml

(*) --> if "Some Test" then

  -->[true] "action 1"

  if "" then
    -> "action 3" as a3
  else
    if "Other test" then
      -left-> "action 5"
    else
      --> "action 6"
    endif
  endif

else

  ->[false] "action 2"

endif

a3 --> if "last test" then
  --> "action 7"
else
  -> "action 8"
endif

@enduml
```

![](https://s.plantuml.com/imgw/img-fdb9305712b772379315d749e4389986.webp " ")



## Synchronization!



You can use&nbsp;`=== code ===`&nbsp;to display synchronization bars.





``` puml {hide=false}
@startuml

(*) --> ===B1===
--> "Parallel Action 1"
--> ===B2===

===B1=== --> "Parallel Action 2"
--> ===B2===

--> (*)

@enduml
```

![](https://s.plantuml.com/imgw/img-866eb00393d869f5c2530807cca1ec5a.webp " ")



## Long action description!





When you declare activities, you can span on several lines the description text. You can also add&nbsp;`\n`&nbsp;in the description.



You can also give a short code to the activity with the&nbsp;`as`&nbsp;keyword. This code can be used latter in the diagram description.





``` puml {hide=false}
@startuml
(*) -left-> "this <size:20>action</size>
is <b>very</b> <color:red>long2</color>
and defined on several lines
that contains many <i>text</i>" as A1

-up-> "Another action\n on several lines"

A1 --> "Short action <img:sourceforge.jpg>"
@enduml
```

![](https://s.plantuml.com/imgw/img-7b7cc738b6fdc6a069fc1e39f91e2f79.webp " ")



## Notes!





You can add notes on a activity using the commands&nbsp;`note left`,&nbsp;`note right`,&nbsp;`note top`&nbsp;or&nbsp;`note bottom`, just after the description of the activity you want to note.



If you want to put a note on the starting point, define the note at the very beginning of the diagram description.



You can also have a note on several lines, using the&nbsp;`endnote`&nbsp;keywords.



``` puml {hide=false}
@startuml

(*) --> "Some action"
note right: This action has to be defined
"Some action" --> (*)
note left
 This note is on
 several lines
end note

@enduml
```

![](https://s.plantuml.com/imgw/img-2325da1e7ea11ec2033311c953afc278.webp " ")



## Partition!



You can define a partition using the&nbsp;`partition`&nbsp;keyword, and optionally declare a background color for your partition (Using a html color code or name)



When you declare activities, they are automatically put in the last used partition.



You can close the partition definition using a closing bracket&nbsp;`}`.



``` puml {hide=false}
@startuml

partition Conductor {
  (*) --> "Climbs on Platform"
  --> === S1 ===
  --> Bows
}

partition Audience #LightSkyBlue {
  === S1 === --> Applauds
}

partition Conductor {
  Bows --> === S2 ===
  --> WavesArmes
  Applauds --> === S2 ===
}

partition Orchestra #CCCCEE {
  WavesArmes --> Introduction
  --> "Play music"
}

@enduml
```

![](https://s.plantuml.com/imgw/img-037f23c510157ea44feb7a53d3350635.webp " ")





## Skinparam!





You can use the&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;command to change colors and fonts for the drawing.



You can use this command :

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in the&nbsp;[command line](https://plantuml.com/en/command-line)&nbsp;or the&nbsp;[ANT task](https://plantuml.com/en/ant-task).

You can define specific color and fonts for stereotyped activities.





``` puml {hide=false}
@startuml

skinparam backgroundColor #AAFFFF
skinparam activity {
  StartColor red
  BarColor SaddleBrown
  EndColor Silver
  BackgroundColor Peru
  BackgroundColor<< Begin >> Olive
  BorderColor Peru
  FontName Impact
}

(*) --> "Climbs on Platform" << Begin >>
--> === S1 ===
--> Bows
--> === S2 ===
--> WavesArmes
--> (*)

@enduml
```

![](https://s.plantuml.com/imgw/img-b1c1edf605e2d3da62511920e2c139fa.webp " ")





## Octagon!



You can change the shape of activities to octagon using the&nbsp;`skinparam activityShape octagon`&nbsp;command.



``` puml {hide=false}
@startuml
'Default is skinparam activityShape roundBox
skinparam activityShape octagon

(*) --> "First Action"
"First Action" --> (*)

@enduml
```

![](https://s.plantuml.com/imgw/img-e0e26d1909804f35fedc80cb42079f7b.webp " ")



## Complete example!







``` puml {hide=false}
@startuml
title Servlet Container

(*) --> "ClickServlet.handleRequest()"
--> "new Page"

if "Page.onSecurityCheck" then
  ->[true] "Page.onInit()"

  if "isForward?" then
   ->[no] "Process controls"

   if "continue processing?" then
     -->[yes] ===RENDERING===
   else
     -->[no] ===REDIRECT_CHECK===
   endif

  else
   -->[yes] ===RENDERING===
  endif

  if "is Post?" then
    -->[yes] "Page.onPost()"
    --> "Page.onRender()" as render
    --> ===REDIRECT_CHECK===
  else
    -->[no] "Page.onGet()"
    --> render
  endif

else
  -->[false] ===REDIRECT_CHECK===
endif

if "Do redirect?" then
 ->[yes] "redirect request"
 --> ==BEFORE_DESTROY===
else
 if "Do Forward?" then
  -left->[yes] "Forward request"
  --> ==BEFORE_DESTROY===
 else
  -right->[no] "Render page template"
  --> ==BEFORE_DESTROY===
 endif
endif

--> "Page.onDestroy()"
-->(*)

@enduml
```

![](https://s.plantuml.com/imgw/img-9a0fa7d61eb27ac1d1d1c82c139abcf1.webp " ")