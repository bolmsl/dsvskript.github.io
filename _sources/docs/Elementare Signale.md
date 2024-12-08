# Elementare Signale
## (Teil I)

Skript von Thomas Kesper & Seyit Ahmet Duman

###### Elementare Signale sind grundlegende Signale aus welchen komplexere Signale zusammengesetzt sind. Sie sind elementar, da sie nicht weiter in einfacheren Formen dargestellt werden können. Sie sind also unzerlegbar und stellen somit die Basis von Signalen dar. Ein Elementarsignal wird mit einer Formel x(t) exakt definiert.

#### Beispiel der Nutzung von Elementaren Signalen:

Bei dem Testen von Audiosystems spielt man Elementare Signale ein und Überprüft den Ausgang. Da es Grundsignale sind, kann man relativ einfach durch das Signal am Ausgang die korrektheit des Systems überrpüfen.

### Bekanntesten Elementar Signale:

### Sprung-, Impuls- (Dirac) und Rampen Signal

#### Sprung:

Ein Sprung Signal ist ein Signal, welches für negative x Werte den Wert 0 und für positive x Werte den Wert 1 annimmt. Sie wird oft als Schalter interpretiert, der bei x= 0 Zeitpunkt eingeschaltet wird und dann für alle zukünftigen Zeiten eingeschaltet bleibt.

##### Ein Analoges Signal eines Sprungs wird wiefolgt definiert:

$$u(t) = \begin{cases} 
      1 & t >= 0 \\
      0 & sonst 
   \end{cases}$$


![png](/_static/lecture_specific/elementaresignale2/output_11_0.png)
    


##### Ein Diskretes Signal eines Sprungs wird wiefolgt definiert:

$$u[n] = \begin{cases} 
      1 & n >= 0 \\
      0 & sonst 
   \end{cases}$$

![png](/_static/lecture_specific/elementaresignale2/output_14_0.png)
    
#### Impuls (Dirac):

Ein Impuls Signal oder Dirac genannt ist ein Signal, welches bis auf einen sehr kurzen Moment immer x(t) = 0 ist. Aber in diesem einen kurzen Moment ist x(t) unendlich groß. Bei einem analogen Signal und einem diskreten wird dies jeweils anders beschrieben.

##### Bei einem Analogen Signal kann der Implus unendlich groß sein und wird somit mit unendlich definiert:

$$δ(t) = \begin{cases} 
      ∞ & t = 0 \\
      0 & sonst 
   \end{cases}$$

![png](/_static/lecture_specific/elementaresignale2/output_19_0.png)
    

##### Bei einem Diskreten Signal kann der Impuls höchsten 1 sein, da dies der größte Wert sein kann. Zwischen 1 und 0 gibt es aber unendlich viele reele Zahlen:

$$δ[n] = \begin{cases} 
      1 & t = 0 \\
      0 & sonst 
   \end{cases}$$

    
![png](/_static/lecture_specific/elementaresignale2/output_22_0.png)
    


### Vom Rechteck zum Dirac-Impuls

* __Ausgangssituation:__ Rechteckpuls mit Breite $\Delta t $ und Höhe $\ \frac{1}{\Delta t} \$ 


* Wenn wir $\Delta t $ gegen null gehen lassen, wird Rechteckpuls $\ \delta(t) $ unendlich dünn und unendlich hoch.

    * Aber die Fläche von Rechteck bleibt '1'
    
    * $\ \int_{-\infty}^{\infty} \delta(t)\,.\,dt = 1 $



![png](/_static/lecture_specific/elementaresignale2/output_25_0.png)
    



### Dirac-Impuls Eigenschaften

Dirac-Funktion ist zum Abtasten von einem analogen Signal:

* __Fläche von Dirac:__ _$\ \int_{-\infty}^{\infty} \delta(t)\,.\,dt = 1 $_ und _$\ \delta(t) = 0, t\neq$0$_
 

* __Abtastung:__ _$\ \int_{-\infty}^{\infty} x(t)\,.\,\delta(t)\,.\,dt = x(0) $_

* __Verschobene Delta-Funktion__ im Integral _$\ \int_{-\infty}^{\infty} x(t)\,.\,\delta(t-t_0)\,.\,dt = x(t_0) $_

* __Diskrete Funktion:__ _$\ \sum_{-\infty}^{\infty} x[n]\,.\,\delta[n-k] = x[k] $_

__Funktionswert von $\ x(t) $ an Stelle $\ t_0$ abgetastat__


![png](/_static/lecture_specific/elementaresignale2/output_32_0.png)
    



### Beziehung zwischen Sprung, Dirac und Rampe:


    
![png](/_static/lecture_specific/elementaresignale2/output_34_0.png)
    



Das Integral eines Impuls Signals (Dirac) ist immer ein Sprung Signal. Dadurch folgt, dass die Ableitung eines Sprungs einen Impuls Signal ist. Das Integral eines Sprungs ist ein Rampen Signal und die Ableitung eines Rampen Signals ist ein Sprung Signal.


___Kontinuierlich___

|__Integral von Dirac:__ | $\ u(t) = \int_{t = -\infty}^{\infty} \delta(t) $|__Integral von Sprung:__ $\ x(t) = \int_{t = -\infty}^{\infty} u(t) $ |
|:---|:---|:---|
|__Ableitung von Sprung:__ | $\ \delta(t) = \frac{du}{dt} $| __Ableitung von Rampe:__ $\ u(t) = \frac{dx}{dt} $ |

___Diskret___

|__Integral von Dirac:__ | $\ u[n] = \sum_{k = -\infty}^{\infty} \delta[k] $|__Integral von Sprung:__ $\ x[n] = \sum_{k = -\infty}^{\infty} u[k] $ |
|:---|:---|:---|
|__Ableitung von Sprung:__ | $\ \delta[n] = u[n]-u[n-1] $| __Ableitung von Rampe:__ $\ u[n] = x[n]-x[n-1] $ |

### Weitere Elementare Signale:

### Rechteck- Funktion

$\ T_0 \$ defeniert in der Recheck-Funktion die Breite des Rechtecks

 $$\ rect[\frac{t}{T_0}] = \begin{cases} 
      0 & t < 0 \\
      1 & t \geq 0 
   \end{cases}$$


    
![png](/_static/lecture_specific/elementaresignale2/output_42_0.png)
    


Die Rechteck Funtion wird genutzt um einen bestimmten Bereich einer Funktion darzustellen. Wenn man die Rechteckfunktion (mit den Werten 0 oder 1) mit der gewünschten Funktion multipliziert, bekommt man eine Funktion, welche überall null ist, nur in den Bereichen wo das Rechteck ist, bekommt man die Werte der gewünschten Funktion.

### Sinc- Funktion

Sinc- Funktionen  oder auch Spaltfunktion genannt.
Diese wird definiert als:

 $$\ sinc[\frac{t}{T_0}] =  \frac{sin(\frac{πt}{T_0})}{\frac{πt}{T_0}} $$


    
![png](/_static/lecture_specific/elementaresignale2/output_47_0.png)
    


### Kontinuierliche Kosinus- und Sinus-Schwingungen

Kosiuns und Sinus Signale sind kontinuierliche Signale, welche über die folgenden Formeln ausgedrückt werden:

$$x(t) =  x̂ * cos(2* pi * f0 * t) $$
$$x(t) =  x̂ * sin(2* pi * f0 * t) $$
    $$x̂:Amplitude $$
    $$f0:Frequenz (Hz) $$
    $$ω= 2 * pi * f0-> Kreisfrequenz (1/s)$$
    $$T0= 1/f0-> Periodendauer(s) $$


`
![png](/_static/lecture_specific/elementaresignale2/output_51_0.png)
    


Hier sieht man eine Sinus und eine Cosinus Funktion. Die Amplitude beschriebt den höchsten Punkt, also hier 1. Die Periodendauer ist 6. Dazu sieht man, dass drch eine 90° Phasenverschiebung das Sinus Signal in ein Cosinus Signal gewandelt wird und auch umgekehrt.

# Komplexe Zahlen
## Exkurs

### Imaginäre Zahl 'j'

$\ x^2 = -1 \equiv x = \sqrt{-1}$

* Es ist unlösbar mit den reellen Zahlen
* Da haben wir imaginäre Zahl __'j'__

* Die quadratische Gleichung: $\ x^2-2x+5 = ax^2-bx+c $ 

    * diese lösen wir mit der __abc-Formel__ bzw. __pq-Formel__

$\ x_{1,2} =  \frac{-b \pm \sqrt{b^2-4ac}}{2a} $

$\ x_{1,2} =  \frac{-(-2) \pm \sqrt{(-2)^2-4.1.5}}{2.1} = \frac{2 \pm \sqrt{-16}}{2.1} = \frac{2 \pm \sqrt{16}.\sqrt{-1}}{2.1} = 1 \pm 2.\sqrt{-1} = 1 \pm 2j   $

$\ x_1 = 1 + 2j $ __und__ $\ x_2 = 1 - 2j $

### Real- und Imaginärteil von komplexen Zahlen


Eine komplexe Zahl besteht immer aus einem Realteil (einer reelen Zahl) und einem Imaginärenteil (einer komplexen Zahl). 
Die Sturktur einer komplexen Zahl ist immer wiefolgt:
$$ α + βj  $$
Diese komplexe Zahl kann auf einem zweidimensionalen Koordinatensystem dargestellt werden. Diese nennt sich dann komplexe Zahlenebene.


![png](/_static/lecture_specific/elementaresignale2/output_62_0.png)
    

#### Betrag von komplexen Zahlen

Der Abstand von dem Koordinatenursprung und der komplexen Zahl ist der Bestrag der komplexen Zahl.

__Betrag von 'z':__  $ z : |z| = \sqrt{(α)^2 + (β)^2} $

#### Winkel von komplexen Zahlen

Der Winkel zwischen z und der reellen Achse wird gegen den Uhrzeigersinn gemessen.


    
![png](/_static/lecture_specific/elementaresignale2/output_67_0.png)
    



### Darstellungsformen komplexer Zahlen

#### Trigonometrische Form

$\ z = r\,(\cos(φ) +j\sin(φ)) $ $\ ∀z \in \mathbb {C} , r,φ \in \mathbb {R} \$

#### Exponential Form

$ z= r\,.e^{j\,.φ} $

Die Trigonometrische und Exponential Form sind durch die Eulersche Formel verknüpft:

$ e^{j\,.φ} = cos(φ) +j\,.sin(φ) $

### Rechenregeln von komplexer Zahlen

#### Addition

$ z_1 + z_2 = (x_1 +j\,.y_1) + (x_2 + j\,.y_2)$


$ =x_1 + x_2 + j\,.(y_1 + y_2) $


#### Multiplikation

$ z_1 \,. z_2 = (x_1 +j\,.y_1) \,. (x_2 + j\,.y_2)$

$ =x_1 x_2 - y_1 y_2 + j\,. (x_1 y_2 + y_1 x_2) $

##### Konjugiert Komplexe 

* Spiegelung an der reellen Achse:
    
    
$ z^* = (x_1 + j\,.y_2)^* = x_1 - j\,. y_1 $

$ (z_1 + z_2)^* = z^*_1 + z^*_2 $

$ (z_1 \,. z_2)^* = z^*_1 \,. z^*_2 $

##### Beispiel

$\ (2 + 3 \,j)\,(1-j) = \, ? $

$\ = 2 + 3 \,j - 2\,j - 3\,j^2 $

$\ = 2 + \,j - 3\,(-1) $

$\ = 2 + \,j + 3 $

$\ = 5 + \,j  $

## Elementare Signale
### (Teil II)

### Kontiunirliche Sinus-Funktion

__Sinus-Funktion:__ 
* Signale aus Sinusschwingungen bestehen.

<div class="alert alert-info"> $\ \hat{x}: $ &emsp; Amplitude  &emsp;&emsp; $\ \phi: $ &emsp; Phase </div>

<div class="alert alert-info"> $\ \omega=2\pi f_0 $ &emsp; Kreisfrequenz(1/s) &emsp;&emsp; $\ T_0=\frac{1}{f_0}\ $  &emsp; Periodendauer(s)" </div>

<div class="alert alert-info"> $\ f_0: $ &emsp; Frequenz (Hz) </div>

 + __Sinus- und Kosinusfunktionen über Phasenverschiebung miteinander verknüpft.__ 
    __ __
 _$\ \hat{x}\,sin(2\pi f_0t) = \hat{x}\,cos(2\pi f_0t - \frac{\pi}{2})   $_


![png](/_static/lecture_specific/elementaresignale2/output_82_0.png)
    


#### Beispiel

+ $\ x(t) = \hat{x}\,\sin(\omega \,t + \phi) $
+ $\ \hat{x} = 2 $
+ $\ f_0 = 1 Hz $
+ $\ \phi = -\frac{\pi}{4} $


|___welche Zeitpunt x(t) = 0___| | |___welche Zeitpunt x(t) = 1___|
|:----|---|---|:----|
|___sin(0) = 0___| | |___$\ \sin(\frac{\pi}{2})$ = 1___|
|$\ \omega = 2\,\pi \,f_0 $| | |$\ 2\,\pi \,f_0\,t -\frac{\pi}{4}  = \frac{\pi}{2} $|
|$\ 2\,\pi \,f_0\,t -\frac{\pi}{4}  = 0 $| | |$\ 2\,\pi \,t -\frac{\pi}{4}  = \frac{\pi}{2} $|
|$\ 2\,\pi \,t -\frac{\pi}{4}  = 0 $| | |$\ 2\,\pi \,t = \frac{3\pi}{4}$|
|$\ 2\,\pi \,t = \frac{\pi}{4}$| | |$\ t = \frac{3}{8}\,s$|
|$\ t = \frac{1}{8}\,s$| | | |




![png](/_static/lecture_specific/elementaresignale2/output_84_0.png)
    


### Diskrete Kosinus-Funktion

__Analog (kontinuierlich)__


+ $\ x(t) =  \hat{x} \, \cos(2\pi \, f_0 \, t - φ) $

+ $\ \hat{x}: Amplitude $ 

+ $\ f_0: Frequenz $ 


    
![png](/_static/lecture_specific/elementaresignale2/output_87_0.png)
    


__Diskret__

Eine diskrete Konisnus / Sinus Funktion, gibt nur die Werte der Jeweiligen Form in einem Abtastintervall an.

+ $\ x[n] =  \hat{x} \, \cos(2\pi \, f_0 \, T_s \, n - φ) $

+ $ 2\pi \, f_0 \, T_s \, n = \Omega_0 $

+ $ Abtastintervall: T_s = \frac{1}{f_s} $



    <StemContainer object of 3 artists>




    
![png](/_static/lecture_specific/elementaresignale2/output_89_1.png)
    


### Kontinuierliche harmonische Exponentialfunktion

Durch die Multiplikation einer Sinusschwingung mit der ___imaginären Zahl 'j'___ und die Addition der Kosinusschwingung dazu, erhalten wir die kontinuierliche harmonische Exponentialfunktion.

$\ x(t) = \hat{x}\,\cos(2\,\pi\,f_0\,t) + j\,\hat{x}\,\sin(2\,\pi\,f_0\,t) = \hat{x}\,e^{j\,2\,\pi\,f_0\,t} $

+ $\ \hat{x}: Länge $
+ $\ 2\,\pi\,f_0\,t: Winkel $
+ $\ 2\,\pi\,f_0 = \omega: Winkelgeschwindigkeit $

Positive Frequenz bedeutet Drehung gegen den Uhrzeigersinn


![png](/_static/lecture_specific/elementaresignale2/output_92_0.png)
    



### Diskrete harmonische Exponentialfunktion

$ x[n] = \hat{x}\,e^{j\,\Omega\,n} = \hat{x}\,cos(\Omega\,n) + j\,\hat{x}\,\sin(\Omega\,n) $

$ \Omega = 2\,\pi\,f_0\,T_s: normierte Kreisfrequenz $

$\ hat{x}: Amplitude $

$\ e: Euler'sche Zahl\, 2,71828... $


Zeiger dreht sich in der komplexen Ebene mit Geschwindigkeit ___$\ \Omega $___ gegen den Uhrzeigersinn


![png](/_static/lecture_specific/elementaresignale2/output_96_0.png)
    



### Komplexe Exponentialfunktion

$\ x(t) = \hat{x}\,.e^{z\,t}$ und $\ z = \sigma \,+ j\,\omega \in C $

$\ = \hat{x}\,.e^{(\sigma\,+\, j\,\omega)\,t}$

$\ = \hat{x}\,.e^{\sigma\,t} .\,e^{j\,\omega\,t}$

$\ = e^{\sigma\,t}\,.\hat{x}.\,(\cos(\omega\,t) +\, j\,\sin(\omega\,t))$


__$\ \hat{x}.\,(\cos(\omega\,t) +\, j\,\sin(\omega\,t) $__ : harmonische exponentielle Funktion 

__$\ e^{\sigma\,t} $__ : Zusatzfunktion

|Realteil | |Imaginärteil| |
|:----|:----|:----|:-----|
| $\ Re(z) $| $\ = \hat{x}\,e^\sigma\,\cos(\omega\,t) $ | $\ Im(z) $| $\ = \hat{x}\,e^\sigma\,\sin(\omega\,t) $

|Betrag| |Winkel| |
|:----|:----|:----|:----|
| $\ |e^z| $| $\ = \hat{x}\,e^\sigma\,t $ |$\  \omega\,t $| $\ =arg(\hat{x}\,e^\sigma\,t) $ |



![png](/_static/lecture_specific/elementaresignale2/output_100_0.png)
    



### Gerade und ungerade Signale

#### Gerade Signale

Gerade Funktionen sind zur y-Achse spiegelsymmetrisch. 

$\ x_g(t) = x_g(-t)$

__Besipiele__

* Kosinus-Schwingung
* Rechteckfunktion
* $\ x(t) = t^2 $


![png](/_static/lecture_specific/elementaresignale2/output_103_1.png)
    


#### Ungerade Signale

Ungerade Funktionen sind bezüglich des Ursprungs punktsymmetrisch. 

$\ x_u(t) = -x_u(-t)$

__Besipiele__

* Sinus-Schwingung
* Sägezahnfunktion
* $\ x(t) = t^3 $





![png](/_static/lecture_specific/elementaresignale2/output_105_1.png)
    


Jedes beliebige Signal x(t) kann in ein gerades und ungerades Teilsignal zerlegt werden: 

$\ x(t) = \frac{x(t) + x(-t)}{2} + \frac{x(t) - x(-t)}{2} $

$\ x_g(t) = \frac{x(t) + x(-t)}{2} $

$\ x_u(t) = \frac{x(t) - x(-t)}{2} $


    
![png](/_static/lecture_specific/elementaresignale2/output_107_0.png)
    



### Zerlegung eines Signals in gerade und ungerade Anteile

* Phasenbehaftete Schwingung lässt sich in Kosinus- und Sinus-Schwingung zerlegen.
    * Kosinus-Schwingung: gerades Signal
    * Sinus-Schwingung: ungerades Signal

__Beispiel__ __[$\ \cos(\alpha + \beta) = \cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta)$ ]__

$\ x(t) = \hat{x}\cos(2\pi f_0t+\phi)$

$\ = \frac{x(t) + x(-t)}{2} + \frac{x(t) - x(-t)}{2} $

$\ = \frac{\hat{x}\,\cos\,(\phi + 2\,\pi \,f_0\,t) + \hat{x}\,\cos\,(\phi - 2\,\pi f_0\,t)}{2} + \, \frac{\hat{x}\,\cos\,(\phi + 2\,\pi \,f_0\,t) - \hat{x}\,\cos\,(\phi - 2\,\pi f_0\,t)}{2} $

$\ = \hat{x}\,\cos\,(\phi)\,\cos(2\,\pi \,f_0\,t) - \hat{x}\,\sin\,(\phi)\,\sin(2\,\pi f_0\,t) $


    
![png](/_static/lecture_specific/elementaresignale2/output_111_0.png)
    

    
![png](/_static/lecture_specific/elementaresignale2/output_111_2.png)
    

![png](/_static/lecture_specific/elementaresignale2/output_111_3.png)
    

