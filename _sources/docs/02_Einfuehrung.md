---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---
<link rel="stylesheet" href="Styles.css">

(Einführung)=

# Digitale Signal Verarbeitung: Einführung





+++

## Was ist ein Signal?
Ein <span style='color:blue'> **Signal** <span style='color:black'>ist eine <span style='color:blue'>**Funktion** <span style='color:black'> einer oder mehrerer unabhängiger <span style='color:blue'> **Größen**, <span style='color:black'> die bestimmte <span style='color:blue'> **Informationen** <span style='color:black'> beinhalten.: <span style='color:blue'>        **$f(x,y,z,t)$**

* Signale übertragen Informationen:
    * Temperatur
    * Druck
    * elektrische Spannung
    * Sprache & Musik
    * Bilder & Videos
    * EKG
    * Aktien Kursverlauf
    *...
    
* Signale sind Funktionen, meist der Zeit.
* Signale werden mit Sensoren gemessen und können in beliebiger physikalischer Form vorkommen: Druck, Temperatir, elektrische Spannung, etc.







## Signal:

Definition:
Ein Signal ist eine Informationstragende physikalische Größe über Variablen.
Es kann auch eine mathematische Funktion mit mindestens einer unabhängigen Variable sein

    Träger von Information
    -   Sprache
    -   Bilder
    -   Musik
    -   medizinische Signale
    -   ...

    Variablen/Dimensionen:
    -   Zeit z(t) =\> eindimensional
    -   Raum r(x, y, z) =\> zweidimensional
    -   Lichtstärke l(i) =\> dreidimensional
    -   ...



### kontinuierlich und diskret

Kntinuierliche Signale sind reale Signale. Man könnte sie durchgängig zeichnen

        - x(t), t ∈ ℝ

        - runde Klammer () und abhängig von t !!!

![drawing](images/Einführung/image1.png)

Diskrete Signale entstehen durch das Abtasten von kontinuierlichen Signalen.
Man kann sie nur gepunktet zeichnen.

    -   x\[n\], n ∈ ℤ
    -   eckige Klammer \[\] und abhängig von n !!!

![](images/Einführung/image2.png)

### periodisch und aperiodisch

Periodische Signale wiederholen sich in einem bestimmten Abstand.

    -   x(t + T) = x(t), t, T ∈ ℝ (kontinuierlich)
    -   x\[n + N\] = x\[n\], n, N ∈ ℤ (diskret)
    -   Beispiel
    -   sin
    -   cos
    -   tan
    -   besondere Definitionen

Aperiodische Signale sind nicht periodische Signale. Also sie wiederholen sich nicht in einem
bestimmten Abstand.

#### deterministisch und stochastisch

Deterministische Signale sind nicht zufällig und man kann sie mathematisch exakt beschreiben.

Stochastische Signale sind zufällig und finden sich in der Natur wieder.

    Beispiel:
    -   Rauschen
    -   Sprachsignal
    -   Wackelkontakt

## Signalverarbeitung:

Definition:
Analyse, Manipulation und Synthese von Signalen mit einem System


    Anwendungsbeispiele:
    - Rekonstruktion
    - Nutzsignal vom Rauschen trennen
    - Kompression
    - ...
Man verwendet es für die Filterung von Signalen und besonders wichtig ist die Fourier Tranformation.

Die digitale Signalverarbeitung beschäftigt sich mit der Verarbeitung von Signalen bei digitalen Systemen
Das Digitale System besteht aus der Software für die Signalverarbeitungsverfahren und der Hardware.


![](images/Einführung/image3.png)

Man kann die digitale Signalverarbeitung mit verschiedenen Komponenten erreichen, wie z. B.:

    -   Allzweckrechner
    -   Digitale Signal Prozessoren (DSP)
    -   Spezialschaltungen (ASICs, FPGAs)
    -   Mikroprozessoren

Die Mikroprozessoren sind für viele Einsatzbereiche gut genug 

    -   mittlere Flexibilität
    -   mittlere Geschwindigkeit
    -   geringe Kosten
    -   geringerer Aufwand

### grundlegende Signalverarbeitungskette

![](images/Einführung/image4.png)

### grundlegende digitale Signalverarbeitungskette

![](images/Einführung/image5.png)

    Vorteile:
        -   hohe Stabilität
        -   Reproduzierbarkeit
        -   hohe Zuverlässigkeit
        -   geringe Störempfindlichkeit
    Nachteile:
        -   zusätzlicher Schaltungsaufwand
            -   A/D-Wandler und A/D-Wandler notwendig
        -   Quantisierungsrauschen
        -   neuartige Theorie
    Die Vorteile überwiegen deutlich die Nachteile von der digitalen Signalverarbeitungskette.

## Systeme:
### Systembeschreibung
Systeme können als Black Box oder White Box beschrieben werden. Sie werden mit H abgekürzt.
H steht auch für die Systemantwort.

Bei einem Black Box System hat man eine kontinuierliche Übertragungsfunktion und man hat keine Kenntnisse
über die innere Funktionsweise.
Man findet es bei analogen Schaltung wieder.

Hingegen hat man bei White Box Systemen eine diskrete Übertragungsfunktion und man hat Kenntnisse
über die innere Funktionsweise, durch z. B. den Programmcode.

### Linerarität

![](images/Einführung/image6.png)

### Zeitinvarianz

Ein um m verschobender Eingang sorgt für ein um m verschobenen
Ausgang.
    H{x(t)} = y(t) => H{x(t - m)} = y(t - m)

![](images/Einführung/image7.png)

### dynamisch und gedächnislos

Gedächnislose Systeme betrachten nur die Gegenwart

    y(t) = sin( x(t) + 1)

Dynamische Systeme betrachten nicht nur die Gegenwart, sondern auch die Vergangenheit.

        -   y(t) = x(t) + x(t-1) + 5

### kausal und nicht kausal
Ein System ist kausal, wenn sich die Eingänge sich auf die Gegenwart oder die Vergangenheit beziehen.

    y(t) = 2 * x(t) + x(t-3)

Ein System ist nicht kausal, wenn sich die Eingänge sich nicht auf die Gegenwart und nicht die Vergangenheit beziehen.

    y(t) = 2 * x(t+1)

### stabil und instabil

Ein System H ist stabil, wenn ein beschränktes Eingangssignal zu einem beschränkten Ausgangssignal führt.
![](images/Einführung/image8.png)

Ein System H ist instabil, wenn ein beschränktes Eingangssignal nicht zu einem beschränkten Ausgangssignal führt.

### lineares zeitinvariantes System (LZI)
Lineare Zeitinvarainte Systeme erfüllen die Bedingung der Zeitinvarianz und der Linerarität.

    Beschreibung durch:
    -   Impulsantwort
    -   Übertragungsfunktion
    -   Differentialgleichung
    -   Blockdiagramme

+++

## Bibliography

```{bibliography} ../_bibliography/references.bib
```
