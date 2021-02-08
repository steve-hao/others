## 26 Standard Library
This page explains the official Standard Library for PlantUML This Standard Library is now included in official releases of PlantUML. Including files follows the C convention for "C standard library" (see https://en.wikipedia.org/wiki/C_standard_library )

Contents of the library come from third party contributors. We thank them for their useful contribution!

### 26.1 Amazon Labs Library

https://github.com/awslabs/aws-icons-for-plantuml

The Amazon Labs AWS library provides PlantUML sprites, macros, and other includes for Amazon Web Services (AWS) services and resources.

Used to create PlantUML diagrams with AWS components. All elements are generated from the official AWS Architecture Icons and when combined with PlantUML and the C4 model, are a great way to communicate your design, deployment, and topology as code.

``` puml {hide=false}
@startuml
'Copyright 2019 Amazon.com, Inc. or its affiliates. All Rights Reserved.
'SPDX-License-Identifier: MIT (For details, see https://github.com/awslabs/aws-icons-for-plantuml/blob
!include <awslib/AWSCommon>
' Uncomment the following line to create simplified view
' !include <awslib/AWSSimplified>
!include <awslib/General/Users>
!include <awslib/Mobile/APIGateway>
!include <awslib/SecurityIdentityAndCompliance/Cognito>
!include <awslib/Compute/Lambda>
!include <awslib/Database/DynamoDB>
left to right direction
Users(sources, "Events", "millions of users")
APIGateway(votingAPI, "Voting API", "user votes")
Cognito(userAuth, "User Authentication", "jwt to submit votes")
Lambda(generateToken, "User Credentials", "return jwt")
Lambda(recordVote, "Record Vote", "enter or update vote per user")
DynamoDB(voteDb, "Vote Database", "one entry per user")
sources --> userAuth
sources --> votingAPI
userAuth <--> generateToken
votingAPI --> recordVote
recordVote --> voteDb
@enduml
```

### 26.2 AWS library

https://github.com/milo-minderbinder/AWS-PlantUML

The AWS library consists of Amazon AWS icons, it provides icons of two different sizes.

Use it by including the file that contains the sprite, eg: !include <aws/Storage/AmazonS3/AmazonS3>. When imported, you can use the sprite as normally you would, using <$sprite_name>.

You may also include the common.pumlfile, eg: !include <aws/common>, which contains helper macros defined. With the common.puml imported, you can use the NAME_OF_SPRITE(parameters...) macro.

Example of usage:

``` puml {hide=false}
@startuml
!include <aws/common>
!include <aws/Storage/AmazonS3/AmazonS3>
!include <aws/Storage/AmazonS3/bucket/bucket>
AMAZONS3(s3_internal)
AMAZONS3(s3_partner,"Vendor's S3")
s3_internal <- s3_partner
@enduml
```


### 26.3 Azure library


https://github.com/RicardoNiepel/Azure-PlantUML/

The Azure library consists of Microsoft Azure icons.

Use it by including the file that contains the sprite, eg: !include <azure/Analytics/AzureEventHub.puml>. When imported, you can use the sprite as normally you would, using <$sprite_name>.

You may also include the AzureCommon.puml file, eg: !include <azure/AzureCommon.puml>, which contains helper macros defined. With the AzureCommon.puml imported, you can use the NAME_OF_SPRITE(parameters...) macro.

Example of usage:

``` puml {hide=false}
@startuml
!include <azure/AzureCommon.puml>
!include <azure/Analytics/AzureEventHub.puml>
!include <azure/Analytics/AzureStreamAnalytics.puml>
!include <azure/Databases/AzureCosmosDb.puml>
left to right direction
agent "Device Simulator" as devices #fff
AzureEventHub(fareDataEventHub, "Fare Data", "PK: Medallion HackLicense VendorId; 3 TUs")
AzureEventHub(tripDataEventHub, "Trip Data", "PK: Medallion HackLicense VendorId; 3 TUs")
AzureStreamAnalytics(streamAnalytics, "Stream Processing", "6 SUs")
AzureCosmosDb(outputCosmosDb, "Output Database", "1,000 RUs")
devices --> fareDataEventHub
devices --> tripDataEventHub
fareDataEventHub --> streamAnalytics
tripDataEventHub --> streamAnalytics
streamAnalytics --> outputCosmosDb
@enduml
```

### 26.4 Cloud Insight


https://github.com/rabelenda/cicon-plantuml-sprites

This repository contains PlantUML sprites generated from Cloudinsight icons, which can easily be used in PlantUML diagrams for nice visual representation of popular technologies.

``` puml {hide=false}
@startuml
!include <cloudinsight/tomcat>
!include <cloudinsight/kafka>
!include <cloudinsight/java>
!include <cloudinsight/cassandra>
title Cloudinsight sprites example
skinparam monochrome true
rectangle "<$tomcat>\nwebapp" as webapp
queue "<$kafka>" as kafka
rectangle "<$java>\ndaemon" as daemon
database "<$cassandra>" as cassandra
webapp -> kafka
kafka -> daemon
daemon --> cassandra
@enduml
```

### 26.5 Elastic library


The Elastic library consists of Elastic icons. It is similar in use to the AWS and Azure libraries (it used the same tool to create them).

Use it by including the file that contains the sprite, eg: !include elastic/elastic_search/elastic_search.puml>. When imported, you can use the sprite as normally you would, using <$sprite_name>.

You may also include the common.puml file, eg: !include <elastic/common>, which contains helper macros defined. With the common.puml imported, you can use the NAME//OF//SPRITE(parameters...) macro.

Example of usage:

``` puml {hide=false}
@startuml
!include <elastic/common>
!include <elastic/elasticsearch/elasticsearch>
!include <elastic/logstash/logstash>
!include <elastic/kibana/kibana>
ELASTICSEARCH(ElasticSearch, "Search and Analyze",database)
LOGSTASH(Logstash, "Parse and Transform",node)
KIBANA(Kibana, "Visualize",agent)
Logstash -right-> ElasticSearch: Transformed Data
ElasticSearch -right-> Kibana: Data to View
@enduml
```

### 26.6 Tupadr3 library

https://github.com/tupadr3/plantuml-icon-font-sprites

This library contains several libraries of icons (including Devicons and Font Awesome).

Use it by including the file that contains the sprite, eg: !include <font-awesome/align_center>. When imported, you can use the sprite as normally you would, using <$sprite_name>.

You may also include the common.puml file, eg: !include <font-awesome/common>, which contains helper macros defined. With the common.puml imported, you can use the NAME_OF_SPRITE(parameters...) macro.

Example of usage:

``` puml {hide=false}
@startuml
!include <tupadr3/common>
!include <tupadr3/font-awesome/server>
!include <tupadr3/font-awesome/database>
title Styling example
FA_SERVER(web1,web1) #Green
FA_SERVER(web2,web2) #Yellow
FA_SERVER(web3,web3) #Blue
FA_SERVER(web4,web4) #YellowGreen
FA_DATABASE(db1,LIVE,database,white) #RoyalBlue
FA_DATABASE(db2,SPARE,database) #Red
db1 <--> db2
web1 <--> db1
web2 <--> db1
web3 <--> db1
web4 <--> db1
@enduml
```

``` puml {hide=false}
@startuml
!include <tupadr3/common>
!include <tupadr3/devicons/mysql>
DEV_MYSQL(db1)
DEV_MYSQL(db2,label of db2)
DEV_MYSQL(db3,label of db3,database)
DEV_MYSQL(db4,label of db4,database,red) #DeepSkyBlue
@enduml
```

### 26.7 Google Material Icons


https://github.com/Templarian/MaterialDesign

This library consists of a free Material style icons from Google and other artists.

Use it by including the file that contains the sprite, eg: !include <material/ma_folder_move>. When imported, you can use the sprite as normally you would, using <$ma_sprite_name>. Notice that this library requires an ma_ prefix on sprites names, this is to avoid clash of names if multiple sprites have the same name on different libraries.

You may also include the common.puml file, eg: !include <material/common>, which contains helper macros defined. With the common.puml imported, you can use the MA_NAME_OF_SPRITE(parameters...) macro, note again the use of the prefix MA_.

Example of usage:

``` puml {hide=false}
@startuml
!include <material/common>
' To import the sprite file you DON'T need to place a prefix!
!include <material/folder_move>
MA_FOLDER_MOVE(Red, 1, dir, rectangle, "A label")
@enduml
```

Notes

When mixing sprites macros with other elements you may get a syntax error if, for example, trying to add a rectangle along with classes. In those cases, add { and } after the macro to create the empty rectangle.

Example of usage:

``` puml {hide=false}
@startuml
!include <material/common>
' To import the sprite file you DON'T need to place a prefix!
!include <material/folder_move>
MA_FOLDER_MOVE(Red, 1, dir, rectangle, "A label") {
}
class foo {
bar
}
@enduml
```

### 26.8 Office

https://github.com/Roemer/plantuml-office

There are sprites (*.puml) and colored png icons available. Be aware that the sprites are all only monochrome even if they have a color in their name (due to automatically generating the files). You can either color the sprites with the macro (see examples below) or directly use the fully colored pngs. See the following examples on how to use the sprites, the pngs and the macros.

Example of usage:

``` puml {hide=false}
@startuml
!include <tupadr3/common>
!include <office/Servers/database_server>
!include <office/Servers/application_server>
!include <office/Concepts/firewall_orange>
!include <office/Clouds/cloud_disaster_red>
title Office Icons Example
package "Sprites" {
OFF_DATABASE_SERVER(db,DB)
OFF_APPLICATION_SERVER(app,App-Server)
OFF_FIREWALL_ORANGE(fw,Firewall)
OFF_CLOUD_DISASTER_RED(cloud,Cloud)
db <-> app
app <--> fw
fw <.left.> cloud
}
@enduml
```

``` puml {hide=false}
@startuml
!include <tupadr3/common>
!include <office/servers/database_server>
!include <office/servers/application_server>
!include <office/Concepts/firewall_orange>
!include <office/Clouds/cloud_disaster_red>
' Used to center the label under the images
skinparam defaultTextAlignment center
title Extended Office Icons Example
package "Use sprite directly" {
[Some <$cloud_disaster_red> object]
}
package "Different macro usages" {
OFF_CLOUD_DISASTER_RED(cloud1)
OFF_CLOUD_DISASTER_RED(cloud2,Default with text)
OFF_CLOUD_DISASTER_RED(cloud3,Other shape,Folder)
OFF_CLOUD_DISASTER_RED(cloud4,Even another shape,Database)
OFF_CLOUD_DISASTER_RED(cloud5,Colored,Rectangle, red)
OFF_CLOUD_DISASTER_RED(cloud6,Colored background) #red
}
@enduml
```

### 26.9 ArchiMate


https://github.com/ebbypeter/Archimate-PlantUML

This repository contains ArchiMate PlantUML macros and other includes for creating Archimate Diagrams easily and consistantly.

``` puml {hide=false}
@startuml
!include <archimate/Archimate>
title Archimate Sample - Internet Browser
' Elements
Business_Object(businessObject, "A Business Object")
Business_Process(someBusinessProcess,"Some Business Process")
Business_Service(itSupportService, "IT Support for Business (Application Service)")
Application_DataObject(dataObject, "Web Page Data \n 'on the fly'")
Application_Function(webpageBehaviour, "Web page behaviour")
Application_Component(ActivePartWebPage, "Active Part of the web page \n 'on the fly'")
Technology_Artifact(inMemoryItem,"in memory / 'on the fly' html/javascript")
Technology_Service(internetBrowser, "Internet Browser Generic & Plugin")
Technology_Service(internetBrowserPlugin, "Some Internet Browser Plugin")
Technology_Service(webServer, "Some web server")
'Relationships
Rel_Flow_Left(someBusinessProcess, businessObject, "")
Rel_Serving_Up(itSupportService, someBusinessProcess, "")
Rel_Specialization_Up(webpageBehaviour, itSupportService, "")
Rel_Flow_Right(dataObject, webpageBehaviour, "")
Rel_Specialization_Up(dataObject, businessObject, "")
Rel_Assignment_Left(ActivePartWebPage, webpageBehaviour, "")
Rel_Specialization_Up(inMemoryItem, dataObject, "")
Rel_Realization_Up(inMemoryItem, ActivePartWebPage, "")
Rel_Specialization_Right(inMemoryItem,internetBrowser, "")
Rel_Serving_Up(internetBrowser, webpageBehaviour, "")
Rel_Serving_Up(internetBrowserPlugin, webpageBehaviour, "")
Rel_Aggregation_Right(internetBrowser, internetBrowserPlugin, "")
Rel_Access_Up(webServer, inMemoryItem, "")
Rel_Serving_Up(webServer, internetBrowser, "")
@enduml
```

### 26.10 Kubernetes


https://github.com/michiel/plantuml-kubernetes-sprites

``` puml {hide=false}
@startuml
!include <kubernetes/k8s-sprites-unlabeled-25pct>
package "Infrastructure" {
component "<$master>\nmaster" as master
component "<$etcd>\netcd" as etcd
component "<$node>\nnode" as node
}
@enduml
```

### 26.11 Miscellaneous


You can list standard library folders using the special diagram:

``` puml {hide=false}
@startuml
stdlib
@enduml
```

It is also possible to use the command line java -jar plantuml.jar -stdlib to display the same list.

Finally, you can extract the full standard library sources using java -jar plantuml.jar -extractstdlib.

All files will be extracted in the folder stdlib.

Sources used to build official PlantUML releases are hosted here https://github.com/plantuml/plantuml-stdlib. You can create Pull Request to update or add some library if you find it relevant.
