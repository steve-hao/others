## Basic examples!

The sequence&nbsp;`->`&nbsp;is used to draw a message between two participants. Participants do not have to be explicitly declared.



To have a dotted arrow, you use&nbsp;`-->`



It is also possible to use&nbsp;`<-`&nbsp;and&nbsp;`<--`. That does not change the drawing, but may improve readability. Note that this is only true for sequence diagrams, rules are different for the other diagrams.


``` puml {hide=false}
@startuml
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

Alice -> Bob: Another authentication Request
Alice <-- Bob: Another authentication Response
@enduml
```


## Declaring participant!


If the keyword&nbsp;`participant`&nbsp;is used to declare a participant, more control on that participant is possible.



The order of declaration will be the (default)&nbsp;**order of display**.



Using these other keywords to declare participants will&nbsp;**change the shape**&nbsp;of the participant representation:

*  `actor`
*  `boundary`
*  `control`
*  `entity`
*  `database`
*  `collections`


``` puml {hide=false}
@startuml
actor Foo1
boundary Foo2
control Foo3
entity Foo4
database Foo5
collections Foo6
Foo1 -> Foo2 : To boundary
Foo1 -> Foo3 : To control
Foo1 -> Foo4 : To entity
Foo1 -> Foo5 : To database
Foo1 -> Foo6 : To collections

@enduml
```

Rename a participant using the&nbsp;`as`&nbsp;keyword.

You can also change the background&nbsp;[color](https://plantuml.com/en/color)&nbsp;of actor or participant.

``` puml {hide=false}
@startuml
actor Bob #red
participant Alice 
participant "I have a really\nlong name" as L #99FF99
/' You can also declare:
   participant L as "I have a really\nlong name"  #99FF99
  '/

Alice->Bob: Authentication Request
Bob->Alice: Authentication Response
Bob->L: Log transaction
@enduml
```

You can use the&nbsp;`order`&nbsp;keyword to customize the display order of participants.

``` puml {hide=false}
@startuml
participant Last order 30
participant Middle order 20
participant First order 10
@enduml
```

## Use non-letters in participants!

You can use quotes to define participants. And you can use the&nbsp;`as`&nbsp;keyword to give an alias to those participants.



``` puml {hide=false}
@startuml
Alice -> "Bob()" : Hello
"Bob()" -> "This is very\nlong" as Long
Long --> "Bob()" : ok
@enduml
```

## Message to Self!

A participant can send a message to itself.

It is also possible to have multi-line using&nbsp;`\n`.


``` puml {hide=false}
@startuml
Alice->Alice: this is a signal to self.\nIt also demonstrates\nmultiline \ntext
@enduml
```

## Text alignment!

### Text of response message below the arrow

You can put the text of the response message below the arrow, with the&nbsp;`skinparam responseMessageBelowArrow True`&nbsp;command.



``` puml {hide=false}
@startuml
skinparam responseMessageBelowArrow True
Bob -> Alice : hello
Alice -> Bob : ok
@enduml
```

TODO

Link to Text Alignment on&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;page.

## Change arrow style!

You can change arrow style by several ways:

*  add a final&nbsp;`x`&nbsp;to denote a lost message
*  use&nbsp;`\`&nbsp;or&nbsp;`/`&nbsp;instead of&nbsp;`<`&nbsp;or&nbsp;`>`&nbsp;to have only the bottom or top part of the arrow
*  repeat the arrow head (for example,&nbsp;`>>`&nbsp;or&nbsp;`//`) head to have a thin drawing
*  use&nbsp;`--`&nbsp;instead of&nbsp;`-`&nbsp;to have a dotted arrow
*  add a final "o" at arrow head
*  use bidirectional arrow&nbsp;`<->`


``` puml {hide=false}
@startuml
Bob ->x Alice
Bob -> Alice
Bob ->> Alice
Bob -\ Alice
Bob \\- Alice
Bob //-- Alice

Bob ->o Alice
Bob o\\-- Alice

Bob <-> Alice
Bob <->o Alice
@enduml
```

## Change arrow color!


You can change the color of individual arrows using the following notation:



``` puml {hide=false}
@startuml
Bob -[#red]> Alice : hello
Alice -[#0000FF]->Bob : ok
@enduml
```

## Message sequence numbering!

The keyword&nbsp;`autonumber`&nbsp;is used to automatically add number to messages.





``` puml {hide=false}
@startuml
autonumber
Bob -> Alice : Authentication Request
Bob <- Alice : Authentication Response
@enduml
```

You can specify a startnumber with&nbsp;`autonumber //start//`&nbsp;, and also an increment with&nbsp;`autonumber //start// //increment//`.


``` puml {hide=false}
@startuml
autonumber
Bob -> Alice : Authentication Request
Bob <- Alice : Authentication Response

autonumber 15
Bob -> Alice : Another authentication Request
Bob <- Alice : Another authentication Response

autonumber 40 10
Bob -> Alice : Yet another authentication Request
Bob <- Alice : Yet another authentication Response

@enduml
```

You can specify a format for your number by using between double-quote.


The formatting is done with the Java class&nbsp;`DecimalFormat`&nbsp;(`0`&nbsp;means digit,&nbsp;`#`&nbsp;means digit and zero if absent).



You can use some html tag in the format.



``` puml {hide=false}
@startuml
autonumber "<b>[000]"
Bob -> Alice : Authentication Request
Bob <- Alice : Authentication Response

autonumber 15 "<b>(<u>##</u>)"
Bob -> Alice : Another authentication Request
Bob <- Alice : Another authentication Response

autonumber 40 10 "<font color=red><b>Message 0  "
Bob -> Alice : Yet another authentication Request
Bob <- Alice : Yet another authentication Response

@enduml
```

You can also use&nbsp;`autonumber stop`&nbsp;and&nbsp;`autonumber resume //increment// //format//`&nbsp;to respectively pause and resume automatic numbering.


``` puml {hide=false}
@startuml
autonumber 10 10 "<b>[000]"
Bob -> Alice : Authentication Request
Bob <- Alice : Authentication Response

autonumber stop
Bob -> Alice : dummy

autonumber resume "<font color=red><b>Message 0  "
Bob -> Alice : Yet another authentication Request
Bob <- Alice : Yet another authentication Response

autonumber stop
Bob -> Alice : dummy

autonumber resume 1 "<font color=blue><b>Message 0  "
Bob -> Alice : Yet another authentication Request
Bob <- Alice : Yet another authentication Response
@enduml
```

## Page Title, Header and Footer!


The&nbsp;`title`&nbsp;keyword is used to add a title to the page.



Pages can display headers and footers using&nbsp;`header`&nbsp;and&nbsp;`footer`.


``` puml {hide=false}
@startuml

header Page Header
footer Page %page% of %lastpage%

title Example Title

Alice -> Bob : message 1
Alice -> Bob : message 2

@enduml
```

## Splitting diagrams!


The&nbsp;`newpage`&nbsp;keyword is used to split a diagram into several images.


You can put a title for the new page just after the&nbsp;`newpage`&nbsp;keyword. This title overrides the previously specified title if any.


This is very handy with&nbsp;_Word_&nbsp;to print long diagram on several pages.


(Note: this really does work. Only the first page is shown below, but it is a display artifact.)



``` puml {hide=false}
@startuml

Alice -> Bob : message 1
Alice -> Bob : message 2

newpage

Alice -> Bob : message 3
Alice -> Bob : message 4

newpage A title for the\nlast page

Alice -> Bob : message 5
Alice -> Bob : message 6
@enduml
```


## Grouping message!

It is possible to group messages together using the following keywords:

*  `alt/else`
*  `opt`
*  `loop`
*  `par`
*  `break`
*  `critical`
*  `group`, followed by a text to be displayed



It is possible a add a text that will be displayed into the header (except for&nbsp;`group`).


The&nbsp;`end`&nbsp;keyword is used to close the group.


Note that it is possible to nest groups.



``` puml {hide=false}
@startuml
Alice -> Bob: Authentication Request

alt successful case

    Bob -> Alice: Authentication Accepted

else some kind of failure

    Bob -> Alice: Authentication Failure
    group My own label
    Alice -> Log : Log attack start
        loop 1000 times
            Alice -> Bob: DNS Attack
        end
    Alice -> Log : Log attack end
    end

else Another type of failure

   Bob -> Alice: Please repeat

end
@enduml
```


## Notes on messages!

It is possible to put notes on message using the&nbsp;`note left`&nbsp;or&nbsp;`note right`&nbsp;keywords&nbsp;_just after the message_.

You can have a multi-line note using the&nbsp;`end note`&nbsp;keywords.

``` puml {hide=false}
@startuml
Alice->Bob : hello
note left: this is a first note

Bob->Alice : ok
note right: this is another note

Bob->Bob : I am thinking
note left
a note
can also be defined
on several lines
end note
@enduml
```


## Some other notes!

It is also possible to place notes relative to participant with&nbsp;`note left of`&nbsp;,&nbsp;`note right of`&nbsp;or&nbsp;`note over`&nbsp;keywords.


It is possible to highlight a note by changing its background&nbsp;[color](https://plantuml.com/en/color).


You can also have a multi-line note using the&nbsp;`end note`&nbsp;keywords.


``` puml {hide=false}
@startuml
participant Alice
participant Bob
note left of Alice #aqua
This is displayed
left of Alice.
end note

note right of Alice: This is displayed right of Alice.

note over Alice: This is displayed over Alice.

note over Alice, Bob #FFAAAA: This is displayed\n over Bob and Alice.

note over Bob, Alice
This is yet another
example of
a long note.
end note
@enduml
```


## Changing notes shape!


You can use&nbsp;`hnote`&nbsp;and&nbsp;`rnote`&nbsp;keywords to change note shapes.

``` puml {hide=false}
@startuml
caller -> server : conReq
hnote over caller : idle
caller <- server : conConf
rnote over server
 "r" as rectangle
 "h" as hexagon
endrnote
@enduml
```


## Creole and HTML!


[It is also possible to use creole formatting:](https://plantuml.com/en/creole)



``` puml {hide=false}
@startuml
participant Alice
participant "The **Famous** Bob" as Bob

Alice -> Bob : hello --there--
... Some ~~long delay~~ ...
Bob -> Alice : ok
note left
  This is **bold**
  This is //italics//
  This is ""monospaced""
  This is --stroked--
  This is __underlined__
  This is ~~waved~~
end note

Alice -> Bob : A //well formatted// message
note right of Alice
 This is <back:cadetblue><size:18>displayed</size></back>
 __left of__ Alice.
end note
note left of Bob
 <u:red>This</u> is <color #118888>displayed</color>
 **<color purple>left of</color> <s:red>Alice</strike> Bob**.
end note
note over Alice, Bob
 <w:#FF33FF>This is hosted</w> by aaa
end note
@enduml
```


## Divider!

If you want, you can split a diagram using&nbsp;`==`&nbsp;separator to divide your diagram into logical steps.



``` puml {hide=false}
@startuml

== Initialization ==

Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

== Repetition ==

Alice -> Bob: Another authentication Request
Alice <-- Bob: another authentication Response

@enduml
```


## Reference!


You can use reference in a diagram, using the keyword&nbsp;`ref over`.



``` puml {hide=false}
@startuml
participant Alice
actor Bob

ref over Alice, Bob : init

Alice -> Bob : hello

ref over Bob
  This can be on
  several lines
end ref
@enduml
```


## Delay!



You can use&nbsp;`...`&nbsp;to indicate a delay in the diagram. And it is also possible to put a message with this delay.



``` puml {hide=false}
@startuml

Alice -> Bob: Authentication Request
...
Bob --> Alice: Authentication Response
...5 minutes later...
Bob --> Alice: Bye !

@enduml
```

## Space!


You can use&nbsp;`|||`&nbsp;to indicate some spacing in the diagram.



It is also possible to specify a number of pixel to be used.



``` puml {hide=false}
@startuml

Alice -> Bob: message 1
Bob --> Alice: ok
|||
Alice -> Bob: message 2
Bob --> Alice: ok
||45||
Alice -> Bob: message 3
Bob --> Alice: ok

@enduml
```

## Lifeline Activation and Destruction!

The&nbsp;`activate`&nbsp;and&nbsp;`deactivate`&nbsp;are used to denote participant activation.

Once a participant is activated, its lifeline appears.

The&nbsp;`activate`&nbsp;and&nbsp;`deactivate`&nbsp;apply on the previous message.

The&nbsp;`destroy`&nbsp;denote the end of the lifeline of a participant.


``` puml {hide=false}
@startuml
participant User

User -> A: DoWork
activate A

A -> B: << createRequest >>
activate B

B -> C: DoWork
activate C
C --> B: WorkDone
destroy C

B --> A: RequestCreated
deactivate B

A -> User: Done
deactivate A

@enduml
```


Nested lifeline can be used, and it is possible to add a&nbsp;[color](https://plantuml.com/en/color)&nbsp;on the lifeline.



``` puml {hide=false}
@startuml
participant User

User -> A: DoWork
activate A #FFBBBB

A -> A: Internal call
activate A #DarkSalmon

A -> B: << createRequest >>
activate B

B --> A: RequestCreated
deactivate B
deactivate A
A -> User: Done
deactivate A

@enduml
```

Autoactivation is possible and works with the return keywords:


``` puml {hide=false}
@startuml
autoactivate on
alice -> bob : hello
bob -> bob : self call
bill -> bob #005500 : hello from thread 2
bob -> george ** : create
return done in thread 2
return rc
bob -> george !! : delete
return success

@enduml
```

## Return!


Command&nbsp;`return`&nbsp;generates a return message with optional text label.


The return point is that which caused the most recent life-line activation.


The syntax is&nbsp;`return label`&nbsp;where&nbsp;`label`&nbsp;if provided is any string acceptable for conventional messages.


``` puml {hide=false}
@startuml
Bob -> Alice : hello
activate Alice
Alice -> Alice : some action
return bye
@enduml
```

## Participant creation!


You can use the&nbsp;`create`&nbsp;keyword just before the first reception of a message to emphasize the fact that this message is actually&nbsp;_creating_&nbsp;this new object.



``` puml {hide=false}
@startuml
Bob -> Alice : hello

create Other
Alice -> Other : new

create control String
Alice -> String
note right : You can also put notes!

Alice --> Bob : ok

@enduml
```

## Shortcut syntax for activation, deactivation, creation!

Immediately after specifying the target participant, the following syntax can be used:



*  `++`&nbsp;Activate the target (optionally a #color may follow this)
*  `--`&nbsp;Deactivate the source
*  `**`&nbsp;Create an instance of the target
*  `!!`&nbsp;Destroy an instance of the target


``` puml {hide=false}
@startuml
alice -> bob ++ : hello
bob -> bob ++ : self call
bob -> bib ++  #005500 : hello
bob -> george ** : create
return done
return rc
bob -> george !! : delete
return success
@enduml
```

## Incoming and outgoing messages!


You can use incoming or outgoing arrows if you want to focus on a part of the diagram.


Use square brackets to denote the left "`[`" or the right "`]`" side of the diagram.


``` puml {hide=false}
@startuml
[-> A: DoWork

activate A

A -> A: Internal call
activate A

A ->] : << createRequest >>

A<--] : RequestCreated
deactivate A
[<- A: Done
deactivate A
@enduml
```


You can also have the following syntax:



``` puml {hide=false}
@startuml
[-> Bob
[o-> Bob
[o->o Bob
[x-> Bob

[<- Bob
[x<- Bob

Bob ->]
Bob ->o]
Bob o->o]
Bob ->x]

Bob <-]
Bob x<-]
@enduml
```


## Anchors and Duration!


With&nbsp;`teoz`&nbsp;usage it is possible to add anchors to the diagram and use the anchors to specify duration time.



``` puml {hide=false}
@startuml
!pragma teoz true

{start} Alice -> Bob : start doing things during duration
Bob -> Max : something
Max -> Bob : something else
{end} Bob -> Alice : finish

{start} <-> {end} : some time

@enduml
```

## Stereotypes and Spots!


It is possible to add stereotypes to participants using&nbsp;`<<`&nbsp;and&nbsp;`>>`.


In the stereotype, you can add a spotted character in a colored circle using the syntax&nbsp;`(X,color)`.



``` puml {hide=false}
@startuml

participant "Famous Bob" as Bob << Generated >>
participant Alice << (C,#ADD1B2) Testable >>

Bob->Alice: First message

@enduml
```


By default, the&nbsp;_guillemet_&nbsp;character is used to display the stereotype. You can change this behavious using the skinparam&nbsp;`guillemet`:


``` puml {hide=false}
@startuml

skinparam guillemet false
participant "Famous Bob" as Bob << Generated >>
participant Alice << (C,#ADD1B2) Testable >>

Bob->Alice: First message

@enduml
```


``` puml {hide=false}
@startuml

participant Bob << (C,#ADD1B2) >>
participant Alice << (C,#ADD1B2) >>

Bob->Alice: First message

@enduml
```


## More information on titles!


You can use&nbsp;[creole formatting](https://plantuml.com/en/creole)&nbsp;in the title.


``` puml {hide=false}
@startuml

title __Simple__ **communication** example

Alice -> Bob: Authentication Request
Bob -> Alice: Authentication Response

@enduml
```


You can add newline using&nbsp;`\n`&nbsp;in the title description.



``` puml {hide=false}
@startuml

title __Simple__ communication example\non several lines

Alice -> Bob: Authentication Request
Bob -> Alice: Authentication Response

@enduml
```


You can also define title on several lines using&nbsp;`title`&nbsp;and&nbsp;`end title`&nbsp;keywords.



``` puml {hide=false}
@startuml

title
 <u>Simple</u> communication example
 on <i>several</i> lines and using <font color=red>html</font>
 This is hosted by  aaa
end title

Alice -> Bob: Authentication Request
Bob -> Alice: Authentication Response

@enduml
```

## Participants encompass!



It is possible to draw a box around some participants, using&nbsp;`box`&nbsp;and&nbsp;`end box`&nbsp;commands.



You can add an optional title or a optional background color, after the&nbsp;`box`&nbsp;keyword.





``` puml {hide=false}
@startuml

box "Internal Service" #LightBlue
participant Bob
participant Alice
end box
participant Other

Bob -> Alice : hello
Alice -> Other : hello

@enduml
```

## Removing Foot Boxes!



You can use the&nbsp;`hide footbox`&nbsp;keywords to remove the foot boxes of the diagram.


``` puml {hide=false}
@startuml

hide footbox
title Foot Box removed

Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

@enduml
```


## Skinparam!


You can use the&nbsp;[skinparam](https://plantuml.com/en/skinparam)&nbsp;command to change colors and fonts for the drawing.



You can use this command:

*  In the diagram definition, like any other commands,
*  In an&nbsp;[included file](https://plantuml.com/en/preprocessing),
*  In a configuration file, provided in the&nbsp;[command line](https://plantuml.com/en/command-line)&nbsp;or the&nbsp;[ANT task](https://plantuml.com/en/ant-task).



You can also change other rendering parameter, as seen in the following examples:

``` puml {hide=false}
@startuml
skinparam sequenceArrowThickness 2
skinparam roundcorner 20
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C

User -> A: DoWork
activate A

A -> B: Create Request
activate B

B -> C: DoWork
activate C
C --> B: WorkDone
destroy C

B --> A: Request Created
deactivate B

A --> User: Done
deactivate A

@enduml
```


``` puml {hide=false}
@startuml
skinparam backgroundColor #EEEBDC
skinparam handwritten true

skinparam sequence {
ArrowColor DeepSkyBlue
ActorBorderColor DeepSkyBlue
LifeLineBorderColor blue
LifeLineBackgroundColor #A9DCDF

ParticipantBorderColor DeepSkyBlue
ParticipantBackgroundColor DodgerBlue
ParticipantFontName Impact
ParticipantFontSize 17
ParticipantFontColor #A9DCDF

ActorBackgroundColor aqua
ActorFontColor DeepSkyBlue
ActorFontSize 17
ActorFontName Aapex
}

actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C

User -> A: DoWork
activate A

A -> B: Create Request
activate B

B -> C: DoWork
activate C
C --> B: WorkDone
destroy C

B --> A: Request Created
deactivate B

A --> User: Done
deactivate A

@enduml
```


## Changing padding!


It is possible to tune some padding settings.



``` puml {hide=false}
@startuml
skinparam ParticipantPadding 20
skinparam BoxPadding 10

box "Foo1"
participant Alice1
participant Alice2
end box
box "Foo2"
participant Bob1
participant Bob2
end box
Alice1 -> Bob1 : hello
Alice1 -> Out : out
@enduml
```