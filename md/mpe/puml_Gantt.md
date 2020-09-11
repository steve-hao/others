# Gantt Diagram

This is only a proposal and subject to change.


You are very welcome&nbsp;[to create a new discussion](http://forum.plantuml.net/)&nbsp;on this future syntax. Your feedbacks, ideas and suggestions help us to find the right solution.

The Gantt is described in&nbsp;_natural_&nbsp;language, using very simple sentences (subject-verb-complement).

## Declaring tasks!

Tasks defined using square bracket.

### Duration

Their durations are defined using the&nbsp;`last`&nbsp;verb:


``` puml {hide=false}
@startgantt
[Prototype design] lasts 15 days
[Test prototype] lasts 10 days
@endgantt
```


### Start


Their beginning are defined using the&nbsp;`start`&nbsp;verb:



``` puml {hide=false}
@startgantt
[Design du prototype] lasts 15 days
[Test du prototype] lasts 10 days

Project starts 2020-07-01
[Design du prototype] starts 2020-07-01
[Test du prototype] starts 2020-07-16
@endgantt
```


### End


Their ending are defined using the&nbsp;`end`&nbsp;verb:



``` puml {hide=false}
@startgantt
[Design du prototype] lasts 15 days
[Test du prototype] lasts 10 days

Project starts 2020-07-01
[Design du prototype] ends 2020-07-15
[Test du prototype] ends 2020-07-25

@endgantt
```


### Start/End


It is possible to define both absolutely, by specifying dates:


``` puml {hide=false}
@startgantt

Project starts 2020-07-01
[Design du prototype] starts 2020-07-01
[Test du prototype] starts 2020-07-16
[Design du prototype] ends 2020-07-15
[Test du prototype] ends 2020-07-25

@endgantt
```


## One-line declaration (with the and conjunction)!


It is possible to combine declaration on one line with the&nbsp;`and`&nbsp;conjunction.


``` puml {hide=false}
@startgantt
Project starts 2020-07-01
[Design du prototype] starts 2020-07-01 and ends 2020-07-15
[Test du prototype] starts 2020-07-16 and lasts 10 days
@endgantt
```


## Adding constraints!

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



## Short names!

It is possible to define short name for tasks with the&nbsp;`as`&nbsp;keyword.


``` puml {hide=false}
@startgantt
[Prototype design] as [D] lasts 15 days
[Test prototype] as [T] lasts 10 days
[T] starts at [D]'s end
@endgantt
```
