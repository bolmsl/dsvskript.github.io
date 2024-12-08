---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.13.7
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---
<link rel="stylesheet" href="Styles.css">

(Sensorik und Zeitdiskrete Signale)=

# 2. Sensorik und Zeitdiskrete Signale

In dieser Vorlesung werden wir uns mit verschiedenen Aspekten befassen, darunter:

* Systeme
* Aktive und passive Sensoren
* Zeitdiskrete Signale
* Darstellung zeitdiskreter Signale
* Diskretisierung von Signalen
* Nyquist-Shannon-Abtasttheorem
* Aliasing
* Quantisierungsfehler




+++

## Systembeschreibung

In der digitalen Signalverarbeitung bezeichnet <span style='color:blue'> **ein System** <span style='color:black'>eine geordnete Struktur oder Einheit, die aus verschiedenen Komponenten besteht, die miteinander interagieren, um digitale Signale zu verarbeiten oder zu transformieren. Diese Komponenten können Algorithmen, Filter, Hardware-Module oder Software-Module sein, die entweder diskrete oder kontinuierliche Signale verarbeiten. Ein System (𝐻) wird durch sein Eingabe-Ausgabe-Verhalten beschrieben, entweder als <span style='color:green'>**Black Box** oder **White Box**.

In der <span style='color:green'>**Blackbox-Ansicht** wird das System ausschließlich durch sein Eingabe-Ausgabe-Verhalten beschrieben, ohne dass Einzelheiten über die internen Prozesse oder Mechanismen bekannt sind. Dies bedeutet, dass die Funktionsweise des Systems nur anhand seiner Eingangs- und Ausgangssignale beurteilt wird, ohne dass Informationen über die internen Komponenten, Strukturen oder Algorithmen verfügbar sind.

```{figure} /_static/lecture_specific/02_Sensorik/blackBox.png
```
Um ein Blackbox-System zu beschreiben, können Messungen und Tests durchgeführt werden, um das Eingabe-Ausgabe-Verhalten zu charakterisieren. Dazu gehören die Erfassung von Eingangssignalen, die Beobachtung der entsprechenden Ausgangssignale und die Analyse der Beziehung zwischen ihnen. Diese Informationen können in Form von Messungen, Tabellen oder grafischen Darstellungen präsentiert werden, um das Verhalten des Systems zu dokumentieren.


Die <span style='color:green'>**White-Box-Ansicht** beschreibt ein System nicht nur durch sein Eingabe-Ausgabe-Verhalten, sondern gewährt auch Einblicke in die internen Prozesse, Komponenten und Strukturen des Systems. Im Gegensatz zur Blackbox-Ansicht sind bei der White-Box-Betrachtung Informationen über die internen Mechanismen, Algorithmen und Arbeitsweise des Systems verfügbar.

```{figure} /_static/lecture_specific/02_Sensorik/whiteBox.png
```


### Lineare und nicht-lineare Systeme

Lineare Systeme gehorchen einem wichtigen Prinzip, das als Linearität bekannt ist. Diese Eigenschaft besagt, dass das System die Superpositionsregel einhält, was bedeutet, dass das Verhalten des Systems unter der Addition von Eingängen linear ist. Mathematisch ausgedrückt bedeutet dies, dass für ein lineares System H und Eingänge x1(t) und x2(t) sowie die entsprechenden Ausgänge y1(t) und y2(t) gilt:

Additivität: $$H(x1(t) + x2(t)) = H(x1(t)) + H(x2(t))$$ 
Skalierbarkeit:$$H(ax(t)) = aH(x(t))$$, wobei a eine Konstante ist.

Wenn ein System diese beiden Eigenschaften erfüllt, wird es als linear bezeichnet. Ein Beispiel für ein lineares System ist ein einfacher <span style='color:green'>**RC-Schaltkreis**.

Im Gegensatz dazu zeigen nichtlineare Systeme keine lineare Beziehung zwischen Eingang und Ausgang. Sie können komplexere Verhaltensweisen aufweisen, die nicht durch Superposition beschrieben werden können. Ein Beispiel für ein nichtlineares System ist ein  <span style='color:green'>**Schaltkreis**, der eine nichtlineare Bauelemente wie Dioden oder Transistoren enthält.

### Zeitinvariante vs. zeitvariante Systeme

<span style='color:green'>*Zeitinvariante Systeme* sind Systeme, bei denen eine Verzögerung oder Verschiebung des Eingangssignals auch zu einer entsprechenden Verzögerung oder Verschiebung des Ausgangssignals führt. Mit anderen Worten, wenn das Eingangssignal um eine gewisse Zeit <span style='color:blue'>*t* verzögert wird, dann wird das Ausgangssignal ebenfalls um dieselbe Zeit <span style='color:blue'>*t*  verzögert, ohne dass sich andere Eigenschaften des Signals ändern.

```{figure} /_static/lecture_specific/02_Sensorik/zeitInvar.png
```

Mathematisch ausgedrückt bedeutet Zeitinvarianz:

$$x(t)→H→y(t)$$

$$x(t−τ)→H→y(t−τ)$$

Das bedeutet, dass die Antwort des Systems auf ein um τ verschobenes Eingangssignal ebenfalls um τ verschoben wird.

Im Gegensatz dazu sind zeitvariante Systeme solche, bei denen sich die Charakteristiken des Systems im Laufe der Zeit ändern können. Das bedeutet, dass eine Verschiebung des Eingangssignals nicht unbedingt zu einer entsprechenden Verschiebung des Ausgangssignals führt.

### Dynamische Systeme vs. gedächtnislose Systeme

Ein <span style='color:green'>*gedächtnisloses System* wird als solches bezeichnet, wenn das Ausgangssignal y(t0) für jeden Zeitpunkt t0 ausschließlich vom Eingangssignal x(t0) abhängt. Das bedeutet, dass das System kein Gedächtnis über vergangene Eingangssignale oder vergangene Ausgangssignale hat und jede Ausgabe nur auf der aktuellen Eingabe basiert.

Beispiel:
$$y(t)=x^2(t)$$
$$y(t)=sin(t-1)*U(t)$$

Ein <span style='color:green'>*dynamisches System* wird als solches bezeichnet, wenn das Ausgangssignal y(t0) nicht nur vom Eingangssignal zum Zeitpunkt t=t0 abhängt, sondern auch von anderen Zeitpunkten t ist ungleich zu t0. Das bedeutet, dass das System eine zeitliche Entwicklung oder Dynamik aufweist, bei der das Ausgangssignal von vergangenen Eingaben und vergangenen Ausgaben beeinflusst wird.

Beispiel:
$$y(t)=x(t-1)$$
$$y(t)=3U(t)*2U(t-1)$$

## Sensorik

Lassen Sie uns zunächst definieren, was ein Sensor ist.
Ein <span style='color:green'>*Sensor* ist ein Gerät, das physikalische oder chemische Eigenschaften von Umgebungen oder Substanzen misst und in ein elektrisches Signal umwandelt, das von einem Messgerät, einer Steuerungseinheit oder einem Informationssystem interpretiert werden kann. Sensoren erfassen verschiedene Arten von Informationen:

* Druck
* Gewicht
* Strahlung
* Schall
* Temperatur
* Beschleunigung
* Gewisht
* Feuchtigkeit

```{figure} /_static/lecture_specific/02_Sensorik/sensor.png
```

### Aktive Sensoren und Passive Sensoren

Es gibt zwei Arten von Sensoren: Aktive und Passive. Betrachten wir ihre Hauptunterschiede:

<span style='color:violet'>*Energie*:

Aktive Sensoren: Benötigen Energie zum Senden von Signalen.
Passive Sensoren: Benötigen keine eigene Energiequelle und empfangen Informationen aus bereits vorhandenen Signalen.

<span style='color:violet'>*Signalübertragung*:

Aktive Sensoren: Senden aktive Signale in die Umgebung, um Informationen zu sammeln.
Passive Sensoren: Empfangen nur vorhandene Signale, ohne eigene Signale zu senden.

<span style='color:violet'>*Unabhängigkeit von externen Quellen*:

Aktive Sensoren: Können unabhängig von externen Signalquellen Informationen sammeln.
Passive Sensoren: Sind auf vorhandene Signale in der Umgebung angewiesen, um Informationen zu sammeln.
Beispiele und Anwendungen:

<span style='color:violet'>*Beispiele*
Aktive Sensoren: Infrarotsensoren zur Hinderniserkennung, Ultraschallsensoren zur Abstandsmessung und Radarsysteme zur Navigation in autonomen Systemen.
Passive Sensoren: Temperatursensoren, Mikrofone zur Aufnahme von Schall, Kameras zur Videoüberwachung und Radiosonden zur Erfassung atmosphärischer Daten.



### Zeitdiskrete Signale

<span style='color:blau'>*Zeitdiskrete Signale* sind Signale, die nur zu bestimmten diskreten Zeitpunkten vorhanden sind. Digital-Wandlung ermöglicht Analogdie Umwandlung von kontinuierlichen analogen Signalen in digitale Formate, die dann in digitalen Systemen verarbeitet werden können.  

```{figure} /_static/lecture_specific/02_Sensorik/wandlung.png
```

### Darstellung zeitdiskreter Signale

Darstellung zeitdiskreter Signale:

-Äquidistante Abtastung mit Abtastzeit T0
-Zeitdiskretes Signal als Folge: 
U(n) mit n als Zeitindex
- Das Signal wird charakterisiert durch die Angabe seiner Werte, z.B.: 
$$U[n]={...,0,0,0.26,0.45,0.59,...} mit  n={…,−2,−1,0,1,2,3,…}$$

Das Signal kann auch charakterisiert werden durch eine "diskrete" Funktion bei unendlichen/periodischen Folgen, z.B.: 
$$U[n]=0 für n≤0$$, was der unten dargestellten Reihenfolge entsprechend.

```{figure} /_static/lecture_specific/02_Sensorik/darstSignal.png
```
### Diskretisierung von Signalen

Die <span style='color:blau'>*Diskretisierung von Signalen* beinhaltet zwei Hauptprozesse:

<span style='color:blau'>*Abtastung (Sampling)*: Hierbei werden die Variablen eines kontinuierlichen Signals zu diskreten Zeitpunkten erfasst. Die Abtastzeit 
$$T_s$$ definiert das Intervall zwischen aufeinanderfolgenden Abtastungen.

<span style='color:blau'>*Quantisierung*: Dieser Prozess bezieht sich auf die Zuordnung von diskreten Werten zu den abgetasteten Variablen. Die Quantisierung erfolgt in der Regel durch Rundung oder Truncation, um den kontinuierlichen Wertebereich auf diskrete Werte abzubilden.

```{figure} /_static/lecture_specific/02_Sensorik/diskret.png
```
Die Hauptkomponenten dieses Prozesses:

* Abtastzeit kann zwischen µsec (Ströme, Drehzahlen) und Stunden (thermische, biologische Prozesse) liegen
* Amplitudenauflösung gibt vertikale Genauigkeitdes Digitizers an
* Auflösung des A/D ist die Anzahl der Bits, die zum Digitalisieren des Eingangssignals verwendet werden
z.B. Amplitudenauflösung von 8, 12 oder 16 Bit


### Aliasing
Der <span style='color:blau'>*Aliasing-Effekt* tritt auf, wenn analoge Signale digitalisiert werden und kann zu Fehlern führen. Dies geschieht, wenn die Abtastfrequenz nicht mindestens doppelt so hoch ist wie die Maximalfrequenz des Originalsignals, wie im Abtasttheorem von Nyquist beschrieben. Ein bekanntes Beispiel für Aliasing ist der scheinbar rückwärts drehende Räder-Effekt in Filmen, wenn sich Fahrzeuge beschleunigen.

```{figure} /_static/lecture_specific/02_Sensorik/aliasing.png
```

### Nyquist-Shannon-Abtasttheorem

Der <span style='color:blau'>*Das Nyquist-Shannon-Abtasttheorem* besagt, dass eine theoretisch ideale Rekonstruktion eines Analogsignals aus einem Abtastsignal möglich ist, wenn die Abtastfrequenz mindestens doppelt so hoch ist wie die höchste im Signal vorkommende Frequenz. 

$$ fs ≥ 2 *fmax$$

Die Bedingungen für die Anwendung dieses Theorems sind:

* die höchste Frequenz im Signal bekannt sein muss
* es sich um periodische Signale handeln muss
* die Abtastwerte äquidistant sein müssen

Das Hauptproblem besteht darin, dass die höchste Signalfrequenz in der Regel nicht bekannt ist, daher ist eine Tiefpassfilterung zur Bandbegrenzung erforderlich.

```{figure} /_static/lecture_specific/02_Sensorik/tiefpass.png
```

#### Filterung

Betrachten wir als Beispiel die Bildverarbeitung. 
In den Bildern entsprechen Kanten hochfrequenten Komponenten, während niederfrequente Komponenten Regionen bilden. Tiefpassfilter und Hochpassfilter werden in der Bildverarbeitung eingesetzt:

Tiefpassfilter: Lässt niedrige Frequenzen durch und unterdrückt hochfrequente Komponenten. Dies wird häufig für Unschärfeoperationen in der Bildverarbeitung verwendet.

Hochpassfilterung: Lässt hohe Frequenzen durch und unterdrückt niedrige Frequenzen. Dies wird häufig zum Definieren von Kanten in der Bildverarbeitung verwendet.

```{figure} /_static/lecture_specific/02_Sensorik/filterBeispiel.png
```

#### Quantisierungsfehler


Der Fehler, der bei der Quantisierung von analogen Signalen auftritt, entsteht aufgrund der Diskretisierung der Werte:

*Der <span style='color:blau'>*Ursache*: Analoge Signale haben einen kontinuierlichen Wertebereich, während digitale Signale nur diskrete Werte annehmen können. Die Quantisierung erfordert daher eine Rundung, die einen Fehler verursacht.
*Dieser Fehler ist die Differenz zwischen dem Eingangswert x und dem quantisierten Wert $$x_Q$$.
*Bei der Quantisierung eines kontinuierlichen Zahlenbereichs von $$x_min$$ bis $$x_max$$ mit n Bits ergeben sich $$2^n$$ Quantisierungsstufen.

Der maximale Quantisierungsfehler beträgt:
$$e_{Qmax}=\frac{x_max * x_min}{2^n}$$


