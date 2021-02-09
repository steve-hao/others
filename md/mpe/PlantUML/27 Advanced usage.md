
Advanced usage
### Have a break: resolve a Sudoku.

Sometimes, when modeling, it's good to have a break....

You can use PlantUML to create Sudoku, like in the following example:

```plantuml {hide=false}
@startuml
sudoku
@enduml
```
The sudoku is randomly generated.

It is also possible to generate a specific Sudoku by providing its seed:

```plantuml
@startuml
sudoku 45azkdf4sqq
@enduml
```
