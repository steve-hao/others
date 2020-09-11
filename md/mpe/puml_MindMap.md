# MindMap


MindMap diagram are still in beta: the syntax may change without notice.



## OrgMode syntax!



This syntax is compatible with OrgMode



``` puml {hide=false}
@startmindmap
* Debian
** Ubuntu
*** Linux Mint
*** Kubuntu
*** Lubuntu
*** KDE Neon
** LMDE
** SolydXK
** SteamOS
** Raspbian with a very long name
*** <s>Raspmbc</s> => OSMC
*** <s>Raspyfi</s> => Volumio
@endmindmap
```


## Multilines!



You can use&nbsp;`:`&nbsp;and&nbsp;`;`&nbsp;to have multilines box.


``` puml {hide=false}
@startmindmap
* Class Templates
**:template <typename T>
class cname{
void f1()<U+003B>
...
};
**:other template <typename T>
class cname{
...
};
@endmindmap
```


## Colors!



It is possible to change node&nbsp;[color](https://plantuml.com/en/color).


``` puml {hide=false}
@startmindmap
*[#Orange] Colors
**[#lightgreen] Green
**[#FFBBCC] Rose
**[#lightblue] Blue
@endmindmap
```


## Removing box!


You can remove the box drawing using an underscore.


``` puml {hide=false}
@startmindmap
* root node
** some first level node
***_ second level node
***_ another second level node
***_ foo
***_ bar
***_ foobar
** another first level node
@endmindmap
```


## Arithmetic notation!


You can use the following notation to choose diagram side.



``` puml {hide=false}
@startmindmap
+ OS
++ Ubuntu
+++ Linux Mint
+++ Kubuntu
+++ Lubuntu
+++ KDE Neon
++ LMDE
++ SolydXK
++ SteamOS
++ Raspbian
-- Windows 95
-- Windows 98
-- Windows NT
--- Windows 8
--- Windows 10
@endmindmap
```


## Markdown syntax!



This syntax is compatible with Markdown


``` puml {hide=false}
@startmindmap
* root node
	* some first level node
		* second level node
		* another second level node
	* another first level node
@endmindmap
```


## Changing diagram direction!


It is possible to use both sides of the diagram.


``` puml {hide=false}
@startmindmap
* count
** 100
*** 101
*** 102
** 200

left side

** A
*** AA
*** AB
** B
@endmindmap
```


## Complete example!



``` puml {hide=false}
@startmindmap
caption figure 1
title My super title

* <&flag>Debian
** <&globe>Ubuntu
*** Linux Mint
*** Kubuntu
*** Lubuntu
*** KDE Neon
** <&graph>LMDE
** <&pulse>SolydXK
** <&people>SteamOS
** <&star>Raspbian with a very long name
*** <s>Raspmbc</s> => OSMC
*** <s>Raspyfi</s> => Volumio

header
My super header
endheader

center footer My super footer

legend right
  Short
  legend
endlegend
@endmindmap
```
