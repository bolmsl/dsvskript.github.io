---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
# Digitale Signalverarbeitung - Einführung

## Was ist ein Signal? 

Ein Signal ist eine mathematische Funktion mit mindestens einer unabhängigen Variable (Zeit, Raum, etc.), die eine informationstragende physikalische Größe beschreibt. Bespiele für unabhängige Variablen wären:  Die Zeit im Bezug auf Elektrische Größen (Stromstärke oder Spannung) t: u(t), i(t) oder auch die Zeit (Wochen/Monate/Jahre) im Bezug auf den Kryptoindex, Aktienmarkt n: d(n). Mehrere unabhängige Variablen wären z.B.: Die Raumkoordinaten (x,y) im Bezug auf die Helligkeit oder Intensität eines Bildes x und y: I(x,y). Die Raumkoordinaten (x,y,z) und über die Zeit (t) im Bezug auf den Schalldruck t: p(x,y,z,t) 

```{figure} /_static/lecture_specific/einfuehrung/Bild3.png
```
```{figure} /_static/lecture_specific/einfuehrung/Bild2.png
```

Sie übertragen verschiedenste Informationen wie zum Beispiel GPS-Signale, medizinische Signale(CT, MRT), den Druckverlauf eines Motors, Abstandssignale (mit Radar, Ultraschall, Laser), Funksignale, Datenströme, aber auch Bilder, Videos, Sprache, Musik und Aktienverläufe.
```{figure} /_static/lecture_specific/einfuehrung/Bild4.png
```
        
        
## Eigenschaften von Signalen

Signale können einige verschiedene Eigenschaften haben, welche in Folge aufgezählt werden.
```{figure} /_static/lecture_specific/einfuehrung/Bild5.png
```

### Kontinuierliche und diskrete Signale
    
   
   
Signale können entweder kontinuierlich oder disrekt sein. Kontinuierliche Signale (analog) sind mit jedem beliebigen Wert der Eingangsvariable definiert, wohingegen diskrete Signale (digital) 
zu bestimmten Abständen eine endliche Anzahl von Quantisierungsstufen zugeordnet haben. Es wird meistens durch das Abtasten eines kontinuierlichen Signales erzeugt. 
   
   
    
    
### Periodische und aperiodische Signale
    
Perodische und aperiodische Signale unterscheiden sich darin, dass perodische Signale sich in einem festen Abstand wiederholen (perodisch), während aperiodische Signale dies nicht tun, also nicht periodisch sind. Ein Beispiel für Ersteres wäre die Sinusfunktion und für Letzteres die Funktion x^2.
Bei periodeschen Signale ist ist die Frequenz auch ein wichtiger Wert. Sie wird aus dem Kehrwert von T, also f = 1/T errechnet.
periodisch:
```{figure} /_static/lecture_specific/einfuehrung/Bild6.png
```
aperiodisch:  
```{figure} /_static/lecture_specific/einfuehrung/Bild7.png
```
    
### Deterministische und stochastische Signale

    
Deterministische und stochastische Signale unterscheiden sich in ihrem Bezug auf Zufall. Deterministische Signale hängen nicht vom Zufall ab, sind also genau berechenbar. Sie sind beschrieben durch eine mathematische Funktion. Beispiele von so ein Signal wären Strom in Schaltung sowie die Sinusfunktion.
Stochastische Signale hingegen hängen von Zufällen ab, sind nicht genau berechenbar. Sprache und Rauschen sind Beispiele für so ein Signal.
Deterministisch:
```{figure} /_static/lecture_specific/einfuehrung/Bild8.png
```
Stochastisch:
```{figure} /_static/lecture_specific/einfuehrung/Bild9.png
```
   

### Eindimensionale und mehrdimensionale Signale
    
Der Unterschied von eindimensionalen und mehrdimensionalen Signalen, findet sich, in der Anzahl der Variablen des Signals. Eindimensionale Signale sind nur abhängig von einer Variabel, wie z.B. bei einem Audiosignal P(t). Mehrdimensionale Signale sind abhängig von mehreren Variablen, wie z.B. ein Bild I(x,y) oder ein Video I(x,y,t)
    
## Was ist Signalverabeitung?

Bei der Singalverarbeitung geht es um die Auswertung, Analyse, Manipulation und Synthese von Signalen mit einem System

### Wozu braucht man Signalverabeitung?

Signalverabeitung wird benötigt für die Speicherung und Rekonstruktion von Signale, die Kompression von Signalen, das Trennen von Informationen und Rauschen, sowie Merkmalextraktion für Klassifikation.

### Methoden der Signalverarbeitung

Einige Methoden welche für die Signalverarbeitung benutzt werden sind unteranderem Filtern, Transformation (z.B Fourier Transformation), Interpolation, Prädiktion und Korrelation

## Was ist *digitale* Signalverarbeitung?

Die digitale Signalverarbeitung verarbeitet Signale mit *digitalen* Systemen. Diese Systeme bestehen aus Software und Hardware: Software zur Realisierung von Signalverarbeitungsverfahren und Hardware, wo die Signalverarbeitung realisiert wird.

Erklärung der Komponenten:

physikalische Größe             analoge Komponenten                   digitale Komponenten

Technischer Prozess -> Sensor -> Verstärker -> Sample & Hold-Stufe -> A/D Wandler -> Digitaler Signalprozess

Technischer Prozess <- Aktor <- Verstärker <- Tiefpass & Glättung <- D/A Wandler <- Digitaler Signalprozess
    

## Grundlegende analoge Signalverarbeitungskette

Ein analoges Eingangssignal wird mit einer analogen Schaltung zu einem analogen Ausgangssignal umgewandelt. Die analoge Schaltung benutzt Verstärker, Widerstände, Kondensatoren, etc. Ein Beispiel ist die Rauschunterdrückung durch einen analogen Tiefpass-Filter.
    
```{figure} /_static/lecture_specific/einfuehrung/Bild10.png
```
    
## Grundlegende digitale Signalverarbeitungskette
    
Ein analoges Eingangssignal wird mit einem A/D Wandler zu einem digitalen Signal umgewandelt. Dieses digitale Signal wird dann durch einen digitalen Signalprozess umgewandelt. Nach der Bearbeitung wird das digitale Signal mit einem D/A Wandler wieder in ein analoges Ausgangssignal umgewandelt.
 
```{figure} /_static/lecture_specific/einfuehrung/Bild11.png
```
   
## Eigenschaten der digitalen Signalverarbeitung


Digitale Signalverarbeitung hat auch seine Vor- und Nachteile:
Die Vorteile sind Reproduzierbarkeit, hohe Zuverlässigkeit, hohe Genauigkeit bei großer Wortbreite, Langzeit- und Temperaturstabilität, geringe Störempfindlichkeit, sowie der Wegfall von Abgleichmaßnahmen.
Die Nachteile sind zusätzlicher Schaltungsaufwand (A/D- und D/A-Wandler), ein tiefer Frequenzbereich (Tiefpass am Eingang), die Verursachung von Störungen. Quantisierungsrauschen, sowie "Neue" Programmierung und Theorien. Bsp: Schulungskosten für alte Mitarbeiter.
    

## Realisierungsmöglichkeiten

Es gibt einige verschiede Realisierungsmöglichkeiten für die digitale Signalverarbeitung, jede mit ihren eigenen Vor- und Nachteilen.

### Allzweck-Rechner

Ein Allzweck-Rechner ist sehr flexibel, schnell einsetzbar, hat eine hohe Leistungsaufnahme und hat die Nähe zwischen Entwicklungsumgebung und Betriebsumgebung. Jedoch kann er teuer sein.


### Mikroprozessoren
    
Mikroprozessoren sind günstig, haben mittlere Flexibilität, mittlere Geschwindigkeit und einen geringer Entwicklungsaufwand.

### DSP

DSP haben eine höhere Geschwindigkeit und eine optimierte Architektur für Signalverarbeitung. Sie haben jedoch weniger Flexibilität und einen höheren Entwicklungsaufwand.


### Spezialschaltung (ASICs, FPGAs)

Spezialschaltungen habe eine hohe Geschwindigkeit, hohe Parallelisierbarkeit, jedoch auch hohe Entwicklungskosten und Entwicklungsdauer.
   

# Systeme

## Systembeschreibung

Ein System (H) wird druch Eingabe-Ausgabe-Verhalten als Black Box oder White Box beschrieben.
    
    Bei einer Black Box weiß man nicht was in der Funktion passiert,
     sondern nur was rauskommt.
    
    Bei einer White Box weiß man hingegen was in der Funktion 
    passiert und auch was rauskommt.

```{figure} /_static/lecture_specific/einfuehrung/Bild12.png
```

Beispiel: RC-Glied
```{figure} /_static/lecture_specific/einfuehrung/Bild13.png
```


## Lineare und nicht-lineare Systeme

    Lineare Systeme sind Systeme, welche definiert sind 
    durch die Gültigkeit der Superposition.
    Nicht lineare Systeme sind hingegen, wie der Name schon verrät,
    nicht linear.
    
     - Bsp: 5V -> 1A; 10V -> 2A
        
```{figure} /_static/lecture_specific/einfuehrung/Bild14.png
```

## Zeitinvariante und zeitvariante Systeme

Systeme sind *zeitinvariant* wenn eine Zeitverschiebung am Eingang zur gleichen Zeitverschiebung am Ausgang führt.

Systeme sind *zeitvariant* wenn Sie nicht *zeitinvariant* sind.

Zeitinvariant:   
```{figure} /_static/lecture_specific/einfuehrung/Bild15.png
```


## Dynamische und gedächtnislose Systeme

**Dynamische Systeme** sind nicht nur von dem Eingangssignal zum Zeitpunkt t = t0 abhängig, sondern auch von t != t0 abhängig.

Bsp:
    y(t) = x(t-1)
 
**Gedächtnislose Systeme** sind nur vom Eingangssignal x(t0) für jedes beliebige t0 abhängig. Gibt es in der realen Welt nicht!

Bsp:
    y(t) = x^2(t)


## Kausale und nichtkausale Systeme

### Kausales System
    
Wenn ein Ausgangssignal y(t0) nur vom Eingangssignal x(t), t<=t0 abhängt, wird ein System H als **kausal** bezeichnet.
Das Ausgangssignal hängt also nur vom aktuellen und vergangengen Eingangssignalen ab.

Bsp:
    y[n] = x[n-1]
     
### Nicht-kausale Systeme

Wenn ein System H nicht kausal ist, wird es als nicht-kausal bezeichnet!
Ist in der realen Welt nicht möglich

Bsp:
    y[n] = x[n+1]
    
## Stabile und instabile Systeme

### Stabiles System

Wenn ein **beschränktes Eingangssignal** zu einem **beschränkten Ausgangssignal** führt, wird eine System H als stabil bezeichnet. Das Singal ist in seinen Werten im Minimum und Maximum begrenzt (**beschränkt**).
BIBO (Bounded Input, Bounded Output)

### Instablies System

Wenn ein **beschränktes Eingangssignal** *nicht* zu einem **beschränkten Ausgangssignal** führt, wird es als instabiles System bezeichnet.

Bsp: Ball rollt von einem Berg runter

## LZI Systeme
LZI Systeme bedeutet lineare zeitinvariante Systeme.

x(t) -> H -> y(t)

LZI System können durch, Impulsantwort, Übertragungsfunktion, DGL (Differenzialgleichung) und Blockdiagramme beschrieben werden.


    

```python

```
