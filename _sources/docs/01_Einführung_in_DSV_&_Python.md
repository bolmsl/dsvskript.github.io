# Signale und Signalverarbeitung

# 1.1 Signal
## Definition:

> Ein Signal ist eine übertragene Information oder ein Zustandsträger,
> der in verschiedenen Formen wie elektrisch, akustisch oder visuell
> auftreten kann. Signale dienen der Übermittlung von Nachrichten, Daten
> oder Steuerungsinformationen von einem Sender zu einem Empfänger. Sie
> können verschiedene Eigenschaften wie Amplitude, Frequenz und Phase
> aufweisen, um Informationen zu transportieren oder auf Veränderungen
> in einem System oder der Umgebung hinzuweisen.

 - Informationstragende, physikalische Größe, die sich über eine Variable (Zeit, Raum,…) ändert

-   Informationsträger: Sprache, Musik, Bilder, Videos, Funksignale, Druck, Temperatur, elektrische Spannung,…
-   Beschreibung als mathematische Funktion mindestens einer unabhängigen Variable
## 
-   **Wertkontinuierlich**: in einem Wertebereich alle Werte möglich
-   **Wertdiskret**: Eine Größe oder ein Signal nur in bestimmten festgelegten Werten existiert
-   **Zeitkontinuierlich**: über einen Zeitraum kontinuierlich definiertes Signal
-   **Zeitdiskret**: äquidistanten Zeitpunkten abgetastetes zeitkontinuierliches Signal

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/Signale.png)

## (Grund-)Periode

> Kleinste Zeit, bis sich ein Signal wiederholt.

$$ T_0$$
$$ f = 1/T_0$$

## Kontinuierliches Signal
> Stufenloser, unterbrechungsfreier Verlauf.

$$ t \in \R $$

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/Kontinuierliches_Signal.png)

## Diskretes Signal
> Zu äquidistanten Zeitpunkten (Konstante) abgetastetes kontinuierliches Signal.
> => Folge von Diskreten Werten

$$ x[n], n \in \R$$

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/Diskretes_Signal.png)

## Deterministisches Signal

> Ein deterministisches Signal ist ein Signal, bei dem die Werte zu
> jeder Zeit genau vorhersehbar sind und keine zufälligen oder
> unvorhersehbaren Komponenten enthält.

-   **Periodische Signale**: Sinus, Rechteck,…

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/Deterministisches_Signal.png)

## Periodisches Signal

> Signalwiederholung in festem Abstand.

$$ x(t + T) = x(t)$$
$$x[n +T] = x[n]$$

## Aperiodisches Signal
  > Signalwiederholung in keinem festem Abstand

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/Aperiodisches_Signal.png)
  
## Stochastisches Signal

> Ein stochastisches Signal ist ein Signal, bei dem die Werte zu
> verschiedenen Zeiten nicht genau vorhersagbar sind und zufällige oder
> unvorhersehbare Komponenten enthält. Es kann statistischen Mustern
> oder Wahrscheinlichkeiten folgen und ist nicht deterministisch.

-   **Rauschen**
-   **Stochastische Störungen**: Wackelkontakt, Umgebungsgeräusche
-   **Sprachsignal**

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/Stochastisches_Signal.png)

## n-dimensionales Signal

> Dimension des Signals ist abhängig von der Anzahl der Variablen des
> Signals.

- Eindimensional: Audiosignal u(t)
- Zweidimensional: Bild I(x, y)
- Dreidimensional: Video I(x, y, t)

# 1.2 Signalverarbeitung

>Verarbeitung eines Signals mit einem System

-   **Analyse**
-   **Modifikation**: Filterung, Interpolation, Geräuschreduktion (Rauschentfernung), Entzerrung
-   **Prädiktion**: Schätzung, Vorhersage (Rekonstruktion)
-   **Transformation** in eine andere Domäne: Fourier

## Digitale Signalverarbeitung 
>Die digitale Signalverarbeitung (DSP) ist ein Bereich der Elektrotechnik und Informatik, der sich mit der Verarbeitung und Analyse von Signalen in digitaler Form befasst. Hierbei werden mathematische Algorithmen auf digitale Signale angewandt, um sie zu filtern, zu analysieren, zu komprimieren oder zu transformieren. DSP findet in verschiedenen Anwendungen Anwendung, darunter Kommunikation, Bildverarbeitung, Audioverarbeitung und Steuerungssysteme.

- **Eingang & Ausgang**: Analog
- **Signalverarbeitung** dazwischen: digital
- **Umwandlung**: A/D & D/A

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/digitale_signalverarbeitung.png)
1.  Analoges Eingangssignal
2.  Analoge Vorverarbeitung
3.  A/D Umwandlung
4.  Verarbeitung durch Digitalprozessor
5.  D/A Umwandlung
6.  Analoge Nachbearbeitung
7.  Analoges Ausgangssignal

|Vorteile| Nachteile  |
|--|--|
|Präzision | Zusätzlicher Aufwand (A/D, D/A)|
|Reproduzierbarkeit| Rechenaufwand|
|Zuverlässigkeit| Verzögerung|
|Geringe Störempfindlichkeit | Signalrauschen|
|Flexibilität: for i in range(5-11)|

## Analoge Signalverarbeitung
>Analoge Signalverarbeitung bezieht sich auf die Verarbeitung von kontinuierlichen, nicht-digitalen Signalen, bei denen Informationen durch stetige Änderungen von physikalischen Eigenschaften wie Spannung oder Strom übertragen werden. Dieser Prozess kann beispielsweise in analogen Schaltkreisen erfolgen und umfasst Operationen wie Verstärkung, Filterung und Modulation, um Signale zu manipulieren oder anzupassen.
- **Eingang und Ausgang**: analog
- **Signalverarbeitung** dazwischen: analog
- **Umwandlung**: keine

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/analoge_signalverarbeitung.png)

1.  Analoges Eingangssignal
2.  Verarbeitung durch analoge Schaltung
3.  Analoges Ausgangssignal
## Digitales System
>System, auf dessen Hardware durch eine Software-Realisierung eine Signalverarbeitung umgesetzt wird

-   Zusätzlich die Konvertierung von der analogen zur digitalen Domäne und zurück
-   Zusätzlich eine mathematische Beschreibung der signalverarbeitenden Operation

![](/_static/lecture_specific/01_Vorlesungen_Script_Images/closed-loop-system.png)
