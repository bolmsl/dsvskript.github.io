## Systeme & Sensorik & zeitdiskrete Signale
## Lernziele

>In diesem Kapitel wollen wir uns unterschiedliche Eigenschaften von Systemen anschauen und den Unterschied zwischen aktiven und passiven Sensoren lernen. Außerdem werden wir die Grundlagen der Umwandlung eines analogen zu einem digitalen Signal anschauen. Dies beinhaltet die Abtastung, und Quantisierung. Zu guter letzt wird das Problem von Aliasing behandelt.

>In der Demo werden anschließend Systeme auf ihre Eigenschaften analysiert, sowie ein analoges Signal digitalisiert.

## 1. Systeme

### 1.1 Systembeschreibung

Ein System $(H)$ wird in der Regel durch das Eingabe-Ausgabe-Verhalten beschrieben. Dabei interessieren uns die Beziehungen zwischen Eingangssignal $x(t)$ (oder $x[n]$ für diskrete Systeme) und Ausgangssignal $y(t)$ (bzw. $y[n]$). Die Modellierung eines Systems kann dabei entweder auf eine Black-Box- oder eine White-Box-Perspektive zurückgreifen. 

**Black-Box-Modell**
Das Black-Box-Modell geht davon aus, dass der innere Aufbau des Systems unbekannt oder nicht von Interesse ist. Hier wird das System als eine Art "schwarzer Kasten" behandelt, bei dem nur die äußeren Ein- und Ausgänge betrachtet werden.

Vorteile:
- Einfachheit: Die Analyse konzentriert sich ausschließlich auf die Eingabe-Ausgabe-Beziehung.
Ideal für Systeme, bei denen der innere Aufbau nicht zugänglich oder komplex ist (z. B. in der experimentellen Systemidentifikation).

Beispiel: 
- Ein RC-Glied, bei dem wir nur die Spannung am Eingang und die Spannung am Ausgang messen, ohne den inneren Aufbau des Systems zu betrachten.

**White-Box-Modell**
Im Gegensatz dazu bietet das White-Box-Modell eine detaillierte Darstellung des Systems, einschließlich seiner internen Strukturen, Mechanismen und physikalischen Prinzipien. Hier werden physikalische Modelle oder Gleichungen genutzt, um das Verhalten des Systems zu beschreiben.

Vorteile:
- Erhöhte Genauigkeit: Das System kann genau simuliert und optimiert werden.
- Verständlichkeit: Die internen Mechanismen und ihre Auswirkungen werden transparent.

```{figure} /_static/lecture_specific/vl2/1.png
```

### 1.2 Lineare vs. nicht-lineare 

Definition: Ein System $H$ ist **linear*+, wenn es die folgenden beiden Prinzipien erfüllt:

1. **Additivität** (Superpositionsprinzip): Wenn $H{x_1(t)} = y_1(t)$ und $H{x_2(t)} = y_2(t)$ dann gilt:
$$
H\{x_1(t) + x_2(t)\} = y_1(t) + y_2(t)
$$<br>

2. **Homogenität** (Skalierung): Für jede Skalarkonstante $c$ gilt:
$$
H\{c \cdot x(t)\} = c \cdot y(t)
$$

Dementsprechend erfüllt ein **nicht-lineares System** nicht die Eigenschaften Additivität und Homogenität.

Eigenschaften:

- Die Ausgangssignale eines linearen Systems sind direkt proportional zu den Eingangssignalen.
- Lineare Systeme lassen sich einfach analysieren und modellieren, z. B. durch Differential- oder Differenzengleichungen.
- Sie können mit Übertragungsfunktionen, Impulsantworten und Fourier-Transformationen beschrieben werden.

Beispiel: 

Ein elektrisches Netzwerk aus Widerständen und Kondensatoren ist bei linearem Verhalten (ohne Sättigung oder nicht-lineare Elemente wie Dioden) ein lineares System

```{figure} /_static/lecture_specific/vl2/2.png
```

### 1.3 Zeitinvariante vs. zeitvariante Systeme

**Definition:** <br>
Ein System $H$ ist **zeitinvariant**, wenn eine Zeitverschiebung des Eingangssignals $x(t)$
zu einer äquivalenten Zeitverschiebung des Ausgangssignals $y(t)$ führt, ohne dass sich die grundlegende Systemfunktion verändert.

**Mathematische Beschreibung:** 
Wenn das Eingangssignal $x(t)$ ein Ausgangssignal $y(t)$ erzeugt, also $H{x(t)} = y(t)$, dann gilt für eine Zeitverschiebung $t_0$:
$$
H\{x(t-t_0)\} = y(t-t_0)
$$<br>
Dementsprechend ist ein System **zeitvariant**, wenn eine Zeitverschiebung des Eingangssignals $x(t)$ nicht zu einer äquivalenten Zeitverschiebung des Ausgangssignals $y(t)$ führt.

Eigenschaften:

- Das Systemverhalten bleibt konstant, unabhängig vom Zeitpunkt, zu dem das Eingangssignal $x(t)$auf das System angewendet wird.
- Solche Systeme sind einfacher zu analysieren, da ihre Eigenschaften unabhängig von der Zeit sind.

Beispiel: 
- Ein RC-Tiefpassfilter ist zeitinvariant, da sich das Übertragungsverhalten nicht ändert, wenn das Eingangssignal zeitlich verschoben wird.

```{figure} /_static/lecture_specific/vl2/3.png
```

### 1.4 Dynamische Systeme vs. gedächtnichslose Systeme

#### Dynamische Systeme

Definition: Ein System $H$ ist dynamisch, wenn das Ausgangssignal $y(t_0)$ nicht nur vom aktuellen Eingangssignal $x(t_0)$, sondern auch von früheren (und manchmal zukünftigen) Eingangswerten abhängt.

Mathematische Beschreibung:
$$
y(t_0) = H\{x(t), t \leq t_0\}
$$

Eigenschaften:

- Speicherung: Dynamische Systeme haben ein "Gedächtnis" für vergangene Zustände.
- Zeitabhängigkeit: Der aktuelle Zustand des Systems wird durch seine Vorgeschichte beeinflusst.

Beispiele:

- $y(t) = x(t-1)$
- RC-Schaltkreis: Die Ausgangsspannung hängt von der Ladung des Kondensators ab, die durch vergangene Ströme bestimmt wird.
- Feder-Masse-System: Die Bewegung der Masse hängt nicht nur von der aktuellen Kraft, sondern auch von ihrer Geschwindigkeit (Abhängigkeit von der Vergangenheit) ab.
---
#### Gedächtnislose Systeme
Definition: Ein System $H$ ist gedächtnislos (memory-less), wenn das Ausgangssignal $y(t_0)$ zu jedem Zeitpunkt $t_0$ nur vom Eingangssignal $x(t_0)$ zum gleichen Zeitpunkt abhängt. Es gibt keinen Einfluss vergangener oder zukünftiger Eingangswerte.

Mathematische Beschreibung:
$$
y(t_0) = H\{x(t_0)\}
$$

Eigenschaften:

- Kein Speicher: Das System hat kein "Gedächtnis" für vergangene Eingangswerte.
- Reaktionszeit: Das Ausgangssignal wird sofort durch das aktuelle Eingangssignal bestimmt.

Beispiele:

- $y(t) = x(t-1)$
- Ohmsches Gesetz: $V = R \cdot I$, wo die Spannung $V$ direkt von der momentanen Stromstärke $I$ (Eingang) abhängt

### 1.4 Kausale vs. nichtkausale Systeme

#### Kausale Systeme

**Definition:**

Ein System $H$ ist kausal, wenn das Ausgangssignal $y(t_0)$ zu jedem Zeitpunkt $t_0$ nur von den gegenwärtigen und vergangenen Werten des Eingangssignals $x(t)$ abhängt. Zukünftige Werte des Eingangssignals $x(t)$ (für $t > t_0$) beeinflussen das Ausgangssignal nicht.

Mathematische Beschreibung:

$$
y(t_0) = H\{x(t), t\leq t_0\}
$$

**Eigenschaften:**

- Physikalische Realität: Reale Systeme sind immer kausal, da sie nicht auf zukünftige Ereignisse reagieren können.
- Berechnung: Der Ausgangswert kann in Echtzeit berechnet werden, basierend auf den bekannten Werten des Eingangssignals.

**Beispiele:**

- $y[n] = x[n-1]$
- RC-Schaltkreis: Die Ausgangsspannung hängt von der Ladung des Kondensators ab, die durch vergangene Ströme bestimmt wurde.
- Audio-Effekte: Ein Equalizer reagiert nur auf bereits abgespielte oder gegenwärtige Signale, nicht auf zukünftige.
---
#### Nichtkausale Systeme

**Definition:**

Ein System $H$ ist nicht-kausal, wenn das Ausgangssignal $y(t_0)$ zu einem bestimmten Zeitpunkt $t_0$ auch von zukünftigen Werten des Eingangssignals $x(t)$ abhängt, also für $t > t_0$.

**Mathematische Beschreibung:**
$$
y(t_0) = H\{x(t), t \leq t_0 \, \text{und} \, t > t_0\}
$$

**Eigenschaften:**

- Theoretische Anwendung: Nicht-kausale Systeme sind oft in der Theorie oder bei Offlinesignalverarbeitung relevant, da zukünftige Werte bekannt sein müssen.
- Nicht realisierbar in der physischen Welt, aber nützlich für Vorhersagealgorithmen oder bei der Nachbearbeitung von Signalen.

**Beispiele:**
- $y[n] = x[n+1]$
- Signalglättung: Ein Filter, das auf zukünftige Datenpunkte zugreift, um ein Signal zu glätten.
- Fourier-Transformation: Die Analyse eines Signals im Frequenzbereich erfordert Kenntnisse über das gesamte Signal, einschließlich zukünftiger Werte.


### 1.5 Stabile vs. Instabile Systeme

**Definition:**

Ein System $H$ ist stabil, wenn ein begrenztes Eingangssignal $x(t)$ immer zu einem ebenfalls begrenzten Ausgangssignal $y(t)$ führt.

**Mathematische Beschreibung:**
$$
\text{Wenn } |x(t)| \leq M_x, \text{ dann gilt } |y(t)| \leq M_y \, \forall t
$$
Dabei sind $M_x$ und $M_y$ endliche Werte.

---

BIBO-Stabilität (Bounded Input, Bounded Output):

>Ein System ist BIBO-stabil, wenn es auf jedes begrenzte Eingangssignal mit einem ebenfalls begrenzten Ausgang reagiert.
---
**Eigenschaften:**

- Stabilität ist entscheidend für die Zuverlässigkeit eines Systems.
- Viele Analysewerkzeuge, wie die Laplace- und Z-Transformation, setzen Stabilität voraus.

**Beispiele:**
- RC-Tiefpassfilter: Das Ausgangssignal bleibt begrenzt, auch wenn das Eingangssignal schwankt.
- Gedämpfte Schwingung: Ein System, das nach einer Anregung zu einem Ruhepunkt zurückkehrt.
---
#### Instabiles System

**Definition:** 

Ein System $H$ ist instabil, wenn ein begrenztes Eingangssignal $x(t)$ zu einem unbeschränkten Ausgangssignal $y(t)$ führen kann.

**Eigenschaften:**

- Instabile Systeme reagieren empfindlich auf kleine Änderungen im Eingangssignal, was zu unkontrollierten Ergebnissen führen kann.
- Sie sind in der Praxis häufig unerwünscht, können aber in bestimmten Anwendungen absichtlich eingesetzt werden (z. B. in Oszillatoren).

**Beispiele:**
- Ungefilterter Verstärker: Ein Verstärker, der keine Begrenzung für die Ausgangsspannung hat, kann bei einem schwachen Eingangssignal zu einer Sättigung oder Übersteuerung führen.
- Ungedämpfte Schwingung: Ein System, das bei einer Anregung nicht zur Ruhe kommt und stattdessen immer größere Schwingungen zeigt.

### 1.6 LZI Systeme

Im folgenden Verlauf der Vorlesung werden wir **l**ineare **z**eit**i**nvariante Systeme betrachten.

LZI Systeme können durch verschiedene mathematische Formeln und Modelle beschrieben werden:
- Impulsantwort
- Übertragungsfunktion
- Differentialgleichungen (DGL)
- Blockdiagramme
