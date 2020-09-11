# [Entity Relationship Diagrams](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=entity-relationship-diagrams)

> An entity–relationship model (or ER model) describes interrelated things of interest in a specific domain of knowledge. A basic ER model is composed of entity types (which classify the things of interest) and specifies relationships that can exist between entities (instances of those entity types). Wikipedia.

Note that practitioners of ER modelling almost always refer to&nbsp;_entity types_&nbsp;simply as&nbsp;_entities_. For example the CUSTOMER entity type would be referred to simply as the CUSTOMER entity. This is so common it would be inadvisable to do anything else, but technically an entity is an abstract&nbsp;_instance_&nbsp;of an entity type, and this is what an ER diagram shows - abstract instances, and the relationships between them. This is why entities are always named using singular nouns.

Mermaid can render ER diagrams

``` Mermaid {hide=false}
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```



Entity names are often capitalised, although there is no accepted standard on this, and it is not required in Mermaid.

Relationships between entities are represented by lines with end markers representing cardinality. Mermaid uses the most popular crow's foot notation. The crow's foot intuitively conveys the possibility of many instances of the entity that it connects to.

## [Status](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=status)

ER diagrams are a new feature in Mermaid and are&nbsp;**experimental**. There are likely to be a few bugs and constraints, and enhancements will be made in due course. Currently you can only define entities and relationships, but not attributes.

## [Syntax](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=syntax)

### [Entities and Relationships](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=entities-and-relationships)

Mermaid syntax for ER diagrams is compatible with PlantUML, with an extension to label the relationship. Each statement consists of the following parts, all of which are mandatory:

``` 
<first-entity> <relationship> <second-entity> : <relationship-label>
```

Where:

*  `first-entity`&nbsp;is the name of an entity. Names must begin with an alphabetic character and may also contain digits and hyphens
*  `relationship`&nbsp;describes the way that both entities inter-relate. See below.
*  `second-entity`&nbsp;is the name of the other entity
*  `relationship-label`&nbsp;describes the relationship from the perspective of the first entity.

For example:

``` Mermaid {hide=false}
erDiagram
    PROPERTY ||--|{ ROOM : contains
```

This statement can be read as&nbsp;_a property contains one or more rooms, and a room is part of one and only one property_. You can see that the label here is from the first entity's perspective: a property contains a room, but a room does not contain a property. When considered from the perspective of the second entity, the equivalent label is usually very easy to infer. (Some ER diagrams label relationships from both perspectives, but this is not supported here, and is usually superfluous).

### [Relationship Syntax](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=relationship-syntax)

The&nbsp;`relationship`&nbsp;part of each statement can be broken down into three sub-components:

*  the cardinality of the first entity with respect to the second,
*  whether the relationship confers identity on a 'child' entity
*  the cardinality of the second entity with respect to the first

Cardinality is a property that describes how many elements of another entity can be related to the entity in question. In the above example a&nbsp;`PROPERTY`&nbsp;can have one or more&nbsp;`ROOM`instances associated to it, whereas a&nbsp;`ROOM`&nbsp;can only be associated with one&nbsp;`PROPERTY`. In each cardinality marker there are two characters. The outermost character represents a maximum value, and the innermost character represents a minimum value. The table below summarises possible cardinalities.

| Value (left) | Value (right) | Meaning |
|--------------|---------------|---------|
| `|o` | `o|` | Zero or one |
| `||` | `||` | Exactly one |
| `}o` | `o{` | Zero or more (no upper limit) |
| `}|` | `|{` | One or more (no upper limit) |

### [Identification](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=identification)

Relationships may be classified as either&nbsp;_identifying_&nbsp;or&nbsp;_non-identifying_&nbsp;and these are rendered with either solid or dashed lines respectively. This is relevant when one of the entities in question can not have independent existence without the other. For example a firm that insures people to drive cars might need to store data on&nbsp;`NAMED-DRIVER`s. In modelling this we might start out by observing that a&nbsp;`CAR`&nbsp;can be driven by many&nbsp;`PERSON`&nbsp;instances, and a&nbsp;`PERSON`&nbsp;can drive many&nbsp;`CAR`s - both entities can exist without the other, so this is a non-identifying relationship that we might specify in Mermaid as:&nbsp;`PERSON }|..|{ CAR : "driver"`. Note the two dots in the middle of the relationship that will result in a dashed line being drawn between the two entities. But when this many-to-many relationship is resolved into two one-to-many relationships, we observe that a&nbsp;`NAMED-DRIVER`&nbsp;cannot exist without both a&nbsp;`PERSON`&nbsp;and a&nbsp;`CAR`&nbsp;- the relationships become identifying and would be specified using hyphens, which translate to a solid line:

``` Mermaid {hide=false}
erDiagram
CAR ||--o{ NAMED-DRIVER : allows
    PERSON ||--o{ NAMED-DRIVER : is
```

### [Other Things](https://mermaid-js.github.io/mermaid/#/entityRelationshipDiagram?id=other-things)

*  If you want the relationship label to be more than one word, you must use double quotes around the phrase
*  If you don't want a label at all on a relationship, you must use an empty double-quoted string