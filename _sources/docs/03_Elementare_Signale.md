### Was ist ein Elementarsignal?

- Ein deterministisches Signal, also eine Funktion, die man exakt definieren kann
- Durch diese kann ein System getestet werden. Man spricht auch von System Under Test (SUT). Heißt: Man hat ein System und möchte verstehen, wie es sich verhält. Bestimmte Signale werden an das System angespeist und somit das System analysiert.

**Beispiele für ein Elementarsignal:**

    - Kosinusfunktion
    
    - Impulssignal
    
    - Sprungsignal

BSP: Man kauft sich ein neues Auto und will die Beschleunigung testen. Durch das "auf das Gas hauen" ergibt sich ein Sprungsignal

```{figure} /_static/lecture_specific/elementare_signale/AutoBeispiel.png
```

---
### Sprungsignal

Ein Sprungsignal "springt" auf 1, wenn t bzw. n größer, oder gleich 0 ist. Bei negativen Zahlen bleibt das signal auf 0

**Analog:**


$${u(t) =}\begin{cases} 
1, & \text{für } t \ge 0 \\ 
0, & \text{sonst}
\end{cases}$$


**Diskret:**
 
$${u[n] =}
\begin{cases} 
1, & \text{für } n \ge 0 \\ 
0, & \text{sonst}
\end{cases}$$

```{figure} /_static/lecture_specific/elementare_signale/Sprungsignal.png
```

 ---

### Impuls (Dirac) Signal

Analog: Ist t = 0, so "pulsiert" das Signal ins Unendliche. Ist t alles andere als 0, so beibt das Signal auf 0

Diskret: Ist n = 0, so "pulsiert" das Signal auf 1. Ist n alles andere als 0, so bleibt das Signal auf 0

**Analog:**

$${\delta(t) =}
\begin{cases} 
\infty, & \text{für } t = 0 \\ 
0, & \text{sonst}
\end{cases}$$


**Diskret:**
 

$$ {\delta[n] =}\begin{cases} 
1, & \text{für } n = 0 \\ 
0, & \text{sonst}
\end{cases}$$

```{figure} /_static/lecture_specific/elementare_signale/DiracSignal.png
```

**Beispiel für ein Dirac Signal:**

- Man schlägt mit einem Hammer eine Kugel. Die Kraft die man aufbraucht ist nur an einem Moment da.

Eine Dirac-Funktion ist nichts anderes als eine Rechteckfunktion nur viel schmaler und mit einer Amplitude von $\infty$

```{figure} /_static/lecture_specific/elementare_signale/RechteckDirac.png
```

Aus dieser Grafik folgt, dass je schmaler wir ein Rechteck Signal machen, die Amplitude steigt, und die Breite geringer wird. Das letzte Bild zeigt die "Transformation" zum Dirac Impuls. Dieser hat genau wie die Rechteckfunktion die Fläche 1. 

#### Eigenschaften eines Dirac Impulses:

**Fläche von Dirac:**

$$\int_{-\infty}^\infty {\delta}{(t)} dt = 1$$

- Die Dirac Funktion hat die Eigenschaft, dass sie über das gesamte Intervall integriert immer den Wert 1 ergibt. Das heißt, dass die Fläche des Diracs immer gleich 1 ist, wobei $ {\delta}{(t) = 0}$ gilt für alle  $t {\neq} 0$

**Abstastung:**

  $$\int_{-\infty}^\infty {x(t)}{\delta}{(t)} dt = {x(0)}$$

Um ein Signal abzutasten benutzt man die Dirac Funktion indem man das ursprüngliche Signal ${x(t)}$ mit der Dirac Funktion ${\delta(t)}$ multipliziert. Die Integration liefert dann als Ergebnis ${x(0)}$ was bedeutet, dass die Dirac Funktion das Signal an der Stelle ${t = 0}$ abtastet

**Verschobene Delta-Funktion im Integral:**

$$\int_{-\infty}^\infty {x(t)}{\delta}{(t-t_0)} dt = {x(t_0)}$$

Wenn die Dirac-Delta-Funktion um ${t_0}$ verschoben wird, ergibt die Integration den Wert der Funktion 
${x(t)}$ an der Stelle ${t_0}$. Das heißt, die verschobene Delta-Funktion tastet den Wert der Funktion ${x(t)}$ an der Stelle ${t_0}$ ab. 

**Diskret:**

$$\sum_{n=-\infty}^{\infty}{x[n] \cdot \delta[n - k] = x[k]}$$

**Beispiel zur Abtastung:**

```{figure} /_static/lecture_specific/elementare_signale/Abtastung.png
```

---

### Beziehung zwischen Sprung, Dirac und Rampe:

```{figure} /_static/lecture_specific/elementare_signale/Beziehungen.png
```


Die Grafik zeigt, wie die drei verschiedenen Signale miteinander durch Integration und Differentiation verknüpft sind

---
### Rechteck-Funktion

Ist |t| > $\frac{T_0}{t}$, so bleibt das Signal auf 0.

Ist |t| größer, oder gleich $\frac{T_0}{t}$, so ist das Signal 1.

$${rect (\frac{t}{T_0}) =}
\begin{cases} 
0 & |t| > \frac{T_0}{2} \\ 
1 & |t| \leq \frac{T_0}{2}
\end{cases}$$

wobei ${T_0}$ die Breite des Rechtecks ist.

Die Rechteck-Funktion wird verwendet, um zeitlich begrenzte Signale zu modellieren.

```{figure} /_static/lecture_specific/elementare_signale/Rechteck.png
```

---
### Sinc-Funktion (Spaltfunktion)

Die Sinc-Funktion ist wie folgt definiert:

$sinc (\frac{t}{T_0}) = \frac{sin(\frac{\pi t}{T_0})}{\frac{\pi t}{T_0}}$

```{figure} /_static/lecture_specific/elementare_signale/Sinc.png
```

---

### Komplexe Zahlen:

**Imaginäre Zahl j:**

Definition: Die Zahl $\sqrt{-1}$ wird durch $j$ ersestzt. D.h ${j^2} = {-1}$ ersetzt.

Die imaginäre Zahl wird verwendet, um komplexe Zahlen zu bilden, die aus einem Realteil und einem Imaginärteil bestehen, beispielsweise 
${z = \alpha + \beta j}$, wobei $\alpha$ eine reelle Zahl ist und $\beta$ die imaginäre. Diese komplexe Zahl kann in der **komplexen Zahlenebene** wie folgt dargestellt werden:

```{figure} /_static/lecture_specific/elementare_signale/KomplexeZahlen.png
```

Komplexe Zahlen kann man in verschiedenen Formen darstellen:

1) **Trigonometrische Form:**
$z = r(cos(\phi) + sin(\phi))$

2) **Exponentialform:**
$z = r e^{j\phi}$

Diese zwei Formen sind durch die eulersche Formel verknüpft:

$e^{j\phi} = cos(\phi) + sin(\phi)$

**Rechenregeln:**

```{figure} /_static/lecture_specific/elementare_signale/Rechenregeln.png
```

---

### Kontinuierliche Kosinus- und Sinus-Schwingung:

**Legende:**

```{figure} /_static/lecture_specific/elementare_signale/Legende.png
```

Die **Kontinuierliche Kosinus-Schwingung** wird wie folgt definiert:

$x(t) = \hat{x} \cdot cos(2 \pi f_0 t)$

- Ein Ton beispielsweise kann als Kosinus-Schwingung ausgedrückt werden

```{figure} /_static/lecture_specific/elementare_signale/KontinuierlicheKosinusFunktion.png
```

Die Kosinus-Funktion in der Grafik wurde um $\frac{\pi}{2}$ verschoben, und wird somit zur Sinus-Funktion gemacht.

Die **Diskrete Kosinus-Schwingung** wird wie folgt definiert:

$x[n] = \hat{x} cos(2\pi f_0 T_s n - \phi)$,

wobei $(2\pi f_o T_s)$ auch als ${\Omega_0}$ zusammengefasst werden kann.

Das $\phi$ ist optional und wird daher nur bei einer vorhandenen Phasenverschiebung betrachtet.

```{figure} /_static/lecture_specific/elementare_signale/DiskreteKosinusFunktion.png
```

Die **Kontinuierliche Sinus-Schwingung** wird wie folgt definiert:

$x(t) = \hat{x} \cdot sin(2 \pi f_0 t)$

Sinus und Kosinus sind Phasenverschiebungen derselben Grundfunktion. Kosinus ist die Sinusfunktion mit einer Phasenverschiebung von $\frac{\pi}{2}$ nach links:

$x(t) = \hat{x} \cdot cos(2 \pi f_0 t + \frac{\pi}{2}) = x(t) = \hat{x} \cdot sin(2 \pi f_0 t)$

```{figure} /_static/lecture_specific/elementare_signale/Sinus.png
```

Die Sinus-Funktion in der Grafik hat eine Phasenverschiebung von $\frac{3\pi}{4}$,was bedeutet, dass die Funktion um $\frac{3\pi}{4}$ nach links verschoben ist.
Sie hat eine Amplitude von 5, also schwankt die Funktion zwischen -5 und +5 und die Periodendauer beträgt 1.

---


### Zeitkontinuierliches reales Exponentialsignal


Ein zeitkontinuierliches reales Exponentialsignal, beschreibt ein Signal, dessen Amplitude sich exponentiell mit der Zeit ändert.
Es wird durch folgende Formel definiert:

$x(t) = Ae^{\alpha t}$

Hierbei ist ${A}$ die Anfangsamplitude (also die Amplitude gemessen bei t = 0) und ${\alpha}$ ein Parameter, welcher entweder positiv oder negativ ist. Beide sind reale Zahlen.

**Fall 1:**
Ist ${\alpha} = 0$, so ergibt die e-Funktion einen Wert von 1 und somit ist der Wert von ${A}$ das Signal.

**Fall 2:**
Ist ${\alpha} > 0$, dann steigt das Signal exponentiell.

**Fall 3:**
Ist ${\alpha} < 0$, dann steigt das Signal exponentiell ab.

Grafisch dargestellt:
```{figure} /_static/lecture_specific/elementare_signale/ExponentialSignal.png
```

---

### Periodische komplexe Exponentialfunktion

**Kontinuierlich:**

Die kontinuierliche periodische komplexe Exponentialfunktion besteht aus der Multiplikation der Sinusschwingung mit der imaginären Zahl j und Addition der Kosinusschwingung:

$x(t) = \hat{x} cos(2\pi f_0 t) + j \hat{x} sin(2\pi f_0 t) = \hat{x} e^{j2\pi f_0 t}$, wobei:

$\hat{x}$ = Länge

$2\pi f_0 t$ = Winkel

$2\pi f_0$ = Winkelgeschwindigkeit

Eine negative Frequenz bedeutet eine Drehung im Uhrzeigersinn. Eine positive ist eine Drehung gegen den Uhrzeigersinn.

```{figure} /_static/lecture_specific/elementare_signale/PeriodischKomplexeExponentialFunktion.png
```

Um die Funktion zu diskretisieren wird das ${t}$ mit ${n \cdot T_s}$ ersetzt. Da $\Omega = 2\pi f_0 T_s$ ergibt, kann man diesen Teil mit $\Omega$ ersetzen. 

Die **diskrete** Funktion sieht dementsprechend wie folgt aus:

$x[n] = \hat{x} cos(\Omega \cdot n) + j\hat{x}sin(\Omega \cdot n) = \hat{x} e^{j \cdot \Omega \cdot n}$

---

### Allgemeine komplexe Exponentialfunktion

Die allgemeine Form der komplexen Exponentialfunktion ist gegeben durch:

$x(t) = \hat{x} \cdot e^{zt} = \hat{x} \cdot e^{(\sigma + j\omega)t} = \hat{x} \cdot e^{\sigma t} \cdot e^{j \omega t} = \underbrace{e^{\sigma t}}_{\text{\color{green} Zusatzfunktion}} \cdot \hat{x} \underbrace{\left( \cos(\omega t) + j \sin(\omega t) \right)}_{\text{\color{green} Harmonische Exponentielle}}$

Die Multiplikation der Haarmonischen Exponentielle und der Zusatzfunktion ergibt eine komplexe Exponentielle, welche entweder nach außen ($\sigma > 0$), oder nach innen ($\sigma < 0$) spiralförmig verläuft.

```{figure} /_static/lecture_specific/elementare_signale/AllgemeineKomplexeExponentialFunktion.png
```

---

### Gerade und Ungerade Signale

Ein Signal x(t) ist **gerade**, wenn es symmetrisch zur y-Achse ist:

$x_g(t)=x_g(−t)$

Daraus folgt, dass die Amplitudenwerte des Signals bei positiven und negativen Zeitpunkten identisch sind.

**Beispiele:**
- Kosinus-Schwingung
- Rechteckfunktion

Ein Signal x(t) ist **ungerade**, wenn es punktsymmetrisch bezüglich des Ursprungs ist:

$x_u(t)=-x_u(−t)$

Die Amplitudenwerte des Signals bei positiven und negativen Zeitpunkten sind gleich groß, aber entgegengesetzt.

**Beispiele:**
- Sinus-Schwingung
- Sägezahnfunktion

Jedes Signal x(t) kann in eine gerade und ungerade Komponente zerlegt werden:

$x(t) = 
\underbrace{\frac{x(t) + x(-t)}{2}}_{x_g(t)} + 
\underbrace{\frac{x(t) - x(-t)}{2}}_{x_u(t)}$
```{figure} /_static/lecture_specific/elementare_signale/GeradeUngerade.png
```

**Zerlegung eines Signals in gerade und ungerade Anteile:**

Eine phasenbehaftete Schwingung kann in Kosinus- und Sinus-Schwingungen zerlegt werden.

$\rightarrow$ Kosinus-Schwingung: gerades Signal
 
$\rightarrow$ Sinus-Schwingung: ungerades Signal

**Beispiel:**

```{figure} /_static/lecture_specific/elementare_signale/Beispiel.png
```