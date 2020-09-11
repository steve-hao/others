# Salt (Wireframe)


**Salt**&nbsp;is a subproject included in PlantUML that may help you to design graphical interface or&nbsp;[_Website Wireframe or Page Schematic or Screen Blueprint_](https://en.wikipedia.org/wiki/Website_wireframe).



The goal of this tool is to discuss about simple and sample windows.



You can use either&nbsp;`@startsalt`&nbsp;keyword, or&nbsp;`@startuml`&nbsp;followed by a line with&nbsp;`salt`&nbsp;keyword.

## Basic widgets!



A window must start and end with brackets. You can then define:



*  Button using&nbsp;`[`&nbsp;and&nbsp;`]`.
*  Radio button using&nbsp;`(`&nbsp;and&nbsp;`)`.
*  Checkbox using&nbsp;`[`&nbsp;and&nbsp;`]`.
*  User text area using&nbsp;`"`.
*  Droplist using&nbsp;`^`.


``` puml {hide=false}
@startsalt
{
  Just plain text
  [This is my button]
  ()  Unchecked radio
  (X) Checked radio
  []  Unchecked box
  [X] Checked box
  "Enter text here   "
  ^This is a droplist^
}
@endsalt
```

## Using grid!


A table is automatically created when you use an opening bracket&nbsp;`{`. And you have to use&nbsp;`|`&nbsp;to separate columns.


For example:


``` puml {hide=false}
@startsalt
{
  Login    | "MyName   "
  Password | "****     "
  [Cancel] | [  OK   ]
}
@endsalt
```


Just after the opening bracket, you can use a character to define if you want to draw lines or columns of the grid :



|   |   |
|---|---|
| **Symbol** | **Result** |
| `#` | To display all vertical and horizontal lines |
| `!` | To display all vertical lines |
| `-` | To display all horizontal lines |
| `+` | To display external lines |





``` puml {hide=false}
@startsalt
{+
  Login    | "MyName   "
  Password | "****     "
  [Cancel] | [  OK   ]
}
@endsalt
```


## Group box!


[more info](http://forum.plantuml.net/5840/please-allow-to-create-groupboxes-in-salt?show=5840#q5840)



``` puml {hide=false}
@startsalt
{^"My group box"
  Login    | "MyName   "
  Password | "****     "
  [Cancel] | [  OK   ]
}
@endsalt
```


## Using separator!


You can use several horizontal lines as separator.


``` puml {hide=false}
@startsalt
{
  Text1
  ..
  "Some field"
  ==
  Note on usage
  ~~
  Another text
  --
  [Ok]
}
@endsalt
```


## Tree widget!



To have a Tree, you have to start with&nbsp;`{T`&nbsp;and to use&nbsp;`+`&nbsp;to denote hierarchy.





``` puml {hide=false}
@startsalt
{
{T
 + World
 ++ America
 +++ Canada
 +++ USA
 ++++ New York
 ++++ Boston
 +++ Mexico
 ++ Europe
 +++ Italy
 +++ Germany
 ++++ Berlin
 ++ Africa
}
}
@endsalt
```


## Enclosing brackets!



You can define subelements by opening a new opening bracket.





``` puml {hide=false}
@startsalt
{
Name         | "                 "
Modifiers:   | { (X) public | () default | () private | () protected
                [] abstract | [] final   | [] static }
Superclass:  | { "java.lang.Object " | [Browse...] }
}
@endsalt
```


## Adding tabs!


You can add tabs using&nbsp;`{/`&nbsp;notation. Note that you can use HTML code to have bold text.



``` puml {hide=false}
@startsalt
{+
{/ <b>General | Fullscreen | Behavior | Saving }
{
{ Open image in: | ^Smart Mode^ }
[X] Smooth images when zoomed
[X] Confirm image deletion
[ ] Show hidden images
}
[Close]
}
@endsalt
```



Tab could also be vertically oriented:



``` puml {hide=false}
@startsalt
{+
{/ <b>General
Fullscreen
Behavior
Saving } |
{
{ Open image in: | ^Smart Mode^ }
[X] Smooth images when zoomed
[X] Confirm image deletion
[ ] Show hidden images
[Close]
}
}
@endsalt
```


## Using menu!



You can add a menu by using&nbsp;`{*`&nbsp;notation.





``` puml {hide=false}
@startsalt
{+
{* File | Edit | Source | Refactor }
{/ General | Fullscreen | Behavior | Saving }
{
{ Open image in: | ^Smart Mode^ }
[X] Smooth images when zoomed
[X] Confirm image deletion
[ ] Show hidden images
}
[Close]
}
@endsalt
```


It is also possible to open a menu:


``` puml {hide=false}
@startsalt
{+
{* File | Edit | Source | Refactor
 Refactor | New | Open File | - | Close | Close All }
{/ General | Fullscreen | Behavior | Saving }
{
{ Open image in: | ^Smart Mode^ }
[X] Smooth images when zoomed
[X] Confirm image deletion
[ ] Show hidden images
}
[Close]
}
@endsalt
```


## Advanced table!



You can use two special notations for table :

*  `*`&nbsp;to indicate that a cell with span with left
*  `.`&nbsp;to denotate an empty cell


``` puml {hide=false}
@startsalt
{#
. | Column 2 | Column 3
Row header 1 | value 1 | value 2
Row header 2 | A long cell | *
}
@endsalt
```


## OpenIconic!



[OpenIconic](https://useiconic.com/open/)&nbsp;is an very nice open source icon set. Those icons have been integrated into the&nbsp;[creole parser](https://plantuml.com/en/creole), so you can use them out-of-the-box. You can use the following syntax:&nbsp;`<&ICON_NAME>`.


``` puml {hide=false}
@startsalt
{
  Login<&person> | "MyName   "
  Password<&key> | "****     "
  [Cancel <&circle-x>] | [OK <&account-login>]
}
@endsalt
```





The complete list is available on OpenIconic Website, or you can use the following special diagram:







``` puml {hide=false}
@startuml
listopeniconic
@enduml
```

![](https://s.plantuml.com/imgw/img-be9f8b67d933ea9cd088fee8f739619d.webp " ")



## Include Salt!



You can&nbsp;[read the following explanation](http://forum.plantuml.net/2427/salt-with-minimum-flowchat-capabilities?show=2427#q2427).







``` puml {hide=false}
@startuml
(*) --> "
{{
salt
{+
<b>an example
choose one option
()one
()two
[ok]
}
}}
" as choose

choose -right-> "
{{
salt
{+
<b>please wait
operation in progress
<&clock>
[cancel]
}
}}
" as wait
wait -right-> "
{{
salt
{+
<b>success
congratulations!
[ok]
}
}}
" as success

wait -down-> "
{{
salt
{+
<b>error
failed, sorry
[ok]
}
}}
"
@enduml
```

![](https://s.plantuml.com/imgw/img-a11ebad368b27899db1e9c25afb3a902.webp " ")





It can also be combined with&nbsp;[define macro](https://plantuml.com/en/preprocessing#macro_definition).





``` puml {hide=false}
@startuml
!unquoted procedure SALT($x)
"{{
salt
%invoke_procedure("_"+$x)
}}" as $x
!endprocedure

!procedure _choose()
{+
<b>an example
choose one option
()one
()two
[ok]
}
!endprocedure

!procedure _wait()
{+
<b>please wait
operation in progress
<&clock>
[cancel]
}
!endprocedure

!procedure _success()
{+
<b>success
congratulations!
[ok]
}
!endprocedure

!procedure _error()
{+
<b>error
failed, sorry
[ok]
}
!endprocedure

(*) --> SALT(choose)
-right-> SALT(wait)
wait -right-> SALT(success)
wait -down-> SALT(error)
@enduml
```

![](https://s.plantuml.com/imgw/img-d18817d0f69aee4fbc75215138169c87.webp " ")



## Scroll Bars!



You can use "S" as scroll bar like in following examples:





``` puml {hide=false}
@startsalt
{S
Message
.
.
.
.
}
@endsalt
```



``` puml {hide=false}
@startsalt
{SI
Message
.
.
.
.
}
@endsalt
```


``` puml {hide=false}
@startsalt
{S-
Message
.
.
.
.
}
@endsalt
```

