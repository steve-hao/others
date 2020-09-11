# Activity Diagram (beta)

Current&nbsp;[syntax for activity diagram](https://plantuml.com/en/activity-diagram-legacy)&nbsp;has several limitations and drawbacks (for example, it's difficult to maintain).



So a completely new syntax and implementation is proposed as&nbsp;**beta version**&nbsp;to users (starting with V7947), so that we could define a better format and syntax.



Another advantage of this new implementation is that it's done without the need of having Graphviz installed (as for sequence diagrams).



The new syntax will replace the old one. However, for compatibility reason, the old syntax will still be recognized, to ensure&nbsp;_ascending compatibility_.



Users are simply encouraged to migrate to the new syntax.


## Simple action!

Activities label starts with&nbsp;`:`&nbsp;and ends with&nbsp;`;`.



Text formatting can be done using&nbsp;[creole wiki syntax](https://plantuml.com/en/creole).



They are implicitly linked in their definition order.



``` puml {hide=false}
@startuml
:Hello world;
:This is defined on
several **lines**;
@enduml
```

## Start/Stop!



You can use&nbsp;`start`&nbsp;and&nbsp;`stop`&nbsp;keywords to denote the beginning and the end of a diagram.


``` puml {hide=false}
@startuml
start
:Hello world;
:This is defined on
several **lines**;
stop
@enduml
```


You can also use the&nbsp;`end`&nbsp;keyword.


``` puml {hide=false}
@startuml
start
:Hello world;
:This is defined on
several **lines**;
end
@enduml
```

## Conditional!


You can use&nbsp;`if`,&nbsp;`then`&nbsp;and&nbsp;`else`&nbsp;keywords to put tests in your diagram. Labels can be provided using parentheses.



``` puml {hide=false}
@startuml

start

if (Graphviz installed?) then (yes)
  :process all\ndiagrams;
else (no)
  :process only
  __sequence__ and __activity__ diagrams;
endif

stop

@enduml
```

You can use the&nbsp;`elseif`&nbsp;keyword to have several tests :


``` puml {hide=false}
@startuml
start
if (condition A) then (yes)
  :Text 1;
elseif (condition B) then (yes)
  :Text 2;
  stop
elseif (condition C) then (yes)
  :Text 3;
elseif (condition D) then (yes)
  :Text 4;
else (nothing)
  :Text else;
endif
stop
@enduml
```


## Repeat loop!


You can use&nbsp;`repeat`&nbsp;and&nbsp;`repeatwhile`&nbsp;keywords to have repeat loops.



``` puml {hide=false}
@startuml

start

repeat
  :read data;
  :generate diagrams;
repeat while (more data?) is (yes)
->no;
stop

@enduml
```


It is also possible to use a full action as&nbsp;`repeat`&nbsp;target and insert an action in the return path using the&nbsp;`backward`&nbsp;keyword.




``` puml {hide=false}
@startuml

start

repeat :foo as starting label;
  :read data;
  :generate diagrams;
backward:This is backward;
repeat while (more data?)

stop

@enduml
```


## While loop!

You can use&nbsp;`while`&nbsp;and&nbsp;`end while`&nbsp;keywords to have repeat loops.


``` puml {hide=false}
@startuml

start

while (data available?)
  :read data;
  :generate diagrams;
endwhile

stop

@enduml
```


It is possible to provide a label after the&nbsp;`endwhile`&nbsp;keyword, or using the&nbsp;`is`&nbsp;keyword.


``` puml {hide=false}
@startuml
while (check filesize ?) is (not empty)
  :read file;
endwhile (empty)
:close file;
@enduml
```

## Parallel processing!


You can use&nbsp;`fork`,&nbsp;`fork again`&nbsp;and&nbsp;`end fork`&nbsp;keywords to denote parallel processing.



``` puml {hide=false}
@startuml

start

if (multiprocessor?) then (yes)
  fork
    :Treatment 1;
  fork again
    :Treatment 2;
  end fork
else (monoproc)
  :Treatment 1;
  :Treatment 2;
endif

@enduml
```


## Notes!



Text formatting can be done using&nbsp;[creole wiki syntax](https://plantuml.com/en/creole).


A note can be floating, using&nbsp;`floating`&nbsp;keyword.


``` puml {hide=false}
@startuml

start
:foo1;
floating note left: This is a note
:foo2;
note right
  This note is on several
  //lines// and can
  contain <b>HTML</b>
  ====
  * Calling the method ""foo()"" is prohibited
end note
stop

@enduml
```

## Colors!



You can specify a&nbsp;[color](https://plantuml.com/en/color)&nbsp;for some activities.



``` puml {hide=false}
@startuml

start
:starting progress;
#HotPink:reading configuration files
These files should be edited at this point!;
#AAAAAA:ending of the process;

@enduml
```

## Arrows!


Using the&nbsp;`->`&nbsp;notation, you can add texts to arrow, and change their&nbsp;[color](https://plantuml.com/en/color).


It's also possible to have dotted, dashed, bold or hidden arrows.



``` puml {hide=false}
@startuml
:foo1;
-> You can put text on arrows;
if (test) then
  -[#blue]->
  :foo2;
  -[#green,dashed]-> The text can
  also be on several lines
  and **very** long...;
  :foo3;
else
  -[#black,dotted]->
  :foo4;
endif
-[#gray,bold]->
:foo5;
@enduml
```


## Connector!


You can use parentheses to denote connector.


``` puml {hide=false}
@startuml
start
:Some activity;
(A)
detach
(A)
:Other activity;
@enduml
```

## Grouping!


You can group activity together by defining partition:


``` puml {hide=false}
@startuml
start
partition Initialization {
    :read config file;
    :init internal variable;
}
partition Running {
    :wait for user interaction;
    :print information;
}

stop
@enduml
```


## Swimlanes!



Using pipe&nbsp;`|`, you can define swimlanes.



It's also possible to change swimlanes&nbsp;[color](https://plantuml.com/en/color).



``` puml {hide=false}
@startuml
|Swimlane1|
start
:foo1;
|#AntiqueWhite|Swimlane2|
:foo2;
:foo3;
|Swimlane1|
:foo4;
|Swimlane2|
:foo5;
stop
@enduml
```


## Detach!



It's possible to remove an arrow using the&nbsp;`detach`&nbsp;keyword.





``` puml {hide=false}
@startuml
 :start;
 fork
   :foo1;
   :foo2;
 fork again
   :foo3;
   detach
 endfork
 if (foo4) then
   :foo5;
   detach
 endif
 :foo6;
 detach
 :foo7;
 stop
@enduml
```


## SDL (Specification and Description Language)!



By changing the final&nbsp;`;`&nbsp;separator, you can set different rendering for the activity:

*  `|`
*  `<`
*  `>`
*  `/`
*  `\\`
*  `]`
*  `}`



``` puml {hide=false}
@startuml
:Ready;
:next(o)|
:Receiving;
split
 :nak(i)<
 :ack(o)>
split again
 :ack(i)<
 :next(o)
 on several lines|
 :i := i + 1]
 :ack(o)>
split again
 :err(i)<
 :nak(o)>
split again
 :foo/
split again
 :bar\\
split again
 :i > 5}
stop
end split
:finish;
@enduml
```

![](https://s.plantuml.com/imgw/img-38e43aca114123afbb019e57bb175865.webp " ")



## Complete example!



``` puml {hide=false}
@startuml

start
:ClickServlet.handleRequest();
:new page;
if (Page.onSecurityCheck) then (true)
  :Page.onInit();
  if (isForward?) then (no)
    :Process controls;
    if (continue processing?) then (no)
      stop
    endif

    if (isPost?) then (yes)
      :Page.onPost();
    else (no)
      :Page.onGet();
    endif
    :Page.onRender();
  endif
else (false)
endif

if (do redirect?) then (yes)
  :redirect process;
else
  if (do forward?) then (yes)
    :Forward request;
  else (no)
    :Render page template;
  endif
endif

stop

@enduml
```
