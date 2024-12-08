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

(03_Zeitdisk)=

#  Zeitdiskrete Signale

> \"Python has gotten sufficiently weapons grade that we don't descend
> into R anymore. Sorry, R people. I used to be one of you but we no
> longer descend into R.\" -- Chris Wiggins

### inheitsimpuls und Einheitssprung
Der zeitdiskrete Einheitsimpuls (Kronecker-Delta) ist mit Höhe 1 hingegen unterschiedlich 
zum zeitkontinuierlichen Dirac-Impuls (Höhe ∞) definiert. Daher kann der Einheitsimpuls im 
Zeitdiskreten tatsächlich in der Praxis realisiert werden und stellt keinen, nur theoretischen 
Grenzfall dar. Wird ein zeitdiskreter Einheitsimpuls auf einen D/A-Wandler mit Halteglied 
gegeben, so ist seine Länge und damit die darin enthaltene Energie proportional zu T0. 


## zeitdisktrete Signale:

![](images/Zeitdiskret/image12.png)

### Darstellung zeitdiskreter Signale

Ein Signal wird in gleichen Abständen abgetastet (äquidisdant) und wird dadurch Zeitdiskret.


![](images/Zeitdiskret/image13.png)

Eine rechtsseitige Folge liegt vor, wenn folgende Bedingung gilt:
    
    u[n] = 0 für n ≤ 0 ⇒ rechtseitige Folge
    
    Vom zeitkontinuierlichem Signal bleiben nur die blauen
    Punkte übrig, aber ist noch wertkontinuierlich.
    Kurz: man betrachtet nur die Indexe größer 0.

### Diskretisierung von Signalen

Durch Abtasten und Quantisieren erhält man ein digitales Signal
(zeit- und wertdiskret).

    -   Abtastzeit => Zeitintervall in dem abgetastet wird

    -   Amplitudenauflösung => vertikale Genauigkeit des Wertebereichs

    -   Auflösung des A/D
        -   Die Anzahl der Bits bestimmt über die Genauigkeit (Amplitudenauflösung).
        -   Je höher die Anzahl der Bits, desto genauer ist die Amplitudenauflösung
        -   Es empfiehlt sich nur die minimal notwendige Auflösung zu verwenden, weil
            die Wandlung auch eine gewisse Zeit beansprucht.

![](images/Zeitdiskret/image14.png)

    Rechnung:
        5V Referenzspannung für den ADC
        ADC12 liefert 1003
        (5V * 1003) / 2^12 = 1,224 V liegt an

### Abtastung:

#### Abtasttheorem
    
    
    Formel: fs ≥ 2*fmax
    -   fs ist die Abtastfrequenz
    -   fmax die maximale Frequenz

    Die Abtastfrequenz muss mindestens das Doppelte von der maximal zu erwartenden Frequenz sein.
    Allerdings ist die maximale Frequenz in der Praxis häufig unbekannt und es kann zum Aliasing kommen (siehe Aliasing).
  
    Sie gilt grundsätzlich nur für periodische Signale (Wir machen aber trotzdem die Annahme,
    dass sie auch für nicht periodische Signale zu verwenden sind)
    Die Abtastwerte müssen Äquidistand sein.

#### Quantisierungsfehler


    Formel: eqmax = (xmax - xmin)/2^n
    -   eqmax ist der Quantisierungsfehler (Tiefe/Breite der
            Treppenstufe)

    -   xmax maximaler Wert im wertkontimuierlichen Bereich

    -   xmin minimaler Wert im wertkontimuierlichen Bereich (meistens 0)

    -   n ist die Größe des ADCs

    Durch das quantisieren entstehen im abgetasteten Signal Treppenstufen.
    Je größer die Stufen, desto größer der Fehler.

![](images/Zeitdiskret/image15.png)

#### Aliasing
    
Die erwartete Darstellung stimmt nicht mehr mit dem Gezeigten.
Es tritt vorallem dann auf, wenn das Abtasttheorem verletzt wird.
    
    Beipiel:
    -   Reifen scheinen rückwärts zu drehen auf der Autobahn

    Lösung:
    Man erhöht die Abtastfrequenz bis es nicht mehr zum Aliasing kommt. Das Problem ist nur
    man kennt die maximale Frequenz nicht (siehe Abtasttheorem) und die Abtastfrequenz ist
    technisch begrenzt.

    Stattdessen kann man einen Tiefpassfilter vorschalten, der nur Frequenzen durchlässt, für die das System
    konzipiert wurde.
    Einen Tiefpass als elektrische Schaltung wird auch meistens in der Praxis verwendet.

Man kann mit Antialiasing bei Bildern entgegenwirken,
indem man spezielle Tiefpassfilter verwendet.
Der Tiefpassfilter scheint die Kanten zu glätten (Kanten verschmieren)




## Bibliography

```{bibliography} ../_bibliography/references.bib
```

```{code-cell} ipython3

```
