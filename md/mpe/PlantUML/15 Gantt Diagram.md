## 15 Gantt Diagram

The Gantt is described in natural language, using very simple sentences (subject-verb-complement).

### 15.1 Declaring tasks

Tasks defined using square bracket.

#### 15.1.1 Duration

Their durations are defined using the last verb:

``` puml {hide=false}
@startgantt
[Prototype design] lasts 15 days
[Test prototype] lasts 10 days
-- All example --
[Task 1 (1 day)] lasts 1 day
[T2 (5 days)] lasts 5 days
[T3 (1 week)] lasts 1 week
[T4 (1 week and 4 days)] lasts 1 week and 4 days
[T5 (2 weeks)] lasts 2 weeks
@endgantt
```

#### 15.1.2 Start

Their beginning are defined using the start verb:

``` puml {hide=false}
@startuml
[Prototype design] lasts 15 days
[Test prototype] lasts 10 days
Project starts 2020-07-01
[Prototype design] starts 2020-07-01
[Test prototype] starts 2020-07-16
@enduml
```

#### 15.1.3 End

Their ending are defined using the end verb:

``` puml {hide=false}
@startuml
[Prototype design] lasts 15 days
[Test prototype] lasts 10 days
Project starts 2020-07-01
[Prototype design] ends 2020-07-15
[Test prototype] ends 2020-07-25
@enduml
```

#### 15.1.4 Start/End

It is possible to define both absolutely, by specifying dates:

``` puml {hide=false}
@startuml
Project starts 2020-07-01
[Prototype design] starts 2020-07-01
[Test prototype] starts 2020-07-16
[Prototype design] ends 2020-07-15
[Test prototype] ends 2020-07-25
@enduml
```

### 15.2 One-line declaration (with the and conjunction)

It is possible to combine declaration on one line with the and conjunction.

``` puml {hide=false}
@startuml
Project starts 2020-07-01
[Prototype design] starts 2020-07-01 and ends 2020-07-15
[Test prototype] starts 2020-07-16 and lasts 10 days
@enduml
```

### 15.3 Adding constraints

It is possible to add constraints between tasks.

``` puml {hide=false}
@startgantt
[Prototype design] lasts 15 days
[Test prototype] lasts 10 days
[Test prototype] starts at [Prototype design]'s end
@endgantt
```

``` puml {hide=false}
@startgantt
[Prototype design] lasts 10 days
[Code prototype] lasts 10 days
[Write tests] lasts 5 days
[Code prototype] starts at [Prototype design]'s end
[Write tests] starts at [Code prototype]'s start
@endgantt
```

### 15.4 Short names

It is possible to define short name for tasks with the as keyword.

``` puml {hide=false}
@startgantt
[Prototype design] as [D] lasts 15 days
[Test prototype] as [T] lasts 10 days
[T] starts at [D]'s end
@endgantt
```

### 15.5 Customize colors

It is also possible to customize colors with is colored in.

``` puml {hide=false}
@startgantt
[Prototype design] lasts 13 days
[Test prototype] lasts 4 days
[Test prototype] starts at [Prototype design]'s end
[Prototype design] is colored in Fuchsia/FireBrick
[Test prototype] is colored in GreenYellow/Green
@endgantt
```

### 15.6 Completion status

You can set the completion status of a task.

``` puml {hide=false}
@startgantt
[foo] lasts 21 days
[foo] is 40% completed
[bar] lasts 30 days and is 10% complete
@endgantt
```

### 15.7 Milestone

You can define Milestones using the happen verb.

#### 15.7.1 Relative milestone (use of constraints)


``` puml {hide=false}
@startgantt
[Test prototype] lasts 10 days
[Prototype completed] happens at [Test prototype]'s end
[Setup assembly line] lasts 12 days
[Setup assembly line] starts at [Test prototype]'s end
@endgantt
```

#### 15.7.2 Absolute milestone (use of fixed date)

``` puml {hide=false}
@startgantt
Project starts 2020-07-01
[Test prototype] lasts 10 days
[Prototype completed] happens 2020-07-10
[Setup assembly line] lasts 12 days
[Setup assembly line] starts at [Test prototype]'s end
@endgantt
```

#### 15.7.3 Milestone of maximum end of tasks

``` puml {hide=false}
@startgantt
[Task1] lasts 4 days
then [Task1.1] lasts 4 days
[Task1.2] starts at [Task1]'s end and lasts 7 days
[Task2] lasts 5 days
then [Task2.1] lasts 4 days
[MaxTaskEnd] happens at [Task1.1]'s end
[MaxTaskEnd] happens at [Task1.2]'s end
[MaxTaskEnd] happens at [Task2.1]'s end
@endgantt
```

[Ref. QA-10764]

### 15.8 Hyperlinks

You can add hyperlinks to tasks.

``` puml {hide=false}
@startgantt
[task1] lasts 10 days
[task1] links to [[http://plantuml.com]]
@endgantt
```

### 15.9 Calendar

You can specify a starting date for the whole project. By default, the first task starts at this date.

``` puml {hide=false}
@startgantt
Project starts the 20th of september 2017
[Prototype design] as [TASK1] lasts 13 days
[TASK1] is colored in Lavender/LightBlue
@endgantt
```

### 15.10 Coloring days

It is possible to add colors to some days.

``` puml {hide=false}
@startgantt
Project starts the 2020/09/01
2020/09/07 is colored in salmon
2020/09/13 to 2020/09/16 are colored in lightblue
[Prototype design] as [TASK1] lasts 22 days
[TASK1] is colored in Lavender/LightBlue
[Prototype completed] happens at [TASK1]'s end
@endgantt
```

### 15.11 Changing scale

You can change scale for very long project, with one of those parameters:
* printscale
* ganttscale
* projectscale

and one of the values:
* daily (by default)
* weekly
* monthly

(See QA-11272, QA-9041 and QA-10948)

#### 15.11.1 Daily (by default)

``` puml {hide=false}
@startuml
saturday are closed
sunday are closed
Project starts the 1st of january 2021
[Prototype design end] as [TASK1] lasts 19 days
[TASK1] is colored in Lavender/LightBlue
[Testing] lasts 14 days
[TASK1]->[Testing]
2021-01-18 to 2021-01-22 are named [End's committee]
2021-01-18 to 2021-01-22 are colored in salmon
@enduml
```

#### 15.11.2 Weekly

``` puml {hide=false}
@startuml
printscale weekly
saturday are closed
sunday are closed
Project starts the 1st of january 2021
[Prototype design end] as [TASK1] lasts 19 days
[TASK1] is colored in Lavender/LightBlue
[Testing] lasts 14 days
[TASK1]->[Testing]
2021-01-18 to 2021-01-22 are named [End's committee]
2021-01-18 to 2021-01-22 are colored in salmon
@enduml
```

``` puml {hide=false}
@startgantt
printscale weekly
Project starts the 20th of september 2020
[Prototype design] as [TASK1] lasts 130 days
[TASK1] is colored in Lavender/LightBlue
[Testing] lasts 20 days
[TASK1]->[Testing]
2021-01-18 to 2021-01-22 are named [End's committee]
2021-01-18 to 2021-01-22 are colored in salmon
@endgantt
```

#### 15.11.3 Monthly

``` puml {hide=false}
@startgantt
projectscale monthly
Project starts the 20th of september 2020
[Prototype design] as [TASK1] lasts 130 days
[TASK1] is colored in Lavender/LightBlue
[Testing] lasts 20 days
[TASK1]->[Testing]
2021-01-18 to 2021-01-22 are named [End's committee]
2021-01-18 to 2021-01-22 are colored in salmon
@endgantt
```

### 15.12 Close day

It is possible to close some day.

``` puml {hide=false}
@startgantt
project starts the 2018/04/09
saturday are closed
sunday are closed
2018/05/01 is closed
2018/04/17 to 2018/04/19 is closed
[Prototype design] lasts 14 days
[Test prototype] lasts 4 days
[Test prototype] starts at [Prototype design]'s end
[Prototype design] is colored in Fuchsia/FireBrick
[Test prototype] is colored in GreenYellow/Green
@endgantt
```

Then it is possible to open some closed day.

``` puml {hide=false}
@startgantt
2020-07-07 to 2020-07-17 is closed
2020-07-13 is open
Project starts the 2020-07-01
[Prototype design] lasts 10 days
Then [Test prototype] lasts 10 days
@endgantt
```

### 15.13 Simplified task succession

It's possible to use the then keyword to denote consecutive tasks.

``` puml {hide=false}
@startgantt
[Prototype design] lasts 14 days
then [Test prototype] lasts 4 days
then [Deploy prototype] lasts 6 days
@endgantt
```

You can also use arrow ->

``` puml {hide=false}
@startgantt
[Prototype design] lasts 14 days
[Build prototype] lasts 4 days
[Prepare test] lasts 6 days
[Prototype design] -> [Build prototype]
[Prototype design] -> [Prepare test]
@endgantt
```

### 15.14 Separator

You can use -- to separate sets of tasks.

``` puml {hide=false}
@startgantt
[Task1] lasts 10 days
then [Task2] lasts 4 days
-- Phase Two --
then [Task3] lasts 5 days
then [Task4] lasts 6 days
@endgantt
```

### 15.15 Working with resources

You can affect tasks on resources using the on keyword and brackets for resource name.

``` puml {hide=false}
@startgantt
[Task1] on {Alice} lasts 10 days
[Task2] on {Bob:50%} lasts 2 days
then [Task3] on {Alice:25%} lasts 1 days
@endgantt
```

Multiple resources can be assigned to a task:

``` puml {hide=false}
@startgantt
[Task1] on {Alice} {Bob} lasts 20 days
@endgantt
```

Resources can be marked as off on specific days:

``` puml {hide=false}
@startgantt
project starts on 2020-06-19
[Task1] on {Alice} lasts 10 days
{Alice} is off on 2020-06-24 to 2020-06-26
@endgantt
```

### 15.16 Complex example

It also possible to use the and conjunction.
You can also add delays in constraints.

``` puml {hide=false}
@startgantt
[Prototype design] lasts 13 days and is colored in Lavender/LightBlue
[Test prototype] lasts 9 days and is colored in Coral/Green and starts 3 days after [Prototype design]'s end
[Write tests] lasts 5 days and ends at [Prototype design]'s end
[Hire tests writers] lasts 6 days and ends at [Write tests]'s start
[Init and write tests report] is colored in Coral/Green
[Init and write tests report] starts 1 day before [Test prototype]'s start and ends at [Test prototype]'s end
@endgantt
```

### 15.17 Comments

As is mentioned on Common Commands page:  Everything that starts with simple quote ' is a comment.

You can also put comments on several lines using /' to start and '/ to end.

(i.e.: the first character (except space character) of a comment line must be a simple quote ')

``` puml {hide=false}
@startgantt
' This is a comment
[T1] lasts 3 days
/' this comment
is on several lines '/
[T2] starts at [T1]'s end and lasts 1 day
@endgantt
```

### 15.18 Using style

``` puml {hide=false}
@startuml
<style>
ganttDiagram {
task {
FontName Helvetica
FontColor red
FontSize 18
FontStyle bold
BackGroundColor GreenYellow
LineColor blue
}
milestone {
FontColor blue
FontSize 25
FontStyle italic
BackGroundColor yellow
LineColor red
}
note {
FontColor DarkGreen
FontSize 10
LineColor OrangeRed
}
}
</style>
[Task1] lasts 20 days
note bottom
memo1 ...
memo2 ...
explanations1 ...
explanations2 ...
end note
[Task2] lasts 4 days
[Task1] -> [Task2]
-- Separator title --
[M1] happens on 5 days after [Task1]'s end
-- end --
@enduml
```

### 15.19 Add notes


``` puml {hide=false}
@startgantt
[task01] lasts 15 days
note bottom
memo1 ...
memo2 ...
explanations1 ...
explanations2 ...
end note
[task01] -> [task02]
@endgantt
```

Example with overlap.

``` puml {hide=false}
@startgantt
[task01] lasts 15 days
note bottom
memo1 ...
memo2 ...
explanations1 ...
explanations2 ...
end note
[task01] -> [task02]
[task03] lasts 5 days
@endgantt
```

``` puml {hide=false}
@startgantt
-- test01 --
[task01] lasts 4 days
note bottom
'note left
memo1 ...
memo2 ...
explanations1 ...
explanations2 ...
end note
[task02] lasts 8 days
[task01] -> [task02]
note bottom
'note left
memo1 ...
memo2 ...
explanations1 ...
explanations2 ...
end note
-- test02 --
[task03] as [t3] lasts 7 days
[t3] -> [t4]
@endgantt
```

TODO: DONE Thanks for correction (of #386 on v1.2020.18) when overlapping

``` puml {hide=false}
@startgantt
Project starts 2020-09-01
[taskA] starts 2020-09-01 and lasts 3 days
[taskB] starts 2020-09-10 and lasts 3 days
[taskB] displays on same row as [taskA]
[task01] starts 2020-09-05 and lasts 4 days
then [task02] lasts 8 days
note bottom
note for task02
more notes
end note
then [task03] lasts 7 days
note bottom
note for task03
more notes
end note
-- separator --
[taskC] starts 2020-09-02 and lasts 5 days
[taskD] starts 2020-09-09 and lasts 5 days
[taskD] displays on same row as [taskC]
[task 10] starts 2020-09-05 and lasts 5 days
then [task 11] lasts 5 days
note bottom
note for task11
more notes
end note
@endgantt
```

### 15.20 Pause tasks

``` puml {hide=false}
@startgantt
Project starts the 5th of december 2018
saturday are closed
sunday are closed
2018/12/29 is opened
[Prototype design] lasts 17 days
[Prototype design] pauses on 2018/12/13
[Prototype design] pauses on 2018/12/14
[Prototype design] pauses on monday
[Test prototype] starts at [Prototype design]'s end and lasts 2 weeks
@endgantt
```

### 15.21 Change link colors

``` puml {hide=false}
@startgantt
[T1] lasts 4 days
[T2] lasts 4 days and starts 3 days after [T1]'s end with blue dotted link
[T3] lasts 4 days and starts 3 days after [T2]'s end with green bold link
[T4] lasts 4 days and starts 3 days after [T3]'s end with green dashed link
@endgantt
```

``` puml {hide=false}
@startuml
Links are colored in blue
[Prototype design] lasts 14 days
[Build prototype] lasts 4 days
[Prepare test] lasts 6 days
[Prototype design] -[#FF00FF]-> [Build prototype]
[Prototype design] -[dotted]-> [Prepare test]
@enduml
```

### 15.22 Tasks or Milestones on the same line

``` puml {hide=false}
@startgantt
[Prototype design] lasts 13 days
[Test prototype] lasts 4 days and 1 week
[Test prototype] starts 1 week and 2 days after [Prototype design]'s end
[Test prototype] displays on same row as [Prototype design]
[r1] happens on 5 days after [Prototype design]'s end
[r2] happens on 5 days after [r1]'s end
[r3] happens on 5 days after [r2]'s end
[r2] displays on same row as [r1]
[r3] displays on same row as [r1]
@endgantt
```

### 15.23 Highlight today

``` puml {hide=false}
@startgantt
Project starts the 20th of september 2018
sunday are close
2018/09/21 to 2018/09/23 are colored in salmon
2018/09/21 to 2018/09/30 are named [Vacation in the Bahamas]
today is 30 days after start and is colored in #AAF
[Foo] happens 40 days after start
[Dummy] lasts 10 days and starts 10 days after start
@endgantt
```

### 15.24 Task between two milestones

``` puml {hide=false}
@startgantt
project starts on 2020-07-01
[P_start] happens 2020-07-03
[P_end] happens 2020-07-13
[Prototype design] occurs from [P_start] to [P_end]
@endgantt
```

### 15.25 Grammar and verbal form

Verbal form Example
* [T] starts
* [M] happens

### 15.26 Add title, header, footer, caption or legend on gantt diagram

``` puml {hide=false}
@startuml
header some header
footer some footer
title My title
[Prototype design] lasts 13 days
legend
The legend
end legend
caption This is caption
@enduml
```

(See also: Common commands)

### 15.27 Removing Foot Boxes

You can use the hide footbox keywords to remove the footboxes of the ganttdiagram (as for sequencediagram).

Examples on:
* daily scale (without project start)

``` puml {hide=false}
@startgantt
hide footbox
title Foot Box removed
[Prototype design] lasts 15 days
[Test prototype] lasts 10 days
@endgantt
```

* daily scale

``` puml {hide=false}
@startgantt
Project starts the 20th of september 2017
[Prototype design] as [TASK1] lasts 13 days
[TASK1] is colored in Lavender/LightBlue
hide footbox
@endgantt
```

* weekly scale

``` puml {hide=false}
@startgantt
hide footbox
printscale weekly
saturday are closed
sunday are closed
Project starts the 1st of january 2021
[Prototype design end] as [TASK1] lasts 19 days
[TASK1] is colored in Lavender/LightBlue
[Testing] lasts 14 days
[TASK1]->[Testing]
2021-01-18 to 2021-01-22 are named [End's committee]
2021-01-18 to 2021-01-22 are colored in salmon
@endgantt
```

* monthly scale

``` puml {hide=false}
@startgantt
hide footbox
projectscale monthly
Project starts the 20th of september 2020
[Prototype design] as [TASK1] lasts 130 days
[TASK1] is colored in Lavender/LightBlue
[Testing] lasts 20 days
[TASK1]->[Testing]
2021-01-18 to 2021-01-22 are named [End's committee]
2021-01-18 to 2021-01-22 are colored in salmon
@endgantt
```
