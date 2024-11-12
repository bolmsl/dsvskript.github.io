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

(DSV)=

## FFT

### Bedeutung und Motivation der FFT

Der FFT-Algorithmus (Fast Fourier Transform) ist eine numerische effizientere Methode zur Berechnung der DFT.
Der FFT-Algorithmus wird James Cooley und John W. Turkey zugeschrieben, welche diesen 1965 veröffentlichten. Der Algorithmus findet sich jedoch in anderer Form bereits 1805 in Werken von Carl Friedrich Gauß.
Der FFT-Algorithmus gehört zu der Kategorie der Divide and Conquer Algorithmen. Der FFT-Algorithmus benötigt daher eine beliebig große Zweierpotenz als Anzahl an Eingangsvariablen. Ist diese nicht gegeben werden die fehlenden stellen solange mit nullen aufgefüllt bis eine zweierpotenz an eingangsvariablen vorliegt. Die Berechnung der DFT wird nun in zwei Teilsummen aufgeteilt. Dies geschieht solange bis am Ende nur noch zwei Werte verbleiben. 
Die Rechenkomplexität wird somit von $O(N^{2})$ (Ursprüngliche Rechenkomplexität der DFT) auf $O(N \cdot log_{2}(N))$ reduziert.
Angenommen jeder Rechenvorgang dauert eine Nanosekunde, dann wäre 
Der Berechnungsaufwand bei einer Werteanzahl von 10<sup>9</sup> ist somit bei der FFT 30.10<sup>9</sup> wohingegen er bei der DFT 10<sup>18</sup> beträgt. Angenommen jeder dieser Rechenvorgänge dauert eine Nanosekunde so bräuchte die DFT ca. 30 Jahre, die FFT hingegen 30 Sekunden. 
Dies macht den FFT-Algoritmus zum Wichtigsten Algorithmus in der digitalen Signalverarbeitung.

| N                        | 1000     |    $10^{6}$       |  $10^{9}$         |
|--------------------------|----------|-------------------|-------------------|
| DFT:$N^{2}$              | $10^{6}$ | $10^{12}$         | $10^{18}$         |
| FFT:$N \cdot log_{2}(N)$ | $10^{4}$ | $20 \cdot 10^{6}$ | $30 \cdot 10^{9}$ |


### Ausgangspunkt: Definition der DFT

Zur Wiederholung eine DFT X[k]=$\sum\nolimits_{n=0}^{N-1}x[n]W_{N}^{kn}$ besteht aus folgenden Bestandteilen: 
* k: diskrete Frequenzvariable
* n: diskrete Zeitvariable
* N repräsentiert die Anzahl der Abstasterte und Frequenzvariablen
* X[k] repräsentiert den k-ten DFT_Koeffizient (die entsprechende Frequenz welche vom n-ten Abtastwert errechnet wurde)
* x[n] repräsentiert den n-ten Abtastwert von x(t)
* W<sub>N</sub> = e<sup>-j$\frac{2\Pi}{N}$</sup> repräsentiert den Drehfaktor

### Grundidee FFT

Um die Laufzeit zu verbessern, soll die DFT als Teile-Herrsche-Algorithmus umgeschrieben werden.
Damit die Liste der Abtastwerte immer weiter halbiert werden kann, wird vorrausgesetzt, dass N eine Zweierpotenz ist.   
Unter der Annahme $ N=2^{q}, q \in \mathbb{N} $ lässt sich die DFT wie folgt umschreiben.

1. x\[n\] wird in gerade und ungerade Teile aufgeteilt.  
    gerade $ n = 2r $:&emsp;$ x_{1}[n] = x[2r] $  
    ungerade $ n = 2r+1 $:&emsp;$ x_{2}[n] = x[2r + 1] $  
    f&uuml;r $ r = 0, 1, ..., \frac{N}{2}-1 $
2. Die DFT wird jeweils für den geraden und ungeraden Anteil bestimmt.  
    $ X[k]=\sum_{r=0}^{\frac{N}{2}-1}x[2r]W_{N}^{2rk}+\sum_{r=0}^{\frac{N}{2}-1}x[2r+1]W_{N}^{(2r+1)k} $  
    Der Drehfaktor des ungeraden Anteils l&auml;sst sich wie der des geraden Anteils schreiben, wenn der Teil
    $ W_{N}^{k} $ ausgeklammert wird.  
    $ X[k]=\sum_{r=0}^{\frac{N}{2}-1}x[2r]W_{N}^{2rk}+W_{N}^{k}\sum_{r=0}^{\frac{N}{2}-1}x[2r+1]W_{N}^{2rk} $
3. Der Drehfaktor wird umgeformt.  
   $ W_{N}^{2rk}=e^{-j\frac{2 \pi}{N}2rk}=e^{-j\frac{2 \pi}{N/2}rk}=W_{N/2}^{rk} $
4. Umformulieren der Analysegleichung  
   $ X[k]=\sum_{r=0}^{\frac{N}{2}-1}x[2r]W_{N/2}^{rk}+W_{N}^{k}\sum_{r=0}^{\frac{N}{2}-1}x[2r+1]W_{N/2}^{rk} $  
   Die Teilsummen lassen sich jetzt als DFTs der geraden und ungeraden Anteile schreiben  
   $ X[k]=X_{1}[k]+W_{N}^{k}X_{2}[k], k=0,1,...,N-1 $

### Schmetterlingsgraph


![Schmetterlingsgraph Grundidee](../Schmetterlingsgraph_Grundidee.png)

#### Rekursive Zerlegung

Die FFT wird auf beide Hälften angewandt.
![Schmetterlingsgraph Zerlegt 1](../Schmetterlingsgraph_zerlegt_1.png)
Die Zerlegung wird wiederholt, bis jeweils noch zwei Werte vorhanden sind.
![Schmetterlingsgraph Zerlegt 2](../Schmetterlingsgraph_zerlegt_2.png)

### Weitere Vereinfachungen

Da $X[k+\frac{N}{2}]=X[k]$ l&auml;sst sich $X[k]$ f&uuml;r alle $k \ge \frac{N}{2}$ umschreiben als
$ X[r+\frac{N}{2}]=X_{1}[r]+W_{N}^{r+\frac{N}{2}}X_{2}[r], r=0,1,...,\frac{N}{2}-1 $

Der Drehfaktor lässt sich wie folgt umformulieren.

1. $ W_{N}^{r+N/2}=W_{N}^{N/2}W_{N}^{r} $
2. $ W_{N}^{N/2}=e^{-j\frac{2\pi}{N}\cdot\frac{N}{2}}=e^{-j\pi}=-1 $  
3. 2 eingesetzt in 1:  
   $ W_{N}^{N/2}W_{N}^{r}=-W_{N}^{r} $

Dadurch kann die Anzahl der Multiplikationen halbiert und der Schmetterlingsgraph vereinfacht werden:  
$ X[r]=X_{1}[r]+W_{N}^{r}X_{2}[r], r=0,1,...,\frac{N}{2}-1 $
$ X[r+\frac{N}{2}]=X_{1}[r]-W_{N}^{r}X_{2}[r], r=0,1,...,\frac{N}{2}-1 $

![Schmetterlingsgraph vereinfacht](../Schmetterlingsgraph_vereinfacht.png)

### Vollst&auml;ndiger Schmetterlingsgraph
Vollständiger Schmetterlingsgraph mit Vereinfachung
![Schmetterlingsgraph vollstaendig](../Schmetterlingsgraph_vollstaendig.png)
