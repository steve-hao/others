---
tags: []
created: 2020-09-04T02:10:58.741Z
modified: 2020-09-22T03:57:14.699Z
---
$$
 \alpha\beta\chi
$$

$\frac{abc}{xyz}$
 ​
 $$
 \frac{abc123} {xyz123}
 $$

``` puml
@startmindmap
* tour [[http://plantuml.com/sequence Alice]]
** time
** date
*** start
*** This is __underlined__

@endmindmap
```

``` puml
@startuml

!define osaPuml https://raw.githubusercontent.com/Crashedmind/PlantUML-opensecurityarchitecture2-icons/master
!include osaPuml/Common.puml
!include osaPuml/User/all.puml
!include osaPuml/Hardware/all.puml
!include osaPuml/Misc/all.puml
!include osaPuml/Server/all.puml
!include osaPuml/Site/all.puml

'. Mary is a Developer in the Product team. She has a Windows 10 PC and an Android phone.
'. Bob is a Manager in the Accounts team. He has Mac and an iPhone.
'. Ivan is an IT guy who looks after the server. 
'. They connect to the network hub, and via a firewall to the Internet.


' Users

osa_user_green_developer(Mary, "Mary", "Product team", "Developer")
osa_user_green_operations(Ivan, "Ivan", "IT Team", "Server Admin")
osa_user_green_business_manager(Bob, "Bob", "Accounts team", "Manager")

' Devices
osa_desktop(pc, "192.168.1.10", "Windows 10", "PC")
osa_laptop(mac, "192.168.1.12", "Mac", "Mac")
osa_iPhone(iphone, "Dynamic IP", "iPhone 11", "Phone")
osa_iPhone(android, "Dynamic IP", "Android 10", "Phone")
osa_server(server, "192.168.1.100", "Ubuntu Server 20.04 LTS", "Server")

' Network
osa_device_wireless_router(wifiAP, "192.168.1.1", "Network")
osa_hub(hub, "Office hub", "Hub")
osa_firewall(firewall, "51.37.24.103", "Network")
osa_cloud(cloud, "Internet", "Network")


Mary --> pc: source code
Mary --> android: social media

Bob --> mac: financial info
Bob --> iphone: phone calls


Ivan --> server: configuration

iphone --> wifiAP
android --> wifiAP
wifiAP --> hub

server --> wifiAP
mac --> hub
pc --> hub


hub --> firewall

firewall --> cloud

footer %filename() rendered with PlantUML version %version()\nThe Hitchhiker’s Guide to PlantUML
@enduml

```

``` puml
@startuml
!include <awslib/AWSCommon>
!include <awslib/AWSSimplified.puml>
!include <awslib/Compute/all.puml>
!include <awslib/mobile/all.puml>
!include <awslib/general/all.puml>
!include <awslib/GroupIcons/all.puml>

' skinparam linetype polyline
 skinparam linetype ortho

package "AWS Cloud" {
EC2(Smadex, "Smadex Service", " ")
}

Users(Users, "Users", " ")
TraditionalServer(AdExchange, "Ad Exchange", " ")
Mobile(Mobile, "Publisher app or web", " ")

Users -down-> Mobile: 1. Visits
Mobile -right-> AdExchange: 2. Start auction
AdExchange -right-> Smadex: 3. Bid request / response
Smadex -left-> Mobile: 4. Show Ad
Users -right-> Smadex: 5. Impression / click / install / event {request id}
@enduml

```
``` puml
@startuml


autonumber
box "UnTrustedDomain" #Red
	database UnTrustedKeyStore as UKS
	control UnTrustedKeyManager as UKM
    boundary KeyLoader as KL
end box

box "TrustedDomain" #Green
	database PersistentStorage as KS
    control KeyManager as KM

end box


group In the Beginning...
    
    group RootKBPK    
        note over KM: A Unique random key is born
        KS --> KS: Root KBPK exists
    end
   
    group Storage in UnTrustedDomain 
        KM --> KM: Create Class N KPBK
        KS --> KM: RootKBPK 
        note over KM: Shorthand for create a KeyBlock with ClassKBPK N as key payload, and RootKBPK as KBPK
        UKM --> UKS: KeyBlock[ClassKBPK N]RootKBPK        
        note over UKS: Process is repeated for ClassKBPK 1,2,3...N 
    end
end 

@enduml

```

``` puml
sprite $foo1 {
  FFFFFFFFFFFFFFF
  F0123456789ABCF
  F0123456789ABCF
  F0123456789ABCF
  F0123456789ABCF
  F0123456789ABCF
  F0123456789ABCF
  F0123456789ABCF
  F0123456789ABCF
  FFFFFFFFFFFFFFF
}
Alice -> Bob : Testing <$foo1>
```

aaa  
$\sqrt{abc}$、$\sqrt{2} $
 ​
 
 $$
 x^{x^{x^{x^{...}}}}=4\\
 x\color{red}^{(x^{x^{x^{...}}})}\color{black}=2 \Rightarrow x^{2}=2 \Rightarrow x=\sqrt{2}\\
 \sqrt{2}^{\sqrt{2}^{\sqrt{2}^{\sqrt{2}^{...}}}}=2\\
 x\color{green}^{(x^{x^{x^{...}}})}\color{black}=4 \Rightarrow x^{4}=4 \Rightarrow x=\sqrt{2}\\
 2=\sqrt{2}^{\sqrt{2}^{\sqrt{2}^{\sqrt{2}^{...}}}}=4\\
 $$

$x_{1}\cdot y_{2}\dots\infty\partial x \hat{ABC}$

\lvert hdhd \rvert 
$a\equiv b\times \int_{0}^{+\infty} \bigcup \mathbb{Z} $

$\left(\LARGE{AB}\right) \frac{df}{dx} \frac{\partial y}{\partial x} $

$$
 \sum_{j=1}^{n} 
$$
$$
\left(\LARGE{AB}\right(\\
\left| gsasb \right|
|asbvd|
\left\| abc \right\| 
$$

\begin{}
  
\end{}

\begin{bbb}
  \begin{aaa}
    
  \end{aaa}
\end{bbb}
$\bar{abc}\circ A^\circ \ddot{abc}\bigcup$

$\overrightarrow{F} hhh $ 
partial derivative
$$
 \left|\begin{matrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
   \end{matrix} \right\|
$$

$$
 \left| \begin{matrix}
   a & b & c\\
   d & e & f\\
   z & abc & n\\
 \end{matrix}
  \right|
$$


$$
\lim_{x \to \infty} 
$$

$$
\frac{\partial f}{\partial x} 
$$
responsibility
$$
\begin{cases}
   &\text{dfdff}\\
  ww &\text{fdgfd}\\
\end{cases} 
$$

$$
 \begin{aligned}
   ax+by&=c \\
   d&=3x-1 \\
 \end{aligned}
$$

$$
 \sqrt[5]{(x-1)} 
$$

$$
\textnormal{abcdef}
\textrm{ccc}\textsf{\,open} \texttt{AAA}\textit{That}\underline{Belone}\textbf{aaa}\mathrm{res}\mathbf{asd}\mathbb{qwe}\mathcal{zxc}\mathit{bgh}\mathtt{mnb}
$$

$$
 \alpha\beta\chi\delta\epsilon\varepsilon\phi\varphi\gamma\eta\iota\kappa\lambda\mu\nu\omega\pi\theta\vartheta\rho\sigma\varsigma\tau\upsilon \wedge\xi\psi\zeta
$$

$$
\Large aabcdefg\\
aabcd  \Huge vvv \\wer
$$

$$
\begin{cases}
  ssss \\
  bbbb
\end{cases}
$$

$$
\left(  \right)
$$

$\frac{1}{5+x}$

$\hat{\sin(x)}$

$\bar{(\frac{\bar{a}}{132})}$

$$ good luck $$
$$
 x\circ 180^\circ C  =\dot{\theta} \ddot{\beta}
$$

$$
  x\equiv y \\
 x\times y \\
 x\leq y\\
 x\lt y \\
 \sqrt{x-y}\\
 \int_{1}^{\infty}\bar{(x-1)}\,dx
$$

$has\,a\, good $

$\sin(\theta)$

$\sin(x)$ 
$$ \lim_{x\to\infty}\exp(-x) $$

$$
\sin(x)\\ 
\sum_{n=1}^\infty 1/k
$$

$$
 \sin^2(\theta) + \cos^2(\theta) = 1
$$
 ​
 $$
 \prod_{n=1}^{k}
 $$

 $$
c \to dgg
 $$
$\displaystyle abc$ 

$$
 \sum_{k=1}^{\infty} 
$$

$$
\llcorner abc \parallel hfhf \bowtie DHHD \not= bbb
$$

 $$
 \int_a^bf(x)\,dx
 $$
 ​
 $$
 \lim\limits_{x\to\infty}\exp(-x) = 0
 $$
 
$$ \,abc$$

$$
 f(x) = 
 \begin{cases}
 2x,\,\,x>0\\
 3x,\,\,x\le0\\
 \end{cases}
 $$


 $\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123字体}$


$$
 {\displaystyle \int f(x)\,dx}
 $$

$$
 {\textstyle \int f(x)\,dx}
 $$

$$
 \scriptstyle \int f(x)\,dx
 $$


$\tiny{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\scriptsize{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\small{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\normalsize{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\large{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\Large{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\LARGE{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\huge{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123}$

$\Huge{ABCDEFGHIJKLMNOPQRSTUVWXYZabc123




## chenglog 8.5->8.7