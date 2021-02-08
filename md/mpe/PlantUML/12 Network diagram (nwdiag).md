## 12 Network diagram (nwdiag)

nwdiag has been created by Takeshi Komiya and allows to quickly draw network diagrams. So we thank him for his creation!

Since the syntax is clear and simple, this has been integrated within PlantUML. We reuse here the examples that Takeshi has documented.

### 12.1 Simple diagram

``` puml {hide=false}
@startuml
nwdiag {
network dmz {
address = "210.x.x.x/24"
web01 [address = "210.x.x.1"];
web02 [address = "210.x.x.2"];
}
network internal {
address = "172.x.x.x/24";
web01 [address = "172.x.x.1"];
web02 [address = "172.x.x.2"];
db01;
db02;
}
}
@enduml
```

### 12.2 Define multiple addresses

``` puml {hide=false}
@startuml
nwdiag {
network dmz {
address = "210.x.x.x/24"
// set multiple addresses (using comma)
web01 [address = "210.x.x.1, 210.x.x.20"];
web02 [address = "210.x.x.2"];
}
network internal {
address = "172.x.x.x/24";
web01 [address = "172.x.x.1"];
web02 [address = "172.x.x.2"];
db01;
db02;
}
}
@enduml
```

### 12.3 Grouping nodes

``` puml {hide=false}
@startuml
nwdiag {
network Sample_front {
address = "192.168.10.0/24";
// define group
group web {
web01 [address = ".1"];
web02 [address = ".2"];
}
}
network Sample_back {
address = "192.168.20.0/24";
web01 [address = ".1"];
web02 [address = ".2"];
db01 [address = ".101"];
db02 [address = ".102"];
// define network using defined nodes
group db {
db01;
db02;
}
}
}
@enduml
```

``` puml {hide=false}
@startuml
nwdiag {
// define group at outside network definitions
group {
color = "#FF7777";
web01;
web02;
db01;
}
network dmz {
web01;
web02;
}
network internal {
web01;
web02;
db01;
}
}
@enduml
```

### 12.4 Extended Syntax

You can add or change:
* address;
* color;
* description;
* shape.

``` puml {hide=false}
@startuml
nwdiag {
network Sample_front {
address = "192.168.10.0/24"
color = "red"
// define group
group web {
web01 [address = ".1", shape = "node"]
web02 [address = ".2"]
}
}
network Sample_back {
address = "192.168.20.0/24"
web01 [address = ".1"]
web02 [address = ".2"]
db01 [address = ".101", shape = database ]
db02 [address = ".102"]
// define network using defined nodes
group db {
db01;
db02;
}
}
}
@enduml
```

### 12.5 Using Sprite on nwdiag

You can use all the Sprite of all Standard Library or other.

``` puml {hide=false}
@startuml
!include <office/Servers/application_server>
!include <office/Servers/database_server>
nwdiag {
network dmz {
address = "210.x.x.x/24"
// set multiple addresses (using comma)
web01 [address = "210.x.x.1, 210.x.x.20", description = "<$application_server>\n web01"]
web02 [address = "210.x.x.2", description = "<$application_server>\n web02"];
}
network internal {
address = "172.x.x.x/24";
web01 [address = "172.x.x.1"];
web02 [address = "172.x.x.2"];
db01 [address = "172.x.x.100", description = "<$database_server>\n db01"];
db02 [address = "172.x.x.101", description = "<$database_server>\n db02"];
}
}
@enduml
```

[Ref. QA-11862]

### 12.6 Using OpenIconic on nwdiag

You can also use the icons from OpenIconic on the description.

``` puml {hide=false}
@startuml
nwdiag {
network dmz {
address = "210.x.x.x/24"
user [description = "<&person*5>\n user1"];
// set multiple addresses (using comma)
web01 [address = "210.x.x.1, 210.x.x.20", description = "<&cog*4>\nweb01"]
web02 [address = "210.x.x.2", description = "<&cog*4>\nweb02"];
}
network internal {
address = "172.x.x.x/24";
web01 [address = "172.x.x.1"];
web02 [address = "172.x.x.2"];
db01 [address = "172.x.x.100", description = "<&spreadsheet*4>\n db01"];
db02 [address = "172.x.x.101", description = "<&spreadsheet*4>\n db02"];
ptr [address = "172.x.x.110", description = "<&print*4>\n ptr01"];
}
}
@enduml
```

### 12.7 Same nodes on more than two networks

You can use same nodes on different networks (more than two networks); nwdiag use in this case 'jump line' over networks.

``` puml {hide=false}
@startuml
nwdiag {
// define group at outside network definitions
group {
color = "#7777FF";
web01;
web02;
db01;
}
network dmz {
color = "pink"
web01;
web02;
}
network internal {
web01;
web02;
db01 [shape = database ];
}
network internal2 {
color = "LightBlue";
web01;
web02;
db01;
}
}
@enduml
```

### 12.8 Peer networks


``` puml {hide=false}
@startuml
nwdiag {
inet [shape = cloud];
inet -- router;
network {
router;
web01;
web02;
}
}
@enduml
```

### 12.9 Peer networks and group


``` puml {hide=false}
@startuml
nwdiag {
internet [ shape = cloud];
internet -- router;
group {
color = "pink";
app;
db;
}
network proxy {
width = full
router;
app;
}
network default {
width = full
app;
db;
}
}
}
@enduml
```

### 12.10 Add title, header, footer or legend on network diagram


``` puml {hide=false}
@startuml
header some header
footer some footer
title My title
nwdiag {
network inet {
web01 [shape = cloud]
}
}
legend
The legend
end legend
@enduml
```

[Ref. QA-11303]

### 12.11 Change width of the networks


You can change the width of the networks, especially in order to have the same full width for only some or all networks.

Here are some examples, with all the possibilities:
* without

``` puml {hide=false}
@startuml
nwdiag {
network NETWORK_BASE {
dev_A [address = "dev_A" ]
dev_B [address = "dev_B" ]
}
network IntNET1 {
dev_B [address = "dev_B1" ]
dev_M [address = "dev_M1" ]
}
network IntNET2 {
dev_B [address = "dev_B2" ]
dev_M [address = "dev_M2" ]
}
}
@enduml
```

* only the first

``` puml {hide=false}
@startuml
nwdiag {
network NETWORK_BASE {
width = full
dev_A [address = "dev_A" ]
dev_B [address = "dev_B" ]
}
network IntNET1 {
dev_B [address = "dev_B1" ]
dev_M [address = "dev_M1" ]
}
network IntNET2 {
dev_B [address = "dev_B2" ]
dev_M [address = "dev_M2" ]
}
}
@enduml
```

* the first and the second

``` puml {hide=false}
@startuml
nwdiag {
network NETWORK_BASE {
width = full
dev_A [address = "dev_A" ]
dev_B [address = "dev_B" ]
}
network IntNET1 {
width = full
dev_B [address = "dev_B1" ]
dev_M [address = "dev_M1" ]
}
network IntNET2 {
dev_B [address = "dev_B2" ]
dev_M [address = "dev_M2" ]
}
}
@enduml
```

* all the network (with same full width)

``` puml {hide=false}
@startuml
nwdiag {
network NETWORK_BASE {
width = full
dev_A [address = "dev_A" ]
dev_B [address = "dev_B" ]
}
network IntNET1 {
width = full
dev_B [address = "dev_B1" ]
dev_M [address = "dev_M1" ]
}
network IntNET2 {
width = full
dev_B [address = "dev_B2" ]
dev_M [address = "dev_M2" ]
}
}
@enduml
```
