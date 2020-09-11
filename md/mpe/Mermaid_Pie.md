# [Pie chart diagrams](https://mermaid-js.github.io/mermaid/#/pie?id=pie-chart-diagrams)


> A pie chart (or a circle chart) is a circular statistical graphic, which is divided into slices to illustrate numerical proportion. In a pie chart, the arc length of each slice (and consequently its central angle and area), is proportional to the quantity it represents. While it is named for its resemblance to a pie which has been sliced, there are variations on the way it can be presented. The earliest known pie chart is generally credited to William Playfair's Statistical Breviary of 1801 -Wikipedia

Mermaid can render Pie Chart diagrams.

``` Mermaid {hide=false}
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```



## [Syntax](https://mermaid-js.github.io/mermaid/#/pie?id=syntax)

Drawing a pie chart is really simple in mermaid.

*  Start with&nbsp;`pie`&nbsp;keyword to begin the diagram
*  Followed by&nbsp;`title`&nbsp;keyword and its value in string to give a title to the pie-chart. This is&nbsp;**_OPTIONAL_**
*  Followed by dataSet
    
    *  `label`&nbsp;for a section in the pie diagram within&nbsp;`" "`&nbsp;quotes.
    *  Followed by&nbsp;`:`&nbsp;semi-colon as separator
    *  Followed by&nbsp;`positive numeric value`&nbsp;(supported upto two decimal places)

[pie] [title] [titlevalue] (OPTIONAL)  
"[datakey1]" : [dataValue1]  
"[datakey2]" : [dataValue2]  
"[datakey3]" : [dataValue3]  
.  
.

## [Example](https://mermaid-js.github.io/mermaid/#/pie?id=example)

``` Mermaid {hide=false}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```