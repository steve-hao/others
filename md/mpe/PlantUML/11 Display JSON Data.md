## 11 Display JSON Data

JSON format is widely used in software.

You can use PlantUML to visualize your data.

To activate this feature, the diagram must:
* begin with @startjson keyword
* end with @endjson keyword.

``` puml {hide=false}
@startjson
{
"fruit":"Apple",
"size":"Large",
"color":"Red"
}
@endjson
```

### 11.1 Complex example

You can use complex JSON structure.

``` puml {hide=false}
@startjson
{
"firstName": "John",
"lastName": "Smith",
"isAlive": true,
"age": 27,
"address": {
"streetAddress": "21 2nd Street",
"city": "New York",
"state": "NY",
"postalCode": "10021-3100"
},
"phoneNumbers": [
{
"type": "home",
"number": "212 555-1234"
},
{
"type": "office",
"number": "646 555-4567"
}
],
"children": [],
"spouse": null
}
@endjson
```

### 11.2 Highlight parts

``` puml {hide=false}
@startjson
#highlight "lastName"
#highlight "address" / "city"
#highlight "phoneNumbers" / "0" / "number"
{
"firstName": "John",
"lastName": "Smith",
"isAlive": true,
"age": 28,
"address": {
"streetAddress": "21 2nd Street",
"city": "New York",
"state": "NY",
"postalCode": "10021-3100"
},
"phoneNumbers": [
{
"type": "home",
"number": "212 555-1234"
},
{
"type": "office",
"number": "646 555-4567"
}
],
"children": [],
"spouse": null
}
@endjson
```

### 11.3 JSON basic element

#### 11.3.1 Synthesis of all JSON basic element

``` puml {hide=false}
@startjson
{
"null": null,
"true": true,
"false": false,
"JSON_Number": [-1, -1.1, "<color:green>TBC"],
"JSON_String": "a\nb\rc\td <color:green>TBC...",
"JSON_Object": {
"{}": {},
"k_int": 123,
"k_str": "abc",
"k_obj": {"k": "v"}
},
"JSON_Array" : [
[],
[true, false],
[-1, 1],
["a", "b", "c"],
["mix", null, true, 1, {"k": "v"}]
]
}
@endjson
```

### 11.4 JSON array or table

#### 11.4.1 Array type

``` puml {hide=false}
@startjson
{
"Numeric": [1, 2, 3],
"String ": ["v1a", "v2b", "v3c"],
"Boolean": [true, false, true]
}
@endjson
```

#### 11.4.2 Minimal array or table

#### 11.4.3 Number array

``` puml {hide=false}
@startjson
[1, 2, 3]
@endjson
```

#### 11.4.4 String array

``` puml {hide=false}
@startjson
["1a", "2b", "3c"]
@endjson
```

#### 11.4.5 Boolean array


``` puml {hide=false}
@startjson
[true, false, true]
@endjson
```

### 11.5 JSON numbers

``` puml {hide=false}
@startjson
{
"DecimalNumber": [-1, 0, 1],
"DecimalNumber . Digits": [-1.1, 0.1, 1.1],
"DecimalNumber ExponentPart": [1E5]
}
@endjson
```

### 11.6 JSON strings

#### 11.6.1 JSON Unicode

On JSON you can use Unicode directly or by using escaped form like .

``` puml {hide=false}
@startjson
{
  "<color:blue><b>code": "<color:blue><b>value",
  "a\\u005Cb":           "a\u005Cb",
  "\\uD83D\\uDE10":      "\uD83D\uDE10",
  "😐":                  "😐"
}
@endjson
```

#### 11.6.2 JSON two-character escape sequence

``` puml {hide=false}
@startjson
{
"**legend**: character name": ["**two-character escape sequence**", "example (beetwen 'a' and 'B')"],
"quotation mark character (U+0022)": ["\\\"", "a\"b"],
"reverse solidus character (U+005C)": ["\\\\", "a\\b"],
"solidus character (U+002F)": ["\\\/", "a\/b"],
"backspace character (U+0008)": ["\\b", "a\bb"],
"form feed character (U+000C)": ["\\f", "a\fb"],
"line feed character (U+000A)": ["\\n", "a\nb"],
"carriage return character (U+000D)": ["\\r", "a\rb"],
"character tabulation character (U+0009)": ["\\t", "a\tb"]
}
@endjson
```

TODO: FIXME FIXME or not ?, on the same item as management in PlantUML ? TODO: FIXME

``` puml {hide=false}
@startjson
[
"\\\\",
"\\n",
"\\r",
"\\t"
]
@endjson
```

### 11.7 Minimal JSON examples

``` puml {hide=false}
@startjson
"Hello world!"
@endjson
```

``` puml {hide=false}
@startjson
42
@endjson
```

``` puml {hide=false}
@startjson
true
@endjson
```

(Examples come from STD 90 - Examples)
