## [Directives](https://mermaid-js.github.io/mermaid/#/directives?id=directives)

**Edit this Page**&nbsp;[![N|Solid](https://mermaid-js.github.io/mermaid/img/GitHub-Mark-32px.png " ")](https://mermaid-js.github.io/mermaid/#/./directives)

### [Directives were added in](https://mermaid-js.github.io/mermaid/#/directives?id=directives-were-added-in-a-href860_docs-version-860)[Version 8.6.0](https://mermaid-js.github.io/mermaid/#/8.6.0_docs)

#### [Init directives](https://mermaid-js.github.io/mermaid/#/directives?id=init-directives)

With this version, directives are supported. Technically there are two flavors of directive: init/initialize and everything else. The init/initialize directive is parsed early in the flow enough to be able to re-initialize mermaid with a new configuration object. Example:

``` Mermaid {hide=false}
%%{init: { 'logLevel': 'debug', 'theme': 'dark' } }%%
graph >
A-->B
```

will set the&nbsp;`logLevel`&nbsp;to&nbsp;`debug`&nbsp;and the&nbsp;`theme`&nbsp;to&nbsp;`dark`&nbsp;for a flowchart diagram.

Note: init or initialize are both acceptable as init directives. Also note that init directives are coalesced. This means:

``` 
%%{init: { 'logLevel': 'debug', 'theme': 'forest' } }%%
%%{initialize: { 'logLevel': 'fatal', "theme":'dark', 'startOnLoad': true } }%%
...
```

will result an init object looking like this:

``` 
{
  logLevel: 'fatal',
  theme: 'dark',
  startOnLoad: true
}
```

to be sent to&nbsp;`mermaid.initialize(...)`

#### [Other directives](https://mermaid-js.github.io/mermaid/#/directives?id=other-directives)

The other flavor of directive is everything else. In this category are any directives that follow the graph type declaration. Essentially, these directives will not be processed early in the flow like the init directive. Each individual graph type will handle these directives. As an example:

``` Mermaid {hide=false}
%%{init: { 'logLevel': 'debug', 'theme': 'dark' } }%%
sequenceDiagram
%%{config: { 'fontFamily': 'Menlo', 'fontSize': 44, 'fontWeight': 400} }%%
Alice->>Bob: Hi Bob
Bob->>Alice: Hi Alice
```

This will set the&nbsp;`logLevel`&nbsp;to&nbsp;`debug`&nbsp;and&nbsp;`theme`&nbsp;to&nbsp;`dark`&nbsp;for a sequence diagram. Then, during processing, the config for the sequence diagram is set by the&nbsp;`config`&nbsp;directive. This directive is handled in the&nbsp;`sequenceDb.js`. In this example, the fontFamily, fontSize, and fontWeight are all set for this sequence diagram.

#### [Backwards Compatibility](https://mermaid-js.github.io/mermaid/#/directives?id=backwards-compatibility)

Init directives and any other non-multiline directives should be backwards compatible because they will be treated as comments in prior versions of mermaid-js.

Multiline directives, however, will pose an issue and will render an error. This is unavoidable.

### [Wrapping](https://mermaid-js.github.io/mermaid/#/directives?id=wrapping)

The&nbsp;`%%{wrap}%%`&nbsp;directive and the inline&nbsp;`wrap:`&nbsp;text hint have also been added for sequence diagrams. This has been explained in my previous comments and has not materially changed.