# Digitale Signalverarbeitung - DFT Teil 2

## Diskrete Fourier-Transformation

### Herleitung der DFT-Gleichung

Am Anfang haben wir die Fourier-Transformation. Die Fourier-Transformation Ist Zeit und Frequenz kontinuierlich,

>$\ X(f) = \int_{-\infty}^{\infty}x(t)e^{-j2\pi ft}dt$<br>

da  wir die diskreter Fourier-Transformation haben wollen, müssen wir die Zeit und die Frequenz diskretisieren.

Wir fangen damit an, dass wir die Zeit diskretisieren in einem endlichen Bereich, dies machen wir, indem wir in einem festem periodischen Abstand den Frequenz Wert ablesen (Zeit diskret, Frequenz kontinuierlich):

>$\ X_{S}(f) = \sum_{n=0}^{N-1}x_{n}e^{-j2\pi fnT_{S}} = \sum_{n=0}^{N-1}x_{n}e^{-j2\pi n\frac{f}{f_{s}}}$<br>
<img src="Abtast_Graph.png">

Nachdem wir die Zeit diskretisiert haben, diskretisieren wir die Frequenz, das können wir machen, da wir die Formel in einem endlichen Bereich betrachten.

Um die Frequenz zu diskretisieren, diskretisieren wir die Kreisfrequenz:

>$\ \omega = \frac{2\pi}{T} $<br>

wird zu:

>$\ \omega = \frac{2\pi}{NT_{S}} $<br>

Multipliziert mit k erhält man die Frequenz, der verschiedenen Datenpunkte. 

Die diskretisierte Kreisfrequenz setz man in die zeitlich diskretisierte Fourier-Transformation. Dies sieht wie folgt aus:

>$\ X[k] = \sum_{n=0}^{N-1}x_{n}e^{-jwnT_{s}} = \sum_{n=0}^{N-1}x[n]e^{-jk\frac{2\pi}{NT_{s}}nT_{s}} = \sum_{n=0}^{N-1}x[n]e^{-jk\frac{2\pi}{N}n}$<br>

### Implementierung der DFT

Bei der Implementierung der DFT wird ein Teil, der DFT Gleichung Mit dem Drehfaktor ersetzt.
Der Drehfaktor lautet:

>$\ W_{N} = e^{-j\frac{2\pi}{N}}$

Wenn man die DFT Gleichung ersetzt, erhält man folgende Gleichung:

>$\ X[k] = \sum_{n=0}^{N-1}x[n]W_{N}^{kn}$

Die Gleichung wird für eine DFT Matrix benutzt k sind die Zeilen und n sind die Spalten.
> $$W_{N} = \begin{bmatrix} 
    W^{0, 0}_{N} & W^{0, 1}_{N} & ... & W^{0, (N-1)}_{N}\\
    W^{1, 0}_{N} & W^{1, 1}_{N} & ... & W^{1, (N-1)}_{N}\\
    ...          & ...          & ... & ...             \\
    W^{(N-1), 0}_{N} & W^{(N-1), 1)}_{N} & ... & W^{(N-1)(N-1)}_{N}\\    
\end{bmatrix}$$

Die inverse bekommt man durch die folgende Gleichung:

>$\ X[n] = \frac{1}{N} \sum_{n=0}^{N-1}x[k]W_{N}^{-kn}$

## Eigenschaften der DFT

### Linearität

Die Multiplikation mit k und Addition kann man auch vor der Diskretisierung oder nach der Diskretisierung ausrechnen:

> DFT{a ⋅ x(k) + b ⋅ y(k)} = a ⋅ DFT{x(k)} + b ⋅ DFT{y(k)}

### Periodizität

Das Ergebnis ändert sich nicht, obwohl man eine Periode, vor der Diskretisierung, weiter schaut:
> x[n] = x[n + N]<br>
> x[k] = x[k + N]

### Parceval-Theorem

Die Energie der Fourier-Transformation, welche zeitlich diskretisiert ist, die gleiche Energie ist, wie der der DFT multipliziert mit 1/N:
> $\ \sum_{n=0}^{N-1}[X(n)]^2 = \frac{1}{N} \sum_{n=0}^{N-1}[x(k)]^2 $

### Symmetrie

Die Symmetrie sagt raus, das alle geraden Datenpunkte, der DFT, konjugiert und nicht konjugiert das selber ergeben, sowie alle ungeraden Datenpunkte, der DFT:

> $\ X[\frac{N}{2}+l] = X[\frac{N}{2}-l]$<br>
>$\ l = \lbrace^{0, 1, 2, ... für N gerade}_{0.5, 1.5, 2.5, ... für N ungerade} $


```python

```
