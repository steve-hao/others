# Maths

*  [Standalone diagram](https://plantuml.com/en/ascii-math#40d03d9ecc034ee6)
*  [How is this working ?](https://plantuml.com/en/ascii-math#1372f849f88d74e1)



You can use&nbsp;[AsciiMath](http://asciimath.org/)&nbsp;or&nbsp;[JLaTeXMath](https://github.com/opencollab/jlatexmath)&nbsp;notation within PlantUML:


```  {hide=false}
@startuml
:<math>int_0^1f(x)dx</math>;
:<math>x^2+y_1+z_12^34</math>;
note right
Try also
<math>d/dxf(x)=lim_(h->0)(f(x+h)-f(x))/h</math>
<latex>P(y|\mathbf{x}) \mbox{ or } f(\mathbf{x})+\epsilon</latex>
end note
@enduml
```

![](https://s.plantuml.com/imgw/img-9452af977c5269311e9d62e89ff81ce4.webp " ")



or:



```  {hide=false}
@startuml
Bob -> Alice : Can you solve: <math>ax^2+bx+c=0</math>
Alice --> Bob: <math>x = (-b+-sqrt(b^2-4ac))/(2a)</math>
@enduml
```

![](https://s.plantuml.com/imgw/img-cf744d0930a0e3d5bed5e48bde5840cd.webp " ")





## Standalone diagram!



You can also use&nbsp;`@startmath`/`@endmath`&nbsp;to create standalone&nbsp;[AsciiMath](http://asciimath.org/)&nbsp;formula.







```  {hide=false}
@startmath
f(t)=(a_0)/2 + sum_(n=1)^ooa_ncos((npit)/L)+sum_(n=1)^oo b_n\ sin((npit)/L)
@endmath
```

![](https://s.plantuml.com/imgw/img-069852f4939568ffe98ebf557e458e6a.webp " ")







Or use&nbsp;`@startlatex`/`@endlatex`&nbsp;to create standalone&nbsp;[JLaTeXMath](https://github.com/opencollab/jlatexmath)&nbsp;formula.





```   {hide=false}
@startlatex
\sum_{i=0}^{n-1} (a_i + b_i^2)
@endlatex
```

![](https://s.plantuml.com/imgw/img-46fa917770517a9aa18ac578748b44b3.webp " ")



## How is this working ?!

To draw those formulas, PlantUML uses two OpenSource projects:



*  [AsciiMath](https://github.com/asciimath/asciimathml/tree/master/asciimath-based)&nbsp;that converts AsciiMath notation to LaTeX expression.
*  [JLatexMath](https://github.com/opencollab/jlatexmath)&nbsp;that displays mathematical formulas written in LaTeX. JLaTeXMath is the best Java library to display LaTeX code.



[ASCIIMathTeXImg.js](https://github.com/asciimath/asciimathml/blob/master/asciimath-based/ASCIIMathTeXImg.js)&nbsp;is small enough to be integrated into PlantUML standard distribution.



Since&nbsp;[JLatexMath](https://github.com/opencollab/jlatexmath)&nbsp;is bigger, you have to&nbsp;[download it](http://beta.plantuml.net/plantuml-jlatexmath.zip)&nbsp;separately, then unzip the 4 jar files (_batik-all-1.7.jar_,&nbsp;_jlatexmath-minimal-1.0.3.jar_,&nbsp;_jlm_cyrillic.jar_&nbsp;and&nbsp;_jlm_greek.jar_) in the same folder as PlantUML.jar.