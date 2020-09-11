# 数学

**Markdown Preview Enhanced** 使用 [KaTeX](https://github.com/Khan/KaTeX) 或者 [MathJax](https://github.com/mathjax/MathJax) 来渲染数学表达式。

KaTeX 拥有比 MathJax 更快的性能，但是它却少了很多 MathJax 拥有的特性。你可以查看 [KaTeX supported functions/symbols](https://khan.github.io/KaTeX/function-support.html) 来了解 KaTeX 支持那些符号和函数。

默认下的分隔符：

- `$...$` 或者 `\(...\)` 中的数学表达式将会在行内显示。
- `$$...$$` 或者 `\[...\]` 或者 <code>```math</code> 中的数学表达式将会在块内显示。

![](https://cloud.githubusercontent.com/assets/1908863/14398210/0e408954-fda8-11e5-9eb4-562d7c0ca431.gif)

你可以在 [插件设置中](zh-cn/usages.md?id=package-settings) 选择数学渲染引擎以及分隔符。

你也可以通过 <kbd>cmd-shift-p</kbd> 然后选择 `Markdown Preview Enhanced: Open Mathjax config` 命令来打开 Mathjax 配置文件。

[➔ 图像](zh-cn/diagrams.md)


# KaTex
### Supported FunctionsThis is a list of TeX functions supported by KaTeX. It is sorted into logical groups.

There is a similar&nbsp;[Support Table](https://katex.org/docs/support_table.html), sorted alphabetically, that lists both supported and un-supported functions.



## [](https://katex.org/docs/supported.html#accents)Accents

|   |   |   |
|---|---|---|
| $a'$ `a'` | $\tilde{a}$ `\tilde{a}` | $\mathring{g}$ `\mathring{g}` |
| $a''$ `a''` | $\widetilde{ac}$ `\widetilde{ac}` | $\overgroup{AB}$ `\overgroup{AB}` |
| $a^{\prime}$ `a^{\prime}` | $\utilde{AB}$ `\utilde{AB}` | $\undergroup{AB}$`\undergroup{AB}` |
| $\acute{a}$ `\acute{a}` | $\vec{F}$ `\vec{F}` | $\Overrightarrow{AB}$ `\Overrightarrow{AB}` |
| $\bar{y}$ `\bar{y}` | $\overleftarrow{AB}$ `\overleftarrow{AB}` | $\overrightarrow{AB}$ `\overrightarrow{AB}` |
| $\breve{a}$ `\breve{a}` | $\underleftarrow{AB}$ `\underleftarrow{AB}` | $\underrightarrow{AB}$ `\underrightarrow{AB}` |
| $\check{a}$ `\check{a}` | $\overleftharpoon{ac}$ `\overleftharpoon{ac}` | $\overrightharpoon{ac}$ `\overrightharpoon{ac}` |
| $\dot{a}$ `\dot{a}` | $\overleftrightarrow{AB}$ `\overleftrightarrow{AB}` | $\overbrace{AB}$ `\overbrace{AB}` |
| $\ddot{a}$ `\ddot{a}` | $\underleftrightarrow{AB}$ `\underleftrightarrow{AB}` | $\underbrace{AB}$ `\underbrace{AB}` |
| $\grave{a}$ `\grave{a}` | $\overline{AB}$ `\overline{AB}` | $\overlinesegment{AB}$ `\overlinesegment{AB}` |
| $\hat{\theta}$ `\hat{\theta}` | $\underline{AB}$ `\underline{AB}` | $\underlinesegment{AB}$ `\underlinesegment{AB}` |
| $\widehat{ac}$ `\widehat{ac}` | $\widecheck{ac}$ `\widecheck{ac}` |

**_Accent functions inside \text{…}_**

|   |   |   |   |
|---|---|---|---|
| $\text{\'{a}}$ `\'{a}` | $\text{\~{a}}$ `\~{a}` | $\text{\.{a}}$ `\.{a}` | $\text{\H{a}}$ `\H{a}` |
| $\text{\`{a}}$ ``\`{a}`` | $\text{\={a}}$ `\={a}` | $\text{\"{a}}$ `\"{a}` | $\text{\v{a}}$ `\v{a}` |
| $\text{\^{a}}$ `\^{a}` | $\text{\u{a}}$ `\u{a}` | $\text{\r{a}}$ `\r{a}` |

See also&nbsp;[letters](https://katex.org/docs/supported.html#letters)

## [](https://katex.org/docs/supported.html#delimiters)Delimiters

|   |   |   |   |   |
|---|---|---|---|---|
| $(~)$ &nbsp;`( )` | $\lparen~\rparen$ &nbsp;`\lparen`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rparen` | $⌈~⌉$ &nbsp;`⌈ ⌉` | $\lceil~\rceil$ &nbsp;`\lceil`  <br>$~~~~~$ &nbsp;&nbsp;&nbsp;&nbsp;`\rceil` | $\uparrow$ `\uparrow` |
| $[~]$ &nbsp;`[ ]` | $\lbrack~\rbrack$ &nbsp;`\lbrack`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rbrack` | $⌊~⌋$ &nbsp;`⌊ ⌋` | $\lfloor~\rfloor$ &nbsp;`\lfloor`  <br>$~~~~~$ &nbsp;&nbsp;&nbsp;&nbsp;`\rfloor` | $\downarrow$ `\downarrow` |
| $\{ \}$ `\{ \}` | $\lbrace \rbrace$ `\lbrace`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rbrace` | $⎰⎱$ `⎰⎱` | $\lmoustache \rmoustache$ `\lmoustache`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rmoustache` | $\updownarrow$ `\updownarrow` |
| $⟨~⟩$ &nbsp;`⟨ ⟩` | $\langle~\rangle$ &nbsp;`\langle`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rangle` | $⟮~⟯$ &nbsp;`⟮ ⟯` | $\lgroup~\rgroup$ ⟯&nbsp;`\lgroup`  <br>$~~~~~$ &nbsp;&nbsp;&nbsp;&nbsp;`\rgroup` | $\Uparrow$ `\Uparrow` |
| $\vert$ `|` | $\vert$ `\vert` | $┌ ┐$ `┌ ┐` | $\ulcorner \urcorner$ `\ulcorner`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\urcorner` | $\Downarrow$ `\Downarrow` |
| $\Vert$ `\|` | $\Vert$ `\Vert` | $└ ┘$ `└ ┘` | $\llcorner \lrcorner$ `\llcorner`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\lrcorner` | $\Updownarrow$ `\Updownarrow` |
| $\lvert~\rvert$ &nbsp;`\lvert`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rvert` | $\lVert~\rVert$ &nbsp;`\lVert`  <br>$~~~~~$ &nbsp;&nbsp;&nbsp;&nbsp;`\rVert` | `\left.` | `\right.` | $\backslash$ `\backslash` |
| $\lang~\rang$ &nbsp;`\lang`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rang` | $\lt~\gt$ &nbsp;`\lt \gt` | $⟦~⟧$ &nbsp;`⟦ ⟧` | $\llbracket~\rrbracket$ &nbsp;`\llbracket`  <br>$~~~~$ &nbsp;&nbsp;&nbsp;`\rrbracket` | $\lBrace~\rBrace$ &nbsp;`\lBrace \rBrace` |

**Delimiter Sizing**

$\left(\LARGE{AB}\right)$ `\left(\LARGE{AB}\right)`

$( \big( \Big( \bigg( \Bigg($ `( \big( \Big( \bigg( \Bigg(`

|   |   |   |   |   |
|---|---|---|---|---|
| `\left` | `\big` | `\bigl` | `\bigm` | `\bigr` |
| `\middle` | `\Big` | `\Bigl` | `\Bigm` | `\Bigr` |
| `\right` | `\bigg` | `\biggl` | `\biggm` | `\biggr` |
|   | `\Bigg` | `\Biggl` | `\Biggm` | `\Biggr` |

## [](https://katex.org/docs/supported.html#environments)Environments

|   |   |   |   |
|---|---|---|---|
| $\begin{matrix} a & b \\ c & d \end{matrix}$ |`\begin{matrix}`<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{matrix}` | $\begin{array}{cc}a & b\\c & d\end{array}$ |`\begin{array}{cc}`<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{array}` |
| $\begin{pmatrix} a & b \\ c & d \end{pmatrix}$ |`\begin{pmatrix} `<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{pmatrix}` | $\begin{bmatrix} a & b \\ c & d \end{bmatrix}$ |`\begin{bmatrix} `<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{bmatrix}` |
| $\begin{vmatrix} a & b \\ c & d \end{vmatrix}$ |`\begin{vmatrix} `<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{vmatrix}` | $\begin{Vmatrix} a & b \\ c & d \end{Vmatrix}$ |`\begin{Vmatrix} `<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{Vmatrix}` |
| $\begin{Bmatrix} a & b \\ c & d \end{Bmatrix}$ |`begin{Bmatrix} `<br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{Bmatrix}` | $\def\arraystretch{1.5}\begin{array}{c:c:c} a & b & c \\ \hline d & e & f \\ \hdashline g & h & i \end{array}$ |`\begin{array}{c:c:c}`  <br>&nbsp;&nbsp;&nbsp;`a & b & c \\ \hline`  <br>&nbsp;&nbsp;&nbsp;`d & e & f \\`  <br>&nbsp;&nbsp;&nbsp;`\hdashline`  <br>&nbsp;&nbsp;&nbsp;`g & h & i`  <br>`\end{array}` |
| $\begin{aligned} a&=b+c \\ d+e&=f \end{aligned}$ |`begin{aligned} `<br>`a&=b+c \\`  <br>&nbsp;&nbsp;&nbsp;`d+e&=f`  <br>`\end{aligned}` | $\begin{alignedat}{2}10&x+&3&y=2\\3&x+&13&y=4\end{alignedat}$ |`\begin{alignedat}{2}`<br>`10&x+ &3&y = 2 \\`  <br>&nbsp;&nbsp;&nbsp;`3&x+&13&y = 4`  <br>`\end{alignedat}` |
| $\begin{gathered} a=b \\ e=b+c \end{gathered}$ |`\begin{gathered} `<br>`a=b \\`  <br>&nbsp;&nbsp;&nbsp;`e=b+c`  <br>`\end{gathered}` | $x = \begin{cases} a &\text{if } b \\ c &\text{if } d \end{cases}$ | `x = \begin{cases}`  <br>&nbsp;&nbsp;&nbsp;`a &\text{if } b \\`  <br>&nbsp;&nbsp;&nbsp;`c &\text{if } d`  <br>`\end{cases}` |
| $\begin{smallmatrix} a & b \\ c & d \end{smallmatrix}$ |`\begin{smallmatrix}` <br>`a & b \\`  <br>&nbsp;&nbsp;&nbsp;`c & d`  <br>`\end{smallmatrix}` | $\begin{cases} a &\text{if } b \\ c &\text{if } d \end{cases}⇒…$| `\begin{rcases}`  <br>&nbsp;&nbsp;&nbsp;`a &\text{if } b \\`  <br>&nbsp;&nbsp;&nbsp;`c &\text{if } d`  <br>`\end{rcases}⇒…` |

sim not surply rcases

KaTeX also supports&nbsp;`darray`,&nbsp;`dcases`, and&nbsp;`drcases`.

Acceptable line separators include:&nbsp;`\\`,&nbsp;`\cr`,&nbsp;`\\[distance]`, and&nbsp;`\cr[distance]`.&nbsp;_Distance_&nbsp;can be written with any of the&nbsp;[KaTeX units](https://katex.org/docs/supported.html#units).

The&nbsp;`{array}`&nbsp;environment supports&nbsp;`|`&nbsp;and&nbsp;`:`&nbsp;vertical separators.

The&nbsp;`{array}`&nbsp;environment does not yet support&nbsp;`\cline`&nbsp;or&nbsp;`\multicolumn`.

## [](https://katex.org/docs/supported.html#html)HTML

The following "raw HTML" features are potentially dangerous for untrusted inputs, so they are disabled by default, and attempting to use them produces the command names in red (which you can configure via the&nbsp;`errorColor`&nbsp;[option](https://katex.org/docs/options.html)). To fully trust your LaTeX input, you need to pass an option of&nbsp;`trust: true`; you can also enable just some of the commands or for just some URLs via the&nbsp;`trust`&nbsp;[option](https://katex.org/docs/options.html).

|   |   |
|---|---|
|$\href{https://katex.org/}{\KaTeX}$ | `\href{https://katex.org/}{\KaTeX}` |
|$\url{https://katex.org/}$ | `\url{https://katex.org/}` |
|$\includegraphics[height=0.8em, totalheight=0.9em, width=0.9em, alt=KA logo]{https://katex.org/img/khan-academy.png}$ | `\includegraphics[height=0.8em, totalheight=0.9em, width=0.9em, alt=KA logo]{https://katex.org/img/khan-academy.png}` |
| $\htmlId{bar}{x}$ | `\htmlId{bar}{x}` |
| $\htmlClass{foo}{x}$  | `\htmlClass{foo}{x}` |
| $\htmlStyle{color: red;}{x}$| `\htmlStyle{color: red;}{x}` |
| $\htmlData{foo=a, bar=b}{x}$ | `\htmlData{foo=a, bar=b}{x}` |

`\includegraphics`&nbsp;supports&nbsp;`height`,&nbsp;`width`,&nbsp;`totalheight`, and&nbsp;`alt`&nbsp;in its first argument.&nbsp;`height`&nbsp;is required.

HTML extension (`\html`-prefixed) commands are non-standard, so loosening&nbsp;`strict`&nbsp;option for&nbsp;`htmlExtension`&nbsp;is required.

## [](https://katex.org/docs/supported.html#letters-and-unicode)Letters and Unicode

**Greek Letters**

Direct Input:&nbsp;$Α Β Γ Δ Ε Ζ Η Θ Ι Κ Λ Μ Ν Ξ Ο Π Ρ Σ Τ Υ Φ Χ Ψ Ω α β γ δ ϵ ζ η θ ι κ λ μ ν ξ o π ρ σ τ υ ϕ χ ψ ω ε ϑ ϖ ϱ ς φ ϝ$

|   |   |   |   |
|---|---|---|---|
| $\Alpha$ `\Alpha` | $\Beta$ `\Beta` | $\Gamma$ `\Gamma` | $\Delta$ `\Delta` |
| $\Epsilon$ `\Epsilon` | $\Zeta$ `\Zeta` | $\Eta$ `\Eta` | $\Theta$ `\Theta` |
| $\Iota$ `\Iota` | $\Kappa$ `\Kappa` | $\Lambda$ `\Lambda` | $\Mu$ `\Mu` |
| $\Nu$ `\Nu` | $\Xi$ `\Xi` | $\Omicron$ `\Omicron` | $\Pi$ `\Pi` |
| $\Rho$ `\Rho` | $\Sigma$ `\Sigma` | $\Tau$ `\Tau` | $\Upsilon$ `\Upsilon` |
| $\Phi$ `\Phi` | $\Chi$ `\Chi` | $\Psi$ `\Psi` | $\Omega$ `\Omega` |
| $\varGamma$ `\varGamma` | $\varDelta$ `\varDelta` | $\varTheta$ `\varTheta` | $\varLambda$ `\varLambda` |
| $\varXi$ `\varXi` | $\varPi$ `\varPi` | $\varSigma$ `\varSigma` | $\varUpsilon$ `\varUpsilon` |
| $\varPhi$ `\varPhi` | $\varPsi$ `\varPsi` | $\varOmega$ `\varOmega` |   |
| $\alpha$ `\alpha` | $\beta$ `\beta` | $\gamma$ `\gamma` | $\delta$ `\delta` |
| $\epsilon$ `\epsilon` | $\zeta$ `\zeta` | $\eta$ `\eta` | $\theta$ `\theta` |
| $\iota$ `\iota` | $\kappa$ `\kappa` | $\lambda$ `\lambda` | $\mu$ `\mu` |
| $\nu$ `\nu` | $\xi$ `\xi` | $\omicron$ `\omicron` | $\pi$ `\pi` |
| $\rho$ `\rho` | $\sigma$ `\sigma` | $\tau$ `\tau` | $\upsilon$ `\upsilon` |
| $\phi$ `\phi` | $\chi$ `\chi` | $\psi$ `\psi` | $\omega$ `\omega` |
| $\varepsilon$ `\varepsilon` | $\varkappa$ `\varkappa` | $\vartheta$ `\vartheta` | $\thetasym$ `\thetasym` |
| $\varpi$ `\varpi` | $\varrho$ `\varrho` | $\varsigma$ `\varsigma` | $\varphi$ `\varphi` |
| $\digamma$ `\digamma` |

**Other Letters**

|   |   |   |   |   |
|---|---|---|---|---|
| $\imath$ `\imath` | $\nabla$ `\nabla` | $\Im$ `\Im` | $\Reals$ `\Reals` | $\text{\OE}$ `\text{\OE}` |
| $\jmath$ `\jmath` | $\partial$ `\partial` | $\image$ `\image` | $\wp$ `\wp` | $\text{\o}$ `\text{\o}` |
| $\aleph$ `\aleph` | $\Game$ `\Game` | $\Bbbk$ `\Bbbk` | $\weierp$ `\weierp` | $\text{\O}$ `\text{\O}` |
| $\alef$ `\alef` | $\Finv$ `\Finv` | $\N$ `\N` | $\Z$ `\Z` | $\text{\ss}$ `\text{\ss}` |
| $\alefsym$ `\alefsym` | $\cnums$ `\cnums` | $\natnums$ `\natnums` | $\text{\aa}$ `\text{\aa}` | $\text{\i}$ `\text{\i}` |
| $\beth$ `\beth` | $\Complex$ `\Complex` | $\R$ `\R` | $\text{\AA}$ `\text{\AA}` | $\text{\j}$ `\text{\j}` |
| $\gimel$ `\gimel` | $\ell$ `\ell` | $\Re$ `\Re` | $\text{\ae}$ `\text{\ae}` |
| $\daleth$ `\daleth` | $\hbar$ `\hbar` | $\real$ `\real` | $\text{\AE}$ `\text{\AE}` |
| $\eth$ `\eth` | $\hslash$ `\hslash` | $\reals$ `\reals` | $\text{\oe}$ `\text{\oe}` |

Direct Input:&nbsp;$∂ ∇ ℑ Ⅎ ℵ ℶ ℷ ℸ ⅁ ℏ ð$ ÀÁÂÃÄÅÆÇÈÉÊËÌÍÎÏÐÑÒÓÔÕÖÙÚÛÜÝÞßàáâãäåçèéêëìíîïðñòóôöùúûüýþÿ

**Unicode Mathematical Alphanumeric Symbols**

| Item | Range | Item | Range |
|------|-------|------|-------|
| Bold | $\text{𝐀-𝐙 𝐚-𝐳 𝟎-𝟗}$  | Double-struck | $\text{𝔸-}ℤ\ 𝕜$  |
| Italic | $\text{𝐴-𝑍 𝑎-𝑧}$  | Sans serif | $\text{𝖠-𝖹 𝖺-𝗓 𝟢-𝟫}$  |
| Bold Italic | $\text{𝑨-𝒁 𝒂-𝒛}$ | Sans serif bold | $\text{𝗔-𝗭 𝗮-𝘇 𝟬-𝟵}$ |
| Script | $\text{𝒜-𝒵}$ |Sans serif italic |  $\text{A-Z a-z}$ |
| Fractur | $\text{𝔄-}ℨ\text{ 𝔞-𝔷}$ a-z | Monospace | $\text{𝙰-𝚉 𝚊-𝚣 𝟶-𝟿}$ |

**Unicode**

The letters listed above will render properly in any KaTeX rendering mode.

In addition, Brahmic, Georgian, Chinese, Japanese, and Korean glyphs are always accepted in text mode. However, these glyphs will be rendered from system fonts (not KaTeX-supplied fonts) so their typography may clash. You can provide rules for CSS classes&nbsp;`.latin-fallback`,&nbsp;`.cyrillic-fallback`,&nbsp;`.brahmic-fallback`,&nbsp;`.georgian-fallback`,&nbsp;`.cjk-fallback`, and&nbsp;`.hangul-fallback`&nbsp;to provide fallback fonts for these languages. Use of these glyphs may cause small vertical alignment issues: KaTeX has detailed metrics for listed symbols and most Latin, Greek, and Cyrillic letters, but other accepted glyphs are treated as if they are each as tall as the letter M in the current KaTeX font.

If the KaTeX rendering mode is set to&nbsp;`strict: false`&nbsp;or&nbsp;`strict: "warn"`&nbsp;(default), then KaTeX will accept all Unicode letters in both text and math mode. All unrecognized characters will be treated as if they appeared in text mode, and are subject to the same issues of using system fonts and possibly using incorrect vertical alignment.

For Persian composite characters, a user-supplied&nbsp;[plug-in](https://github.com/HosseinAgha/persian-katex-plugin)&nbsp;is under development.

## [](https://katex.org/docs/supported.html#layout)Layout

### [](https://katex.org/docs/supported.html#annotation)Annotation

|   |   |
|---|---|
| $\cancel{5}$ `\cancel{5}` | $\overbrace{a+b+c}^{\text{note}}$ `\overbrace{a+b+c}^{\text{note}}` |
| $\bcancel{5}$ `\bcancel{5}` | $\underbrace{a+b+c}_{\text{note}}$ `\underbrace{a+b+c}_{\text{note}}` |
| $\xcancel{ABC}$ `\xcancel{ABC}` | $\not =$ `\not =` |
| $\sout{abc}$ `\sout{abc}` | $\boxed{\pi=\frac c d}$ `\boxed{\pi=\frac c d}` |

`\tag{hi} x+y^{2x}` $$\tag{hi} x+y^{2x}$$

`\tag*{hi} x+y^{2x}` $$\tag*{hi} x+y^{2x}$$

### [](https://katex.org/docs/supported.html#line-breaks)Line Breaks

KaTeX 0.10.0+ will insert automatic line breaks in inline math after relations or binary operators such as “=” or “+”. These can be suppressed by&nbsp;`\nobreak`&nbsp;or by placing math inside a pair of braces, as in&nbsp;`{F=ma}`.&nbsp;`\allowbreak`&nbsp;will allow automatic line breaks at locations other than relations or operators.

Hard line breaks are&nbsp;`\\`&nbsp;and&nbsp;`\newline`.

In display math, KaTeX does not insert automatic line breaks. It ignores display math hard line breaks when rendering option&nbsp;`strict: true`.

### [](https://katex.org/docs/supported.html#vertical-layout)Vertical Layout

|   |   |   |
|---|---|---|
| $x_n$ `x_n` | $\stackrel{!}{=}$ `\stackrel{!}{=}` | $a \atop b$ `a \atop b` |
| $e^x$ `e^x` | $\overset{!}{=}$ `\overset{!}{=}` | $a\raisebox{0.25em}{b}c$ `a\raisebox{0.25em}{b}c` |
| $_u^o$ `_u^o` | $\underset{!}{=}$ `\underset{!}{=}` | $\sum_{\substack{0<i<m\\0<j<n}}$ `\sum_{\substack{0<i<m\\0<j<n}}` |

The second argument of&nbsp;`\raisebox`&nbsp;can contain math if it is nested within&nbsp;`$…$`&nbsp;delimiters, as in&nbsp;`\raisebox{0.25em}{$\frac a b$}`

### [](https://katex.org/docs/supported.html#overlap-and-spacing)Overlap and Spacing

|   |   |
|---|---|
| ${=}\mathllap{/\,}$ `{=}\mathllap{/\,}` | $\left(x^{\smash{2}}\right)$ `\left(x^{\smash{2}}\right)` |
| $\mathrlap{\,/}{=}$ `\mathrlap{\,/}{=}` | $\sqrt{\smash[b]{y}}$ `\sqrt{\smash[b]{y}}` |

$\displaystyle\sum_{\mathclap{1\le i\le j\le n}} x_{ij}$ `\sum_{\mathclap{1\le i\le j\le n}} x_{ij}`

KaTeX also supports&nbsp;`\llap`,&nbsp;`\rlap`, and&nbsp;`\clap`, but they will take only text, not math, as arguments.

**Spacing**

| Function | Produces | Function | Produces |
|----------|----------|----------|----------|
| `\,` | ³∕₁₈ em space | `\kern{distance}` | space, width =&nbsp;_distance_ |
| `\thinspace` | ³∕₁₈ em space | `\mkern{distance}` | space, width =&nbsp;_distance_ |
| `\>` | ⁴∕₁₈ em space | `\mskip{distance}` | space, width =&nbsp;_distance_ |
| `\:` | ⁴∕₁₈ em space | `\hskip{distance}` | space, width =&nbsp;_distance_ |
| `\medspace` | ⁴∕₁₈ em space | `\hspace{distance}` | space, width =&nbsp;_distance_ |
| `\;` | ⁵∕₁₈ em space | `\hspace*{distance}` | space, width =&nbsp;_distance_ |
| `\thickspace` | ⁵∕₁₈ em space | `\phantom{content}` | space the width and height of content |
| `\enspace` | ½ em space | `\hphantom{content}` | space the width of content |
| `\quad` | 1 em space | `\vphantom{content}` | a strut the height of content |
| `\qquad` | 2 em space | `\!` | – ³∕₁₈ em space |
| `~` | non-breaking space | `\negthinspace` | – ³∕₁₈ em space |
| `\<space>` | space | `\negmedspace` | – ⁴∕₁₈ em space |
| `\nobreakspace` | non-breaking space | `\negthickspace` | – ⁵∕₁₈ em space |
| `\space` | space |

**Notes:**

`distance`&nbsp;will accept any of the&nbsp;[KaTeX units](https://katex.org/docs/supported.html#units).

`\kern`,&nbsp;`\mkern`,&nbsp;`\mskip`, and&nbsp;`\hspace`&nbsp;accept unbraced distances, as in:&nbsp;`\kern1em`.

`\mkern`&nbsp;and&nbsp;`\mskip`&nbsp;will not work in text mode and both will write a console warning for any unit except&nbsp;`mu`.

## [](https://katex.org/docs/supported.html#logic-and-set-theory)Logic and Set Theory

|   |   |   |   |
|---|---|---|---|
| $\forall$ `\forall` | $\complement$ `\complement` | $\therefore$ `\therefore` | $\emptyset$ `\emptyset` |
| $\exists$ `\exists` | $\subset$ `\subset` | $\because$ `\because` | $\empty$ `\empty` |
| $\exist$ `\exist` | $\supset$ `\supset` | $\mapsto$ `\mapsto` | $\varnothing$ `\varnothing` |
| $\nexists$ `\nexists` | $\mid$ `\mid` | $\to$ `\to` | $\implies$ `\implies` |
| $\in$ `\in` | $\land$ `\land` | $\gets$ `\gets` | $\impliedby$ `\impliedby` |
| $\isin$ `\isin` | $\lor$ `\lor` | $\leftrightarrow$ `\leftrightarrow` | $\iff$ `\iff` |
| $\notin$ `\notin` | $\ni$ `\ni` | $\notni$ `\notni` | $\neg$ `\neg`&nbsp;or&nbsp;`\lnot` |

Direct Input:&nbsp;$∀ ∴ ∁ ∵ ∃ ∣ ∈ ∉ ∋ ⊂ ⊃ ∧ ∨ ↦ → ← ↔ ¬$ ℂ ℍ ℕ ℙ ℚ ℝ

## [](https://katex.org/docs/supported.html#macros)Macros

|   |   |
|---|---|
| $\def\foo{x^2} \foo + \foo$ | `\def\foo{x^2} \foo + \foo` |
| $\gdef\bar#1{#1^2} \bar{y} + \bar{y}$ | `\gdef\bar#1{#1^2} \bar{y} + \bar{y}` |
|   | `\edef\macroname#1#2…{definition to be expanded}` |
|   | `\xdef\macroname#1#2…{definition to be expanded}` |
|   | `\let\foo=\bar` |
|   | `\futurelet\foo\bar x` |
|   | `\global\def\macroname#1#2…{definition}` |
|   | `\newcommand\macroname[numargs]{definition}` |
|   | `\renewcommand\macroname[numargs]{definition}` |
|   | `\providecommand\macroname[numargs]{definition}` |

Macros can also be defined in the KaTeX&nbsp;[rendering options](https://katex.org/docs/options.html).

Macros accept up to nine arguments: #1, #2, etc. Delimiters (such as&nbsp;`\def\add#1+#2{#1\oplus#2}`) are not currently supported.

`\gdef`,&nbsp;`\xdef`,&nbsp;`\global\def`,&nbsp;`\global\edef`,&nbsp;`\global\let`, and&nbsp;`\global\futurelet`&nbsp;will persist between math expressions.

KaTeX has no&nbsp;`\par`, so all macros are long by default and&nbsp;`\long`&nbsp;will be ignored.

Available functions include:

`\char`&nbsp;`\mathchoice`&nbsp;`\TextOrMath`&nbsp;`\@ifstar`&nbsp;`\@ifnextchar`&nbsp;`\@firstoftwo`&nbsp;`\@secondoftwo`&nbsp;`\relax``\expandafter`&nbsp;`\noexpand`

@ is a valid character for commands, as if&nbsp;`\makeatletter`&nbsp;were in effect.

## [](https://katex.org/docs/supported.html#operators)Operators

### [](https://katex.org/docs/supported.html#big-operators)Big Operators

|   |   |   |   |
|---|---|---|---|
| $\sum$ `\sum` | $\prod$ `\prod` | $\bigotimes$ `\bigotimes` | $\bigvee$ `\bigvee` |
| $\int$ `\int` | $\coprod$ `\coprod` | $\bigoplus$ `\bigoplus` | $\bigwedge$ `\bigwedge` |
| $\iint$ `\iint` | $\intop$ `\intop` | $\bigodot$ `\bigodot` | $\bigcap$ `\bigcap` |
| $\iiint$ `\iiint` | $\smallint$ `\smallint` | $\biguplus$ `\biguplus` | $\bigcup$ `\bigcup` |
| $\oint$ `\oint` | $\oiint$ `\oiint` | $\oiiint$ `\oiiint` | $\bigsqcup$ `\bigsqcup` |

Direct Input:&nbsp;<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><annotation encoding="application/x-tex">∫ ∬ ∭ ∮ ∏ ∐ ∑ ⋀ ⋁ ⋂ ⋃ ⨀ ⨁ ⨂ ⨄ ⨆</annotation></semantics></math>∫∬∭∮∏∐∑⋀⋁⋂⋃⨀⨁⨂⨄⨆

### [](https://katex.org/docs/supported.html#binary-operators)Binary Operators

|   |   |   |   |
|---|---|---|---|
| $+$ `+` | $\cdot$ `\cdot` | $\gtrdot$ `\gtrdot` | $x \pmod a$ `x \pmod a` |
| $-$ `-` | $\cdotp$ `\cdotp` | $\intercal$ `\intercal` | $x \pod a$ `x \pod a` |
| $/$ `/` | $\centerdot$ `\centerdot` | $\land$ `\land` | $\rhd$ `\rhd` |
| $*$ `*` | $\circ$ `\circ` | $\leftthreetimes$ `\leftthreetimes` | $\rightthreetimes$ `\rightthreetimes` |
| $\amalg$ `\amalg` | $\circledast$ `\circledast` | $\ldotp$ `\ldotp` | $\rtimes$ `\rtimes` |
| $\And$ `\And` | $\circledcirc$ `\circledcirc` | $\lor$ `\lor` | $\setminus$ `\setminus` |
| $\ast$ `\ast` | $\circleddash$ `\circleddash` | $\lessdot$ `\lessdot` | $\smallsetminus$ `\smallsetminus` |
| $\barwedge$ `\barwedge` | $\Cup$ `\Cup` | $\lhd$ `\lhd` | $\sqcap$ `\sqcap` |
| $\bigcirc$ `\bigcirc` | $\cup$ `\cup` | $\ltimes$ `\ltimes` | $\sqcup$ `\sqcup` |
| $\bmod$ `\bmod` | $\curlyvee$ `\curlyvee` | $x \mod a$ `x\mod a` | $\times$ `\times` |
| $\boxdot$ `\boxdot` | $\curlywedge$ `\curlywedge` | $\mp$ `\mp` | $\unlhd$ `\unlhd` |
| $\boxminus$ `\boxminus` | $\div$ `\div` | $\odot$ `\odot` | $\unrhd$ `\unrhd` |
| $\boxplus$ `\boxplus` | $\divideontimes$ `\divideontimes` | $\ominus$ `\ominus` | $\uplus$ `\uplus` |
| $\boxtimes$ `\boxtimes` | $\dotplus$ `\dotplus` | $\oplus$ `\oplus` | $\vee$ `\vee` |
| $\bullet$ `\bullet` | $\doublebarwedge$ `\doublebarwedge` | $\otimes$ `\otimes` | $\veebar$ `\veebar` |
| $\Cap$ `\Cap` | $\doublecap$ `\doublecap` | $\oslash$ `\oslash` | $\wedge$ `\wedge` |
| $\cap$ `\cap` | $\doublecup$ `\doublecup` | $\pm$ `\pm`&nbsp;or&nbsp;`\plusmn` | $\wr$ `\wr` |

Direct Input:&nbsp;<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><annotation encoding="application/x-tex">+ - / * ⋅ ± × ÷ ∓ ∔ ∧ ∨ ∩ ∪ ≀ ⊎ ⊓ ⊔ ⊕ ⊖ ⊗ ⊘ ⊙ ⊚ ⊛ ⊝</annotation></semantics></math>+−/∗⋅±×÷∓∔∧∨∩∪≀⊎⊓⊔⊕⊖⊗⊘⊙⊚⊛⊝

### [](https://katex.org/docs/supported.html#fractions-and-binomials)Fractions and Binomials

|   |   |   |
|---|---|---|
| $\frac{a}{b}$ `\frac{a}{b}` | $\tfrac{a}{b}$ `\tfrac{a}{b}` | $\genfrac ( ] {2pt}{1}a{a+1}$ `\genfrac ( ] {2pt}{1}a{a+1}` |
| ${a \over b}$ `{a \over b}` | $\dfrac{a}{b}$ `\dfrac{a}{b}` | ${a \above{2pt} b+1}$ `{a \above{2pt} b+1}` |
| $a/b$ `a/b` |   | $\cfrac{a}{1 + \cfrac{1}{b}}$ `\cfrac{a}{1 + \cfrac{1}{b}}` |

|   |   |   |
|---|---|---|
| $\binom{n}{k}$ `\binom{n}{k}` | $\dbinom{n}{k}$ `\dbinom{n}{k}` | ${n\brace k}$ `{n\brace k}` |
| ${n \choose k}$ `{n \choose k}` | $\tbinom{n}{k}$ `\tbinom{n}{k}` | ${n\brack k}$ `{n\brack k}` |

### [](https://katex.org/docs/supported.html#math-operators)Math Operators

|   |   |   |   |
|---|---|---|---|
| $\arcsin$ `\arcsin` | $\cotg$ `\cotg` | $\ln$ `\ln` | $\det$ `\det` |
| $\arccos$ `\arccos` | $\coth$ `\coth` | $\log$ `\log` | $\gcd$ `\gcd` |
| $\arctan$ `\arctan` | $\csc$ `\csc` | $\sec$ `\sec` | $\inf$ `\inf` |
| $\arctg$ `\arctg` | $\ctg$ `\ctg` | $\sin$ `\sin` | $\lim$ `\lim` |
| $\arcctg$ `\arcctg` | $\cth$ `\cth` | $\sinh$ `\sinh` | $\liminf$ `\liminf` |
| $\arg$ `\arg` | $\deg$ `\deg` | $\sh$ `\sh` | $\limsup$ `\limsup` |
| $\ch$ `\ch` | $\dim$ `\dim` | $\tan$ `\tan` | $\max$ `\max` |
| $\cos$ `\cos` | $\exp$ `\exp` | $\tanh$ `\tanh` | $\min$ `\min` |
| $\cosec$ `\cosec` | $\hom$ `\hom` | $\tg$ `\tg` | $\Pr$ `\Pr` |
| $\cosh$ `\cosh` | $\ker$ `\ker` | $\th$ `\th` | $\sup$ `\sup` |
| $\cot$ `\cot` | $\lg$ `\lg` | $\argmax$ `\argmax` | $\argmin$ `\argmin` |
| $\plim$ `\plim` | $\operatorname{f}$ `\operatorname{f}` | $\operatorname*{f}$ `\operatorname*{f}` |   |

Functions on the right column of this table can take&nbsp;`\limits`.

### [](https://katex.org/docs/supported.html#sqrt)\sqrt

$\sqrt{x}$ `\sqrt{x}`

$\sqrt[3]{x}$ `\sqrt[3]{x}`

## [](https://katex.org/docs/supported.html#relations)Relations

$\stackrel{!}{=}$ `\stackrel{!}{=}`

|   |   |   |   |
|---|---|---|---|
| $=$ `=` | $\eqcirc$ `\eqcirc` | $\lesseqgtr$ `\lesseqgtr` | $\sqsupset$ `\sqsupset` |
| $<$ `<` | $\eqcolon$ `\eqcolon` | $\lesseqqgtr$ `\lesseqqgtr` | $\sqsupseteq$ `\sqsupseteq` |
| $>$ `>` | $\Eqcolon$ `\Eqcolon` | $\lessgtr$ `\lessgtr` | $\Subset$ `\Subset` |
| $:$ `:` | $\eqqcolon$ `\eqqcolon` | $\lesssim$ `\lesssim` | $\subset$ `\subset`&nbsp;or&nbsp;`\sub` |
| $\approx$ `\approx` | $\Eqqcolon$ `\Eqqcolon` | $\ll$ `\ll` | $\subseteq$ `\subseteq`&nbsp;or&nbsp;`\sube` |
| $\approxeq$ `\approxeq` | $\eqsim$ `\eqsim` | $\lll$ `\lll` | $\subseteqq$ `\subseteqq` |
| $\asymp$ `\asymp` | $\eqslantgtr$ `\eqslantgtr` | $\llless$ `\llless` | $\succ$ `\succ` |
| $\backepsilon$ `\backepsilon` | $\eqslantless$ `\eqslantless` | $\lt$ `\lt` | $\succapprox$ `\succapprox` |
| $\backsim$ `\backsim` | $\equiv$ `\equiv` | $\mid$ `\mid` | $\succcurlyeq$ `\succcurlyeq` |
| $\backsimeq$ `\backsimeq` | $\fallingdotseq$ `\fallingdotseq` | $\models$ `\models` | $\succeq$ `\succeq` |
| $\between$ `\between` | $\frown$ `\frown` | $\multimap$ `\multimap` | $\succsim$ `\succsim` |
| $\bowtie$ `\bowtie` | $\ge$ `\ge` | $\owns$ `\owns` | $\Supset$ `\Supset` |
| $\bumpeq$ `\bumpeq` | $\geq$ `\geq` | $\parallel$ `\parallel` | $\supset$ `\supset` |
| $\Bumpeq$ `\Bumpeq` | $\geqq$ `\geqq` | $\perp$ `\perp` | $\supseteq$ `\supseteq`&nbsp;or&nbsp;`\supe` |
| $\circeq$ `\circeq` | $\geqslant$ `\geqslant` | $\pitchfork$ `\pitchfork` | $\supseteqq$ `\supseteqq` |
| $\colonapprox$ `\colonapprox` | $\gg$ `\gg` | $\prec$ `\prec` | $\thickapprox$ `\thickapprox` |
| $\Colonapprox$ `\Colonapprox` | $\ggg$ `\ggg` | $\precapprox$ `\precapprox` | $\thicksim$ `\thicksim` |
| $\coloneq$ `\coloneq` | $\gggtr$ `\gggtr` | $\preccurlyeq$ `\preccurlyeq` | $\trianglelefteq$ `\trianglelefteq` |
| $\Coloneq$ `\Coloneq` | $\gt$ `\gt` | $\preceq$ `\preceq` | $\triangleq$ `\triangleq` |
| $\coloneqq$ `\coloneqq` | $\gtrapprox$ `\gtrapprox` | $\precsim$ `\precsim` | $\trianglerighteq$ `\trianglerighteq` |
| $\Coloneqq$ `\Coloneqq` | $\gtreqless$ `\gtreqless` | $\propto$ `\propto` | $\varpropto$ `\varpropto` |
| $\colonsim$ `\colonsim` | $\gtreqqless$ `\gtreqqless` | $\risingdotseq$ `\risingdotseq` | $\vartriangle$ `\vartriangle` |
| $\Colonsim$ `\Colonsim` | $\gtrless$ `\gtrless` | $\shortmid$ `\shortmid` | $\vartriangleleft$ `\vartriangleleft` |
| $\cong$ `\cong` | $\gtrsim$ `\gtrsim` | $\shortparallel$ `\shortparallel` | $\vartriangleright$ `\vartriangleright` |
| $\curlyeqprec$ `\curlyeqprec` | $\in$ `\in`&nbsp;or&nbsp;`\isin` | $\sim$ `\sim` | $\vcentcolon$ `\vcentcolon` |
| $\curlyeqsucc$ `\curlyeqsucc` | $\Join$ `\Join` | $\simeq$ `\simeq` | $\vdash$ `\vdash` |
| $\dashv$ `\dashv` | $\le$ `\le` | $\smallfrown$ `\smallfrown` | $\vDash$ `\vDash` |
| $\dblcolon$ `\dblcolon` | $\leq$ `\leq` | $\smallsmile$ `\smallsmile` | $\Vdash$ `\Vdash` |
| $\doteq$ `\doteq` | $\leqq$ `\leqq` | $\smile$ `\smile` | $\Vvdash$ `\Vvdash` |
| $\Doteq$ `\Doteq` | $\leqslant$ `\leqslant` | $\sqsubset$ `\sqsubset` |
| $\doteqdot$ `\doteqdot` | $\lessapprox$ `\lessapprox` | $\sqsubseteq$ `\sqsubseteq` |

Direct Input:&nbsp;$= < > : ∈ ∋ ∝ ∼ ∽ ≂ ≃ ≅ ≈ ≊ ≍ ≎ ≏ ≐ ≑ ≒ ≓ ≖ ≗ ≜ ≡ ≤ ≥ ≦ ≧ ≫ ≬ ≳ ≷ ≺ ≻ ≼ ≽ ≾ ≿ ⊂ ⊃ ⊆ ⊇ ⊏ ⊐ ⊑ ⊒ ⊢ ⊣ ⊩ ⊪ ⊸ ⋈ ⋍ ⋐ ⋑ ⋔ ⋙ ⋛ ⋞ ⋟ ⌢ ⌣ ⩾ ⪆ ⪌ ⪕ ⪖ ⪯ ⪰ ⪷ ⪸ ⫅ ⫆ ≲ ⩽ ⪅ ≶ ⋚ ⪋ ⟂ ⊨$ `≔ ≕ ⩴`

### [](https://katex.org/docs/supported.html#negated-relations)Negated Relations

$\not =$ `\not =`

|   |   |   |   |
|---|---|---|---|
| $\gnapprox$ `\gnapprox` | $\ngeqslant$ `\ngeqslant` | $\nsubseteq$ `\nsubseteq` | $\precneqq$ `\precneqq` |
| $\gneq$ `\gneq` | $\ngtr$ `\ngtr` | $\nsubseteqq$ `\nsubseteqq` | $\precnsim$ `\precnsim` |
| $\gneqq$ `\gneqq` | $\nleq$ `\nleq` | $\nsucc$ `\nsucc` | $\subsetneq$ `\subsetneq` |
| $\gnsim$ `\gnsim` | $\nleqq$ `\nleqq` | $\nsucceq$ `\nsucceq` | $\subsetneqq$ `\subsetneqq` |
| $\gvertneqq$ `\gvertneqq` | $\nleqslant$ `\nleqslant` | $\nsupseteq$ `\nsupseteq` | $\succnapprox$ `\succnapprox` |
| $\lnapprox$ `\lnapprox` | $\nless$ `\nless` | $\nsupseteqq$ `\nsupseteqq` | $\succneqq$ `\succneqq` |
| $\lneq$ `\lneq` | $\nmid$ `\nmid` | $\ntriangleleft$ `\ntriangleleft` | $\succnsim$ `\succnsim` |
| $\lneqq$ `\lneqq` | $\notin$ `\notin` | $\ntrianglelefteq$ `\ntrianglelefteq` | $\supsetneq$ `\supsetneq` |
| $\lnsim$ `\lnsim` | $\notni$ `\notni` | $\ntriangleright$ `\ntriangleright` | $\supsetneqq$ `\supsetneqq` |
| $\lvertneqq$ `\lvertneqq` | $\nparallel$ `\nparallel` | $\ntrianglerighteq$ `\ntrianglerighteq` | $\varsubsetneq$ `\varsubsetneq` |
| $\ncong$ `\ncong` | $\nprec$ `\nprec` | $\nvdash$ `\nvdash` | $\varsubsetneqq$ `\varsubsetneqq` |
| $\ne$ `\ne` | $\npreceq$ `\npreceq` | $\nvDash$ `\nvDash` | $\varsupsetneq$ `\varsupsetneq` |
| $\neq$ `\neq` | $\nshortmid$ `\nshortmid` | $\nVDash$ `\nVDash` | $\varsupsetneqq$ `\varsupsetneqq` |
| $\ngeq$ `\ngeq` | $\nshortparallel$ `\nshortparallel` | $\nVdash$ `\nVdash` |
| $\ngeqq$ `\ngeqq` | $\nsim$ `\nsim` | $\precnapprox$ `\precnapprox` |

Direct Input:&nbsp;$∉ ∌ ∤ ∦ ≁ ≆ ≠ ≨ ≩ ≮ ≯ ≰ ≱ ⊀ ⊁ ⊈ ⊉ ⊊ ⊋ ⊬ ⊭ ⊮ ⊯ ⋠ ⋡ ⋦ ⋧ ⋨ ⋩ ⋬ ⋭ ⪇ ⪈ ⪉ ⪊ ⪵ ⪶ ⪹ ⪺ ⫋ ⫌$

### [](https://katex.org/docs/supported.html#arrows)Arrows

|   |   |   |
|---|---|---|
| $\circlearrowleft$ `\circlearrowleft` | $\leftharpoonup$ `\leftharpoonup` | $\rArr$ `\rArr` |
| $\circlearrowright$ `\circlearrowright` | $\leftleftarrows$ `\leftleftarrows` | $\rarr$ `\rarr` |
| $\curvearrowleft$ `\curvearrowleft` | $\leftrightarrow$ `\leftrightarrow` | $\restriction$ `\restriction` |
| $\curvearrowright$ `\curvearrowright` | $\Leftrightarrow$ `\Leftrightarrow` | $\rightarrow$ `\rightarrow` |
| $\Darr$ `\Darr` | $\leftrightarrows$ `\leftrightarrows` | $\Rightarrow$ `\Rightarrow` |
| $\dArr$ `\dArr` | $\leftrightharpoons$ `\leftrightharpoons` | $\rightarrowtail$ `\rightarrowtail` |
| $\darr$ `\darr` | $\leftrightsquigarrow$ `\leftrightsquigarrow` | $\rightharpoondown$ `\rightharpoondown` |
| $\dashleftarrow$ `\dashleftarrow` | $\Lleftarrow$ `\Lleftarrow` | $\rightharpoonup$ `\rightharpoonup` |
| $\dashrightarrow$ `\dashrightarrow` | $\longleftarrow$ `\longleftarrow` | $\rightleftarrows$ `\rightleftarrows` |
| $\downarrow$ `\downarrow` | $\Longleftarrow$ `\Longleftarrow` | $\rightleftharpoons$ `\rightleftharpoons` |
| $\Downarrow$ `\Downarrow` | $\longleftrightarrow$ `\longleftrightarrow` | $\rightrightarrows$ `\rightrightarrows` |
| $\downdownarrows$ `\downdownarrows` | $\Longleftrightarrow$ `\Longleftrightarrow` | $\rightsquigarrow$ `\rightsquigarrow` |
| $\downharpoonleft$ `\downharpoonleft` | $\longmapsto$ `\longmapsto` | $\Rrightarrow$ `\Rrightarrow` |
| $\downharpoonright$ `\downharpoonright` | $\longrightarrow$ `\longrightarrow` | $\Rsh$ `\Rsh` |
| $\gets$ `\gets` | $\Longrightarrow$ `\Longrightarrow` | $\searrow$ `\searrow` |
| $\Harr$ `\Harr` | $\looparrowleft$ `\looparrowleft` | $\swarrow$ `\swarrow` |
| $\hArr$ `\hArr` | $\looparrowright$ `\looparrowright` | $\to$ `\to` |
| $\harr$ `\harr` | $\Lrarr$ `\Lrarr` | $\twoheadleftarrow$ `\twoheadleftarrow` |
| $\hookleftarrow$ `\hookleftarrow` | $\lrArr$ `\lrArr` | $\twoheadrightarrow$ `\twoheadrightarrow` |
| $\hookrightarrow$ `\hookrightarrow` | $\lrarr$ `\lrarr` | $\Uarr$ `\Uarr` |
| $\iff$ `\iff` | $\Lsh$ `\Lsh` | $\uArr$ `\uArr` |
| $\impliedby$ `\impliedby` | $\mapsto$ `\mapsto` | $\uarr$ `\uarr` |
| $\implies$ `\implies` | $\nearrow$ `\nearrow` | $\uparrow$ `\uparrow` |
| $\Larr$ `\Larr` | $\nleftarrow$ `\nleftarrow` | $\Uparrow$ `\Uparrow` |
| $\lArr$ `\lArr` | $\nLeftarrow$ `\nLeftarrow` | $\updownarrow$ `\updownarrow` |
| $\larr$ `\larr` | $\nleftrightarrow$ `\nleftrightarrow` | $\Updownarrow$ `\Updownarrow` |
| $\leadsto$ `\leadsto` | $\nLeftrightarrow$ `\nLeftrightarrow` | $\upharpoonleft$ `\upharpoonleft` |
| $\leftarrow$ `\leftarrow` | $\nrightarrow$ `\nrightarrow` | $\upharpoonright$ `\upharpoonright` |
| $\Leftarrow$ `\Leftarrow` | $\nRightarrow$ `\nRightarrow` | $\upuparrows$ `\upuparrows` |
| $\leftarrowtail$ `\leftarrowtail` | $\nwarrow$ `\nwarrow` |
| $\leftharpoondown$ `\leftharpoondown` | $\Rarr$ `\Rarr` |

Direct Input:&nbsp;$← ↑ → ↓ ↔ ↕ ↖ ↗ ↘ ↙ ↚ ↛ ↞ ↠ ↢ ↣ ↦ ↩ ↪ ↫ ↬ ↭ ↮ ↰ ↱↶ ↷ ↺ ↻ ↼ ↽ ↾ ↾ ↿ ⇀ ⇁ ⇂ ⇃ ⇄ ⇆ ⇇ ⇈ ⇉ ⇊ ⇋ ⇌⇍ ⇎ ⇏ ⇐ ⇑ ⇒ ⇓ ⇔ ⇕ ⇚ ⇛ ⇝ ⇠ ⇢ ⟵ ⟶ ⟷ ⟸ ⟹ ⟺ ⟼$ ↽$

**Extensible Arrows**

|   |   |
|---|---|
| $\xleftarrow{abc}$ `\xleftarrow{abc}` | $\xrightarrow[under]{over}$ `\xrightarrow[under]{over}` |
| $\xLeftarrow{abc}$ `\xLeftarrow{abc}` | $\xRightarrow{abc}$ `\xRightarrow{abc}` |
| $\xleftrightarrow{abc}$ `\xleftrightarrow{abc}` | $\xLeftrightarrow{abc}$ `\xLeftrightarrow{abc}` |
| $\xhookleftarrow{abc}$ `\xhookleftarrow{abc}` | $\xhookrightarrow{abc}$ `\xhookrightarrow{abc}` |
| $\xtwoheadleftarrow{abc}$ `\xtwoheadleftarrow{abc}` | $\xtwoheadrightarrow{abc}$ `\xtwoheadrightarrow{abc}` |
| $\xleftharpoonup{abc}$ `\xleftharpoonup{abc}` | $\xrightharpoonup{abc}$ `\xrightharpoonup{abc}` |
| $\xleftharpoondown{abc}$ `\xleftharpoondown{abc}` | $\xrightharpoondown{abc}$ `\xrightharpoondown{abc}` |
| $\xleftrightharpoons{abc}$ `\xleftrightharpoons{abc}` | $\xrightleftharpoons{abc}$ `\xrightleftharpoons{abc}` |
| $\xtofrom{abc}$ `\xtofrom{abc}` | $\xmapsto{abc}$ `\xmapsto{abc}` |
| $\xlongequal{abc}$ `\xlongequal{abc}` |

Extensible arrows all can take an optional argument in the same manner  
as&nbsp;`\xrightarrow[under]{over}`.

## [](https://katex.org/docs/supported.html#special-notation)Special Notation

**Bra-ket Notation**

|   |   |   |
|---|---|---|
| $\bra{\phi}$ `\bra{\phi}` | $\ket{\psi}$ `\ket{\psi}` | $\braket{\phi\vert\psi}$ `\braket{\phi\vert\psi}` |
| $\Bra{\phi}$ `\Bra{\phi}` | $\Ket{\psi}$ `\Ket{\psi}` |   |

## [](https://katex.org/docs/supported.html#style-color-size-and-font)Style, Color, Size, and Font

**Class Assignment**

`\mathbin`&nbsp;`\mathclose`&nbsp;`\mathinner`&nbsp;`\mathop`  
`\mathopen`&nbsp;`\mathord`&nbsp;`\mathpunct`&nbsp;`\mathrel`

**Color**

$\color{blue} F=ma$ `\color{blue} F=ma`

Note that KaTeX&nbsp;`\color`&nbsp;acts like a switch. This aligns with LaTeX and differs from MathJax. Other KaTeX color functions expect the content to be a function argument:

$\textcolor{blue}{F=ma}$ `\textcolor{blue}{F=ma}`  
$\textcolor{#228B22}{F=ma}$ `\textcolor{#228B22}{F=ma}`  
$\colorbox{aqua}{F=ma}$ `\colorbox{aqua}{F=ma}`  
$\fcolorbox{red}{aqua}{F=ma}$ `\fcolorbox{red}{aqua}{F=ma}`

Note that, as in LaTeX,&nbsp;`\colorbox`&nbsp;&&nbsp;`\fcolorbox`&nbsp;renders its third argument as text, so you may want to switch back to math mode with&nbsp;`$`&nbsp;as in the examples above.

For color definition, KaTeX color functions will accept the standard HTML&nbsp;[predefined color names](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#Color_keywords). They will also accept an RGB argument in CSS hexa­decimal style. The "#" is optional before a six-digit specification.

**Font**

|   |   |   |
|---|---|---|
| $\mathrm{Ab0}$ `\mathrm{Ab0}` | $\mathbf{Ab0}$ `\mathbf{Ab0}` | $\mathit{Ab0}$ `\mathit{Ab0}` |
| $\mathnormal{Ab0}$ `\mathnormal{Ab0}` | $\textbf{Ab0}$ `\textbf{Ab0}` | $\textit{Ab0}$ `\textit{Ab0}` |
| $\textrm{Ab0}$ `\textrm{Ab0}` | $\bf Ab0$ `\bf Ab0` | $\it Ab0$ `\it Ab0` |
| $\rm Ab0$ `\rm Ab0` | $\bold{Ab0}$ `\bold{Ab0}` | $\textup{Ab0}$ `\textup{Ab0}` |
| $\textnormal{Ab0}$ `\textnormal{Ab0}` | $\boldsymbol{Ab0}$ `\boldsymbol{Ab}` | $\Bbb{AB}$ `\Bbb{AB}` |
| $\text{Ab0}$ `\text{Ab0}` | $\bm{Ab0}$ `\bm{Ab0}` | $\mathbb{AB}$ `\mathbb{AB}` |
| $\mathsf{Ab0}$ `\mathsf{Ab0}` | $\textmd{Ab0}$ `\textmd{Ab0}` | $\frak{Ab0}$ `\frak{Ab0}` |
| $\textsf{Ab0}$ `\textsf{Ab0}` | $\mathtt{Ab0}$ `\mathtt{Ab0}` | $\mathfrak{Ab0}$ `\mathfrak{Ab0}` |
| $\sf Ab0$ `\sf Ab0` | $\texttt{Ab0}$ `\texttt{Ab0}` | $\mathcal{AB0}$ `\mathcal{AB0}` |
|   | $\tt Ab0$ `\tt Ab0` | $\mathcal AB0$ `\cal AB0` |
|   |   | $\mathscr{AB}$ `\mathscr{AB}` |

One can stack font family, font weight, and font shape by using the&nbsp;`\textXX`&nbsp;versions of the font functions. So&nbsp;`\textsf{\textbf{H}}`&nbsp;will produce&nbsp;$\textsf{\textbf{H}}$ `\mathsf{\mathbf{H}}`&nbsp;will produce&nbsp;<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><annotation encoding="application/x-tex">\mathsf{\mathbf{H}}</annotation></semantics></math>H.

In cases where KaTeX fonts do not have a bold glyph,&nbsp;`\pmb`&nbsp;can simulate one. For example,&nbsp;`\pmb{\mu}`renders as :&nbsp;<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><annotation encoding="application/x-tex">\pmb{\mu}</annotation></semantics></math>μμ

**Size**

|   |   |
|---|---|
| $\Huge AB$ `\Huge AB` | $\normalsize AB$ `\normalsize AB` |
| $\huge AB$ `\huge AB` | $\small AB$ `\small AB` |
| $\LARGE AB$ `\LARGE AB` | $\footnotesize AB$ `\footnotesize AB` |
| $\Large AB$ `\Large AB` | $\scriptsize AB$ `\scriptsize AB` |
| $\large AB$ `\large AB` | $\tiny AB$ `\tiny AB` |

**Style**

|   |
|---|
| $\displaystyle\sum_{i=1}^n$ `\displaystyle\sum_{i=1}^n` |
| $\textstyle\sum_{i=1}^n$ `\textstyle\sum_{i=1}^n` |
| $\scriptstyle x$ `\scriptstyle x`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(The size of a first sub/superscript) |
| $\scriptscriptstyle x$ `\scriptscriptstyle x`&nbsp;(The size of subsequent sub/superscripts) |
| $\lim\limits_x$ `\lim\limits_x` |
| $\lim\nolimits_x$ `\lim\nolimits_x` |
| $\verb!x^2!$ `\verb!x^2!` |

`\text{…}`&nbsp;will accept nested&nbsp;`$…$`&nbsp;fragments and render them in math mode.

## [](https://katex.org/docs/supported.html#symbols-and-punctuation)Symbols and Punctuation

|   |   |   |
|---|---|---|
| `% comment` | $\dots$ `\dots` | $\KaTeX$ `\KaTeX` |
| $\%$ `\%` | $\cdots$ `\cdots` | $\LaTeX$ `\LaTeX` |
| $\#$ `\#` | $\ddots$ `\ddots` | $\TeX$ `\TeX` |
| $\&$ `\&` | $\ldots$ `\ldots` | $\nabla$ `\nabla` |
| $\_$ `\_` | $\vdots$ `\vdots` | $\infty$ `\infty` |
| $\text{\textunderscore}$ `\text{\textunderscore}` | $\dotsb$ `\dotsb` | $\infin$ `\infin` |
| $\text{--}$ `\text{--}` | $\dotsc$ `\dotsc` | $\checkmark$ `\checkmark` |
| $\text{\textendash}$ `\text{\textendash}` | $\dotsi$ `\dotsi` | $\dag$ `\dag` |
| $\text{---}$ `\text{---}` | $\dotsm$ `\dotsm` | $\dagger$ `\dagger` |
| $\text{\textemdash}$ `\text{\textemdash}` | $\dotso$ `\dotso` | $\text{\textdagger}$ `\text{\textdagger}` |
| $\text{\textasciitilde}$ `\text{\textasciitilde}` | $\sdot$ `\sdot` | $\ddag$ `\ddag` |
| $\text{\textasciicircum}$ `\text{\textasciicircum}` | $\mathellipsis$ `\mathellipsis` | $\ddagger$ `\ddagger` |
| $`$ `` ` `` | $\text{\textellipsis}$ `\text{\textellipsis}` | $\text{\textdaggerdbl}$ `\text{\textdaggerdbl}` |
| $\text{\textquoteleft}$ `text{\textquoteleft}` | $\Box$ `\Box` | $\Dagger$ `\Dagger` |
| $\lq$ `\lq` | $\square$ `\square` | $\angle$ `\angle` |
| $\text{\textquoteright}$ `\text{\textquoteright}` | $\blacksquare$ `\blacksquare` | $\measuredangle$ `\measuredangle` |
| $\rq$ `\rq` | $\triangle$ `\triangle` | $\sphericalangle$ `\sphericalangle` |
| $\text{\textquotedblleft}$ `\text{\textquotedblleft}` | $\triangledown$ `\triangledown` | $\top$ `\top` |
| $"$ `"` | $\triangleleft$ `\triangleleft` | $\bot$ `\bot` |
| $\text{\textquotedblright}$ `\text{\textquotedblright}` | $\triangleright$ `\triangleright` | $\$$ `\$` |
| $\colon$ `\colon` | $\bigtriangledown$ `\bigtriangledown` | $\text{\textdollar}$ `\text{\textdollar}` |
| $\backprime$ `\backprime` | $\bigtriangleup$ `\bigtriangleup` | $\pounds$ `\pounds` |
| $\prime$ `\prime` | $\blacktriangle$ `\blacktriangle` | $\mathsterling$ `\mathsterling` |
| $\text{\textless}$ `\text{\textless}` | $\blacktriangledown$ `\blacktriangledown` | $\text{\textsterling}$ `\text{\textsterling}` |
| $\text{\textgreater}$ `\text{\textgreater}` | $\blacktriangleleft$ `\blacktriangleleft` | $\yen$ `\yen` |
| $\text{\textbar}$ `\text{\textbar}` | $\blacktriangleright$ `\blacktriangleright` | $\surd$ `\surd` |
| $\text{\textbardbl}$ `\text{\textbardbl}` | $\diamond$ `\diamond` | $\degree$ `\degree` |
| $\text{\textbraceleft}$ `\text{\textbraceleft}` | $\Diamond$ `\Diamond` | $\text{\textdegree}$ `\text{\textdegree}` |
| $\text{\textbraceright}$ `\text{\textbraceright}` | $\lozenge$ `\lozenge` | $\mho$ `\mho` |
| $\text{\textbackslash}$ `\text{\textbackslash}` | $\blacklozenge$ `\blacklozenge` | $\diagdown$ `\diagdown` |
| $\text{\P}$ `\text{\P}` | $\star$ `\star` | $\diagup$ `\diagup` |
| $\text{\S}$ `\text{\S}` | $\bigstar$ `\bigstar` | $\flat$ `\flat` |
| $\text{\sect}$ `\text{\sect}` | $\clubsuit$ `\clubsuit` | $\natural$ `\natural` |
| $\copyright$ `\copyright` | $\clubs$ `\clubs` | $\sharp$ `\sharp` |
| $\circledR$ `\circledR` | $\diamondsuit$ `\diamondsuit` | $\heartsuit$ `\heartsuit` |
| $\text{\textregistered}$ `\text{\textregistered}` | $\diamonds$ `\diamonds` | $\hearts$ `\hearts` |
| $\circledS$ `\circledS` | $\spadesuit$ `\spadesuit` | $\spades$ `\spades` |
| $\text{\textcircled a}$ `\text{\textcircled a}` | $\maltese$ `\maltese` | $\minuso$ `\minuso` |

Direct Input:&nbsp;$£ ¥ ∇ ∞ · ∠ ∡ ∢ ♠ ♡ ♢ ♣ ♭ ♮ ♯ ✓ … ⋮ ⋯ ⋱ !$ ‼ ⦵$

## [](https://katex.org/docs/supported.html#units)Units

In KaTeX, units are proportioned as they are in TeX.  
KaTeX units are different than CSS units.

| KaTeX Unit | Value | KaTeX Unit | Value |
|------------|-------|------------|-------|
| em | CSS em | bp | 1/72​ inch × F × G |
| ex | CSS ex | pc | 12 KaTeX pt |
| mu | 1/18 CSS em | dd | 1238/1157​ KaTeX pt |
| pt | 1/72.27 inch × F × G | cc | 14856/1157 KaTeX pt |
| mm | 1 mm × F × G | nd | 685/642 KaTeX pt |
| cm | 1 cm × F × G | nc | 1370/107​ KaTeX pt |
| in | 1 inch × F × G | sp | 1/65536 KaTeX pt |

where:

F = (font size of surrounding HTML text)/(10 pt)

G = 1.21 by default, because KaTeX font-size is normally 1.21 × the surrounding font size. This value&nbsp;[can be overridden](https://katex.org/docs/font.html#font-size-and-lengths)&nbsp;by the CSS of an HTML page.

The effect of style and size:

| Unit | textstyle | scriptscript | huge |
|------|-----------|--------------|------|
| em or ex |$\rule{1em}{1em}$ | $\scriptscriptstyle\rule{1em}{1em}$ |$\huge\rule{1em}{1em}$ |
| mu | $\rule{18mu}{18mu}$ | $\scriptscriptstyle\rule{18mu}{18mu}$ | $\huge\rule{18mu}{18mu}$ |
| others | $\rule{10pt}{10pt}$ | $\scriptscriptstyle\rule{10pt}{10pt}$ | $\huge\rule{10pt}{10pt}$  |