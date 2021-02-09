## 17 Work Breakdown Structure (WBS)

WBS diagram are still in beta: the syntax may change without notice.

### 17.1 OrgMode syntax

This syntax is compatible with OrgMode

```plantuml {hide=false}
@startwbs
* Business Process Modelling WBS
** Launch the project
*** Complete Stakeholder Research
*** Initial Implementation Plan
** Design phase
*** Model of AsIs Processes Completed
**** Model of AsIs Processes Completed1
**** Model of AsIs Processes Completed2
*** Measure AsIs performance metrics
*** Identify Quick Wins
** Complete innovate phase
@endwbs
```

### 17.2 Change direction

You can change direction using < and >

```plantuml {hide=false}
@startwbs
* Business Process Modelling WBS
** Launch the project
*** Complete Stakeholder Research
*** Initial Implementation Plan
** Design phase
*** Model of AsIs Processes Completed
****< Model of AsIs Processes Completed1
****> Model of AsIs Processes Completed2
***< Measure AsIs performance metrics
***< Identify Quick Wins
@endwbs
```

### 17.3 Arithmetic notation

You can use the following notation to choose diagram side.

```plantuml {hide=false}
@startwbs
+ New Job
++ Decide on Job Requirements
+++ Identity gaps
+++ Review JDs
++++ Sign-Up for courses
++++ Volunteer
++++ Reading
++- Checklist
+++- Responsibilities
+++- Location
++ CV Upload Done
+++ CV Updated
++++ Spelling & Grammar
++++ Check dates
---- Skills
+++ Recruitment sites chosen
@endwbs
```

### 17.4 Removing box

You can use underscore _ to remove box drawing.

```plantuml {hide=false}
@startwbs
+ Project
 + Part One
  + Task 1.1
  - LeftTask 1.2
  + Task 1.3
 + Part Two
  + Task 2.1
  + Task 2.2
  -_ Task 2.2.1 To the left boxless
  -_ Task 2.2.2 To the Left boxless
  +_ Task 2.2.3 To the right boxless
@endwbs
```

### 17.5 Colors (with inline or style color)

It is possible to change node color:
* with inline color

```plantuml {hide=false}
@startwbs
*[#SkyBlue] this is the partner workpackage
**[#pink] this is my workpackage
** this is another workpackage
@endwbs
```

[Ref. QA-12374, only from v1.2020.20]

* with style color

```plantuml {hide=false}
@startwbs
<style>
wbsDiagram {
.pink {
BackgroundColor pink
}
.your_style_name {
BackgroundColor SkyBlue
}
}
</style>
* this is the partner workpackage <<your_style_name>>
** this is my workpackage <<pink>>
** this is another workpackage
@endwbs
```

### 17.6 Using style

It is possible to change diagram style.

```plantuml {hide=false}
@startwbs
<style>
wbsDiagram {
// all lines (meaning connector and borders, there are no other lines in WBS) are black by default
Linecolor black
arrow {
// note that connector are actually "arrow" even if they don't look like as arrow
// This is to be consistent with other UML diagrams. Not 100% sure that it's a good idea
// So now connector are green
LineColor green
}
:depth(0) {
// will target root node
BackgroundColor White
RoundCorner 10
LineColor red
// Because we are targetting depth(0) for everything, border and connector for level 0 will be red
}
arrow {
:depth(2) {
// Targetting only connector between Mexico-Chihuahua and USA-Texas
LineColor blue
LineStyle 4
LineThickness .5
}
}
node {
:depth(2) {
LineStyle 2
LineThickness 2.5
}
}
}
</style>
* World
** America
*** Canada
*** Mexico
**** Chihuahua
*** USA
**** Texas
***< New York
** Europe
*** England
*** Germany
*** Spain
@endwbs
```

### 17.7 Word Wrap

Using MaximumWidth setting you can control automatic word wrap. Unit used is pixel.

```plantuml {hide=false}
@startwbs
<style>
node {
Padding 12
Margin 3
HorizontalAlignment center
LineColor blue
LineThickness 3.0
BackgroundColor gold
RoundCorner 40
MaximumWidth 100
}
rootNode {
LineStyle 8.0;3.0
LineColor red
BackgroundColor white
LineThickness 1.0
RoundCorner 0
Shadowing 0.0
}
leafNode {
LineColor gold
RoundCorner 0
Padding 3
}
arrow {
LineStyle 4
LineThickness 0.5
LineColor green
}
</style>
* Hi =)
** sometimes i have node in wich i want to write a long text
*** this results in really huge diagram
**** of course, i can explicit split with a\nnew line
**** but it could be cool if PlantUML was able to split long lines, maybe with an option who specify the ma
@endwbs
```
