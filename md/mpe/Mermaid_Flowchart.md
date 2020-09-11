# [Flowcharts - Basic Syntax](http://mermaid-js.github.io/mermaid/#/flowchart?id=flowcharts-basic-syntax)


## [Graph](http://mermaid-js.github.io/mermaid/#/flowchart?id=graph)

This statement declares the direction of the Flowchart.

This declares the graph is oriented from top to bottom (`TD`&nbsp;or&nbsp;`TB`).

``` Mermaid {hide=false}
graph TD
    Start --> Stop
```


This declares the graph is oriented from left to right (`LR`).

``` Mermaid {hide=false}
graph LR
    Start --> Stop
```



## [Flowchart Orientation](http://mermaid-js.github.io/mermaid/#/flowchart?id=flowchart-orientation)

Possible FlowChart orientations are:

*  TB - top to bottom
*  TD - top-down/ same as top to bottom
*  BT - bottom to top
*  RL - right to left
*  LR - left to right

## [Flowcharts](http://mermaid-js.github.io/mermaid/#/flowchart?id=flowcharts)

This renders a flowchart that allows for features such as: more arrow types, multi directional arrows, and linking to and from subgraphs.

Apart from the graph type, the syntax is the same. This is currently experimental but when the beta period is over, both the graph and flowchart keywords will render in the new way. This means it is ok to start beta testing flowcharts.

* An important note on Flowchart nodes, do not type the word "end" as a Flowchart node. Capitalize all or any one the letters to keep the flowchart from breaking, i.e, "End" or "END". Or you can apply this [workaround](http://mermaid-js.github.io/mermaid/#/flowchart?id=an-important-note-on-flowchart-nodes-do-not-type-the-word-quotendquot-as-a-flowchart-node-capitalize-all-or-any-one-the-letters-to-keep-the-flowchart-from-breaking-ie-quotendquot-or-quotendquot-or-you-can-apply-this-a-hrefhttpsgithubcommermaid-jsmermaidissues1444issuecomment-639528897-target_blank-relnoopenerworkaround) 

## [Nodes & shapes](http://mermaid-js.github.io/mermaid/#/flowchart?id=nodes-amp-shapes)

### [A node (default)](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-default)

``` Mermaid {hide=false}
graph LR
    id
```

* Note that the id is what is displayed in the box.

### [A node with text](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-with-text)

It is also possible to set text in the box that differs from the id. If this is done several times, it is the last text found for the node that will be used. Also if you define edges for the node later on, you can omit text definitions. The one previously defined will be used when rendering the box.

```  Mermaid {hide=false}
graph LR
    id1[This is the text in the box]
```



## [Node Shapes](http://mermaid-js.github.io/mermaid/#/flowchart?id=node-shapes)

### [A node with round edges](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-with-round-edges)

``` Mermaid {hide=false}
graph LR 
    id1(This is the text in the box)
```



### [A stadium-shaped node](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-stadium-shaped-node)

``` Mermaid {hide=false}
graph LR
    id1([This is the text in the box])
```



### [A node in a subroutine shape](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-in-a-subroutine-shape)

``` Mermaid {hide=false}
graph LR
    id1[[This is the text in the box]]
```



### [A node in a cylindrical shape](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-in-a-cylindrical-shape)

``` Mermaid {hide=false}
graph LR 
    id1[(Database)]
```



### [A node in the form of a circle](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-in-the-form-of-a-circle)

``` Mermaid {hide=false}
graph LR
    id1((This is the text in the circle))
```



### [A node in an asymetric shape](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-in-an-asymetric-shape)

``` Mermaid {hide=false}
graph LR
    id1>This is the text in the box]
```



Currently only the shape above is possible and not its mirror.&nbsp;_This might change with future releases._

### [A node (rhombus)](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-node-rhombus)

``` Mermaid {hide=false}
graph LR
    id1{This is the text in the box}
```



### [A hexagon node](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-hexagon-node)

``` Mermaid {hide=false}
graph LR
    id1{{This is the text in the box}}
```



### [Parallelogram](http://mermaid-js.github.io/mermaid/#/flowchart?id=parallelogram)

``` Mermaid {hide=false}
graph TD
    id1[/This is the text in the box/]
```



### [Parallelogram alt](http://mermaid-js.github.io/mermaid/#/flowchart?id=parallelogram-alt)

``` Mermaid {hide=false}
graph TD
    id1[\This is the text in the box\]
```



### [Trapezoid](http://mermaid-js.github.io/mermaid/#/flowchart?id=trapezoid)

```  Mermaid {hide=false}
graph TD
    A[/Christmas\]
```



### [Trapezoid alt](http://mermaid-js.github.io/mermaid/#/flowchart?id=trapezoid-alt)

``` Mermaid {hide=false}
graph TD
    B[\Go shopping/]
```



## [Links between nodes](http://mermaid-js.github.io/mermaid/#/flowchart?id=links-between-nodes)

Nodes can be connected with links/edges. It is possible to have different types of links or attach a text string to a link.

### [A link with arrow head](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-link-with-arrow-head)

``` Mermaid {hide=false}
graph LR
    A-->B
```



### [An open link](http://mermaid-js.github.io/mermaid/#/flowchart?id=an-open-link)

``` Mermaid {hide=false}
graph LR
    A --- B
```



### [Text on links](http://mermaid-js.github.io/mermaid/#/flowchart?id=text-on-links)

``` Mermaid {hide=false}
graph LR
    A-- This is the text! ---B
```



or

``` Mermaid {hide=false}
graph LR
    A---|This is the text|B
```



### [A link with arrow head and text](http://mermaid-js.github.io/mermaid/#/flowchart?id=a-link-with-arrow-head-and-text)

``` Mermaid {hide=false}
graph LR
    A-->|text|B
```



or

``` Mermaid {hide=false}
graph LR
    A-- text -->B
```



### [Dotted link](http://mermaid-js.github.io/mermaid/#/flowchart?id=dotted-link)

``` Mermaid {hide=false}
graph LR;
   A-.->B;
```



### [Dotted link with text](http://mermaid-js.github.io/mermaid/#/flowchart?id=dotted-link-with-text)

``` Mermaid {hide=false}
graph LR
   A-. text .-> B
```



### [Thick link](http://mermaid-js.github.io/mermaid/#/flowchart?id=thick-link)

``` Mermaid {hide=false}
graph LR 
   A ==> B
```



### [Thick link with text](http://mermaid-js.github.io/mermaid/#/flowchart?id=thick-link-with-text)

``` Mermaid {hide=false}
graph LR 
   A == text ==> B
```



### [Chaining of links](http://mermaid-js.github.io/mermaid/#/flowchart?id=chaining-of-links)

It is possible declare many links in the same line as per below:

``` Mermaid {hide=false}
graph LR
   A -- text --> B -- text2 --> C
```



It is also possible to declare multiple nodes links in the same line as per below:

``` Mermaid {hide=false}
graph LR
   a --> b & c--> d
```



You can then describe dependencies in a very expressive way. Like the onliner below:

``` Mermaid {hide=false}
graph TB
    A & B--> C & D
```



If you describe the same diagram using the the basic syntax, it will take four lines. A word of warning, one could go overboard with this making the graph harder to read in markdown form. The Swedish word&nbsp;`lagom`&nbsp;comes to mind. It means, not to much and not to little. This goes for expressive syntaxes as well.

``` Mermaid {hide=false}
graph TB
    A --> C
    A --> D
    B --> C
    B --> D
```

## [Beta: New arrow types](http://mermaid-js.github.io/mermaid/#/flowchart?id=beta-new-arrow-types)

When using flowchart instead of graph there is the are new types of arrows supported as per below:

``` Mermaid {hide=false}
flowchart LR
    A --o B
    B --x C
```



## [Beta: multi directional arrows](http://mermaid-js.github.io/mermaid/#/flowchart?id=beta-multi-directional-arrows)

When using flowchart instead of graph there is the possibility to use multidirectional arrows.

``` Mermaid {hide=false}
flowchart LR
    A o--o B
    B <--> C
    C x--x D
```



## [Special characters that break syntax](http://mermaid-js.github.io/mermaid/#/flowchart?id=special-characters-that-break-syntax)

It is possible to put text within quotes in order to render more troublesome characters. As in the example below:

``` Mermaid {hide=false}
graph LR
    id1["This is the (text) in the box"]
```



### [Entity codes to escape characters](http://mermaid-js.github.io/mermaid/#/flowchart?id=entity-codes-to-escape-characters)

It is possible to escape characters using the syntax examplified here.

``` Mermaid {hide=false}
graph LR
        A["A double quote:#quot;"] -->B["A dec char:#9829;"]
```



## [Subgraphs](http://mermaid-js.github.io/mermaid/#/flowchart?id=subgraphs)

``` 
subgraph title
    graph definition
end
```

An example below:

``` Mermaid {hide=false}
graph TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```



You can also set an excplicit id for the subgraph.

``` Mermaid {hide=false}
graph TB
    c1-->a2
    subgraph ide1 [one]
    a1-->a2
    end
```



## [Beta: flowcharts](http://mermaid-js.github.io/mermaid/#/flowchart?id=beta-flowcharts)

With the graphtype flowcharts it is also possible to set edges to and from subgraphs as in the graph below.

``` Mermaid {hide=false}
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
    one --> two
    three --> two
    two --> c2
```



## [Interaction](http://mermaid-js.github.io/mermaid/#/flowchart?id=interaction)

It is possible to bind a click event to a node, the click can lead to either a javascript callback or to a link which will be opened in a new browser tab.&nbsp;**Note**: This functionality is disabled when using&nbsp;`securityLevel='strict'`&nbsp;and enabled when using&nbsp;`securityLevel='loose'`.

``` 
click nodeId callback
```

*  nodeId is the id of the node
*  callback is the name of a javascript function defined on the page displaying the graph, the function will be called with the nodeId as parameter.

Examples of tooltip usage below:

``` 
<script>
  var callback = function(){
      alert('A callback was triggered');
  }
</script>
```

``` Mermaid {hide=false}
graph LR;
    A-->B;
    click A callback "Tooltip for a callback"
    click B "http://www.github.com" "This is a tooltip for a link"
```

The tooltip text is surrounded in double quotes. The styles of the tooltip are set by the class .mermaidTooltip.



> **Success**&nbsp;The tooltip functionality and the ability to link to urls are available from version 0.5.2.

Due to limitations with how Docsify handles JavaScript callback functions, an alternate working demo for the above code can be viewed at&nbsp;[this jsfiddle](https://jsfiddle.net/s37cjoau/3/).

Beginners tip, a full example using interactive links in a html context:

```
<body>
  <div class="mermaid">
    graph LR;
        A-->B;
        click A callback "Tooltip"
        click B "http://www.github.com" "This is a link"
  </div>

  <script>
    var callback = function(){
        alert('A callback was triggered');
    }
    var config = {
        startOnLoad:true,
        flowchart:{
            useMaxWidth:true,
            htmlLabels:true,
            curve:'cardinal',
        },
        securityLevel:'loose',
    };

    mermaid.initialize(config);
  </script>
</body>
```

### [Comments](http://mermaid-js.github.io/mermaid/#/flowchart?id=comments)

Comments can be entered within a flow diagram, which will be ignored by the parser. Comments need to be on their own line, and must be prefaced with&nbsp;`%%`&nbsp;(double percent signs). Any text after the start of the comment to the next newline will be treated as a comment, including any flow syntax

``` Mermaid {hide=false}
graph LR
%% this is a comment A -- text --> B{node}
   A -- text --> B -- text2 --> C
```

## [Styling and classes](http://mermaid-js.github.io/mermaid/#/flowchart?id=styling-and-classes)

### [Styling links](http://mermaid-js.github.io/mermaid/#/flowchart?id=styling-links)

It is possible to style links. For instance you might want to style a link that is going backwards in the flow. As links have no ids in the same way as nodes, some other way of deciding what style the links should be attached to is required. Instead of ids, the order number of when the link was defined in the graph is used. In the example below the style defined in the linkStyle statement will belong to the fourth link in the graph:

``` 
linkStyle 3 stroke:#ff3,stroke-width:4px,color:red;
```

### [Styling a node](http://mermaid-js.github.io/mermaid/#/flowchart?id=styling-a-node)

It is possible to apply specific styles such as a thicker border or a different background color to a node.

``` Mermaid {hide=false}
graph LR
    id1(Start)-->id2(Stop)
    style id1 fill:#f9f,stroke:#333,stroke-width:4px
    style id2 fill:#bbf,stroke:#f66,stroke-width:2px,color:#fff,stroke-dasharray: 5, 5
```



#### [Classes](http://mermaid-js.github.io/mermaid/#/flowchart?id=classes)

More convenient then defining the style every time is to define a class of styles and attach this class to the nodes that should have a different look.

a class definition looks like the example below:

``` 
classDef className fill:#f9f,stroke:#333,stroke-width:4px;
```

Attachment of a class to a node is done as per below:

``` 
class nodeId1 className;
```

It is also possible to attach a class to a list of nodes in one statement:

``` 
class nodeId1,nodeId2 className;
```

A shorter form of adding a class is to attach the classname to the node using the&nbsp;`:::`operator as per below:

``` Mermaid {hide=false}
graph LR
    A:::someclass --> B
    classDef someclass fill:#f96;
```



### [Css classes](http://mermaid-js.github.io/mermaid/#/flowchart?id=css-classes)

It is also possible to predefine classes in css styles that can be applied from the graph definition as in the example below:

**Example style**

``` 
<style>
    .cssClass > rect{
        fill:#FF0000;
        stroke:#FFFF00;
        stroke-width:4px;
    }
</style>
```

**Example definition**

``` 
graph LR;
    A-->B[AAA<span>BBB</span>];
    B-->D;
    class A cssClass;
```



### [Default class](http://mermaid-js.github.io/mermaid/#/flowchart?id=default-class)

If a class is named default it will be assigned to all classes without specific class definitions.

``` 
classDef default fill:#f9f,stroke:#333,stroke-width:4px;
```

## [Basic support for fontawesome](http://mermaid-js.github.io/mermaid/#/flowchart?id=basic-support-for-fontawesome)

It is possible to add icons from fontawesome.

The icons are acessed via the syntax fa:#icon class name#.

``` Mermaid {hide=false}
graph TD
    B["fa:fa-twitter for peace"]
    B-->C[fa:fa-ban forbidden]
    B-->D(fa:fa-spinner);
    B-->E(A fa:fa-camera-retro perhaps?);
```



## [Graph declarations with spaces between vertices and link and without semicolon](http://mermaid-js.github.io/mermaid/#/flowchart?id=graph-declarations-with-spaces-between-vertices-and-link-and-without-semicolon)

*  In graph declarations, the statements also can now end without a semicolon. After release 0.2.16, ending a graph statement with semicolon is just optional. So the below graph declaration is also valid along with the old declarations of the graph.
*  A single space is allowed between vertices and the link. However there should not be any space between a vertex and its text and a link and its text. The old syntax of graph declaration will also work and hence this new feature is optional and is introduce to improve readability.

Below is the new declaration of the graph edges which is also valid along with the old declaration of the graph edges.

``` Mermaid {hide=false}
graph LR
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```



## [Configuration...](http://mermaid-js.github.io/mermaid/#/flowchart?id=configuration)

Is it possible to adjust the width of the rendered flowchart.

This is done by defining&nbsp;**mermaid.flowchartConfig**&nbsp;or by the CLI to use a json file with the configuration. How to use the CLI is described in the mermaidCLI page. mermaid.flowchartConfig can be set to a JSON string with config parameters or the corresponding object.

``` 
mermaid.flowchartConfig = {
    width: 100%
}
```