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

(01_Vorkurs)=

> in diesem Kapitel haben Sie einen Vorkurs zur Auffrischung der Mathematik und Python-Programmierung
> für die digitale Signalverarbeitung Themen in dieser Vorlesung.
> Sie können dieses Kapitel überspringen, wenn Sie mit diesen Themen bereits vertraut sind und sich sicher fühlen.

# Mathematische Vorbereitung 


### Geometrische Bedeutung der Ableitung
Wir betrachten die Funktion

$$ y=f(x)$$

$x_0$ sei ein beliebiger punkt auf der $x$-Achse.

```{figure} /_static/lecture_specific/01_Vorkurs/Ableitung_1.png
```

### Komplexe Zahlen {cite}`baspinar`
Wenn wir bei einer mathematischen Berechnung auf $\sqrt{-1}$ stoßen, ersetzen wir $\sqrt{-1}$ durch
das Symbol $j$ und rechnen wir weiter.

**Beispiel

Wir möchten die quadratische Gleichung
$$ x^2-2x+5=a.x^2+b.x+c=0$$
mit Hilfe der abc-Formel lösen:

$$ x_{1,2} = \frac{-b \pm \sqrt{b^2-4ac}}{2a} $$
$$ = \frac{-(-2) \pm \sqrt{(-2)^2-4.1.5}}{2.1} $$
$$ = \frac{2 \pm \sqrt{-16}}{2} = 1 \pm 2.\sqrt{-1} = 1 \pm 2.j$$
          
Eine komplexe Zahl hat die folgende Struktur:
$$ \alpha+\beta.j $$

$\alpha$ heißt der Realteil der komplexen Zahl und $\beta$ der Imaginärteil. Eine komplexe Zahl enthält
also zwei reelle Zahlen ($\alpha$ und $\beta$). Deshalb können wir eine komplexe Zahl auf einem zwei dimensionalen Koordinatensystem (wie die $xy$-Ebene) platzieren (bzw. visualisieren):


### Matrizen
coming soon!

### Differentialgleichungen




## Bibliography

```{bibliography} ../_bibliography/references.bib
```
