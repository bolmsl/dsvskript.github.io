# Digitale Signalverarbeitung
<h2>Einführung in die Digitale Signalverarbeitung<h2>

 <h3><strong><u> Motivation: <em></u>Wieso beschäftigen wir uns mit Digitalen Signalverarbeitung?</strong></em></h3><br>

 <p><em>1. Kommunikationssysteme:</em><br>
 Die Digitale Signalverarbeitung spielt eine zentrale Rolle in modernen Kommunikationssystemen wie Mobilfunknetzen, WLAN, Satellitenkommunikation und Breitbandinternet.<br>

 <em>2. Bild-und Videobearbeitung:<br></em>
  In der Bild- und Videoverarbeitung werden DSP-Techniken eingesetzt, um Bilder und Videos zu verbessern, zu komprimieren, zu analysieren und zu verarbeiten. Anwendungen reichen von medizinischen Bildgebungsverfahren über Überwachungssysteme bis hin zu Videokonferenzsystemen.<br>

  <em>3. Automobiltechnik</em><br>
  In modernen Fahrzeugen werden DSP-Algorithmen für verschiedene Anwendungen eingesetzt, darunter Spracherkennungssysteme, Bildverarbeitungssysteme für Fahrerassistenzsysteme, Aktive Geräuschunterdrückung (ANC) und Audioverarbeitungssysteme.<br>


![Einparkhilfe](/_static/lecture_specific/Bilder_fur_Einfuerung/Einparkhilfe.png)



  <em>4. Instrumentierung und Regelungstechnik:</em><br>
  In der Instrumentierung und Regelungstechnik werden DSP-Algorithmen verwendet, um Sensordaten zu verarbeiten, Steuersignale zu generieren und Regelungssysteme zu entwerfen, z.B. für Robotik, Automatisierung, Luftfahrt und industrielle Prozesssteuerung.


![Luftfahrt](/_static/lecture_specific/Bilder_fur_Einfuerung/Luftfahrt.png)<br>

<h3><strong><u>Matlab/Simulink</h3></strong></u>
<em>Welche Alternative zu Phyton, um digitale Signale Darzustellen ?</em><br>

<em>MATLAB:</em><br>
<ul> 
<li>In Matlab können digitale Signale mithilfe von Befehlen und Funktionen für die Datenvisualisierung dargestellt werden</li>
<li>Zum Beispiel kann man mit den Befehlen plot, stem, subplot und imshow digitale Signale in Form von Zeitbereichsplots, Spektrumanalysen, Augendiagrammen und anderen Diagrammtypen visualisieren.</li>
<li>Zum Plotten eines einfachen digitalen Signals x gegen die Zeit t kann man den Befehl plot(t, x) verwenden. Für diskrete kann man den Befehl stem(n, x) verwenden, wobei n die Zeitpunkte der Abtastung und x die Abtastwerte sind.</li>
<li>MATLAB bietet auch eine Vielzahl von Funktionen zur Signalverarbeitung und Analyse, mit denen man z.B. digitale Signale filtern, transformieren und spektral analysieren kann
 </ul>
 <br>

 <em>Simulink</em><br>
 <ul>
 <li>In Simulink werden digitale Signale mithilfe von Blöcken modelliert, die verschiedene Signalquellen, Verarbeitungsalgorithmen und Ausgabegeräte darstellen.</li
 >
 <li>Um ein digitales Signal zu modellieren und zu visualisieren, erstellt man ein Simulink-Modell, fügt Signalquellen und Verarbeitungsblöcke hinzu und verbindet diese entsprechend.
 Um die Signale während der Simulation darzustellen, verwendet man am Ende des Modells einen Scope-Block. </li><br>
 <li>Simulink bietet auch spezielle Blöcke für die digitale Signalverarbeitung, wie z.B. Filterblöcke, FFT-Blöcke und DSP-Toolbox-Blöcke, die für die Verarbeitung und Analyse digitaler Signale in Echtzeit verwendet werden können</li>

 <h3><em><strong>Signale</em></h3></strong>
<em>Definition:</em> Ein Signal ist eine Informationstragende physikalische Größe, die zeitlich veränderbar ist <br><br>
Beispiele für Informationsträger:
<ul>
<li>Sprache, Musik</li>
<li>Bilder und Videos</li>
<li>Funksignale</li>
<li>medizinische Signale</li>
<br></ul>



<em>Weitere Definitionen:</em><br><ul><li>
Ein Signal ist eine physikalische Größe, die Informationen trägt und durch eine oder mehrere unabhängige Variablen dargestellt wird</li>
<li>
Es ist eine mathematische Funktion von mindestens einer unabhängigen Variablen, wie Zeit, Raum usw.</li></ul>

Beispiele für <strong> eine unabhängige Variable</strong> sind:<br>
> elektrische Größen wie Stromstärke oder Spannung über die Zeit 
𝑡  (𝑢(𝑡),𝑖(𝑡)) und Kryptoindizes über Wochen/Monate/Jahre 𝑛(𝑑(𝑛)).<br>

Beispiele für <strong> mehrere unabhängige Variablen</strong> sind:<br>

>Grauwert: Helligkeit oder Intensität eines Bildes über den Raumkoordinaten 𝑥 und 𝑦 : 𝐼(𝑥, 𝑦) <br>

>Schalldruck an den Raumkoordinaten 𝑥, 𝑦 und z über die Zeit 𝑡: 𝑝(𝑥, 𝑦, 𝑧,𝑡)

<em><h3><strong>Zeitkontinuierliche vs. diskrete Signale</em></h3></strong>

<u>Kontinuierliche Siganle</u><br>

<em>Definition:</em>  Ein kontinuierliches Signal ist eine Funktion, die über einen kontinuierlichen Bereich von Zeit oder Raum definiert ist<br>

Beispiel:

>Die Spannung an einem elektrischen Stromkreis, die kontinuierlich variiert, während sie über die Zeit gemessen wird. Mathematisch kann dies als 
𝑢
(
𝑡
)
u(t) dargestellt werden, wobei 
𝑡
t die Zeit ist und 
𝑢
u die Spannung

<u>Zeitdiskrete Signale</u><br>

<em>Definition:</em>Ein diskretes Signal ist eine Funktion, die nur an diskreten Punkten im Zeit- oder Raumkontinuum definiert ist.

Beispiel:<br>

> Die Anzahl der Autos, die eine Mautstelle pro Stunde passieren, wobei die Zählung nur zu bestimmten Zeitpunkten erfolgt. Mathematisch kann dies als 
𝑐
[
𝑛
]
c[n] dargestellt werden, wobei 
𝑛
n diskrete Zeitpunkte sind und 
𝑐
c die Anzahl der Autos ist.

<em><strong><h3>Periodische vs. aperiodische Signale</h3></em></strong>

<u>Periodische Signale</u>

<em>Definition:</em>Periodische Signale sind Signale, die sich regelmäßig wiederholen und eine bestimmte Periode haben.

Signalwiederholung in festem Abstand<ul>
<li> 𝑥 𝑡 + 𝑇 = 𝑥 𝑡 , t, T ∈ ℝ (kontinuierlich)</li>
<li>
 𝑥 𝑛 + 𝑁 = 𝑥[𝑛], 𝑛 ∈ ℤ , 𝑁 ∈ ℕ (diskret)</li>
 <strong>(Grund-)Periode</strong>: Das kleinste 𝑇0 bzw. 𝑁0, sodass:
<li>𝑥 𝑡 + 𝑇0 = 𝑥 𝑡 (kontinuierlich)</li>
<li>
 𝑥 𝑛 + 𝑁0 = 𝑥 𝑛 (diskret)</li>
<li>
 <strong>Frequenz</strong>: Kehrwert 𝑓 =1/T</li></ul>


Beispiel:<br>
>Periodische Impulse oder periodische Funktionen mit einer klar definierten Wiederholungszeit

<u>Aperiodische Signale</u>

<em>Definition</em>: Aperiodische Signale sind Signale, die sich nicht regelmäßig wiederholen und keine klare Periodizität aufweisen.

Beispiel:

>Stochastische Signale: Signale, die zufällig sind und keine bestimmte periodische Struktur aufweisen, wie Rauschen oder zufällige Prozesse.

<h3><em><strong>Deterministisch vs. stochastische Signale</h3></em></strong>

<u>Deterministische Signale</u>

<em>Definition:</em> Deterministische Signale sind Signale, bei denen die Werte zu jedem Zeitpunkt eindeutig und vorhersagbar sind. Sie können durch mathematische Formeln oder deterministische Prozesse genau beschrieben werden.

Beispiel:
>Exponentiell abklingende Signale: Signale, die durch einfache exponentielle Funktionen wie 
𝑥
(
𝑡
)
=
𝑒
−
𝛼
𝑡
x(t)=e 
−αt
  beschrieben werden können.

  <u>Stochastische Signale:</u>

  <em>Definition</em>: stochastische Signale sind Signale, bei denen die Werte zu jedem Zeitpunkt zufällig sind und nicht genau vorhersagbar sind. Sie können durch statistische Verteilungen oder stochastische Prozesse beschrieben werden.
  
  Beispiel:
  >Rauschsignale: Signale, die zufällige Schwankungen oder Störungen aufweisen, wie thermisches Rauschen in elektronischen Schaltungen oder atmosphärisches Rauschen in Kommunikationssystemen.
  
  <h3><em><strong>Eindimensionale vs. mehrdimensionale Signale</h3></em></strong>

  <u>Eindimenionale Signale</u>

  <em>Definition</em>: Eindimensionale Signale sind Signale, die entlang einer einzigen unabhängigen Variablen definiert sind, wie Zeit, Entfernung oder eine andere skalare Größe.

  Beispiel:
  >Zeitabhängige Signale: Signale, die sich nur über die Zeit ändern, wie Audioaufnahmen, Musikstücke oder Bewegungssensordaten.

  <u>Mehrdimensionale Signale</u>

  <em>Definition</em>: Mehrdimensionale Signale sind Signale, die entlang mehrerer unabhängiger Variablen definiert sind, wie Raumkoordinaten, mehrere Frequenzen oder mehrere Kanäle.

  Beispiel:
  >Bildsignale: Signale, die sowohl in horizontaler als auch in vertikaler Richtung (Pixel) variieren, wie Fotografien, medizinische Bilder oder Satellitenbilder.

![Ein-MehrdimensionaleSignale](/_static/lecture_specific/Bilder_fur_Einfuerung/Ein-MehrdimensionaleSignale.png)



<h3><em><strong>Was ist digitale Signalverarbeitung?</h3></em></strong>

<em>Definiton:</em> Ist ein Bereich der Ingenieurwissenschaften und der Informatik, der sich mit der Analyse, Modellierung, Verarbeitung und Interpretation von Signalen befasst

Analyse:
>Signalverarbeitung beinhaltet die Untersuchung von Signalen, um deren Eigenschaften, Muster und Strukturen zu verstehen. Dies umfasst die Bestimmung von Signalparametern wie Amplitude, Frequenz, Phase und Zeitdauer.

Modellierung:
>Es beinhaltet die Entwicklung von mathematischen Modellen und Algorithmen, die Signalverhalten und -eigenschaften beschreiben können. Diese Modelle werden verwendet, um Signale zu analysieren, zu synthetisieren und zu interpretieren.

Verarbeitung:
> Signalverarbeitung umfasst verschiedene Techniken zur Manipulation und Transformation von Signalen, um bestimmte Ziele zu erreichen. Dies kann Filterung, Frequenzanalyse, Zeit-Frequenz-Analyse, Codierung, Dekodierung, Rauschunterdrückung und mehr umfassen.

Interpretation:
>Nach der Verarbeitung werden die resultierenden Signale interpretiert, um Informationen zu extrahieren und Entscheidungen zu treffen. Dies kann die Erkennung von Mustern, die Klassifizierung von Objekten, die Vorhersage von Trends oder die Steuerung von Systemen umfassen.

Wozu Braucht man sie?:
<ul>
<li>
Speicherung</li>
<li>Rekonstruktion</li>
<li>Trennung von Nutzsignal (Information) und Rauschen</li>
<li>Kompression</li>
<li>Merkmalextraktion für Klassifikation</li>
</ul>

<em><h3><strong>Analoge Signalverarbeitungskette</h3></em></strong>

![Analoge Signalverarbeitungskette](/_static/lecture_specific/Bilder_fur_Einfuerung/analogeSignalverarbeitungskette.png)


<em>Beschreibung:</em> Bei einer analogen Signalverarbeitungskette werden die analogen Einganssignale nur durch analoge Schaltungen wie Verstärker, Widerstände oder Kondensatoren beeinflusst und dann als analoges Ausgangssignal ausgegeben.

<em><h3><strong>Digitale Signalverarbeitungskette</h3></em></strong>

![Digitale Signalverarbeitungskette](/_static/lecture_specific/Bilder_fur_Einfuerung/digitaleSignalverarbeitungskette.png)


<em>Beschreibung</em>:Bei der digitalen Signalverarbeitungskette werden die Signale zunächst durch Umwandler digitalisiert und anschließend wieder zu einem analgoen Signal umgewandelt. Die wesentliche Signalverabeitung passiert dabei durch den Digitalprozessor, der das Signal noch vor der Umwandlung zu einem analogen Signal, bearbeitet.

<em><h3><strong>Eigenschaften der digitalen Signalverarbeitung</h3></em></strong>

<ul><u>Vorteile</u>
<li>Präzision und Hohe Genauigkeit bei großer 
Wortbreite</li>
<li> Reproduzierbarkeit</li>
<li>Hohe Zuverlässigkeit</li>
<li>Geringe Störempfindlichkeit</li>
<li>Flexibilität</li>
<li>Skalierbarkeit</li>
</ul>

<ul><u>Nachteile</u>
<li>Zusätzlicher Schaltungsaufwand (A/D- und D/A-Wandlung)</li>
<li>Rechenleistung</li>
<li>Verzögerung</li>
<li>Samplinfehler</li>
<li>Quantisierungsfehler</li>
<li>Signalrauschen</li>
</ul>

<h3><em><strong>Realisierungsmöglichkeiten</h3></em></strong>

<strong>Allzweck-Rechner</strong> (PCs, Workstation, 
Großrechner, Supercomputer, …)
<ul>
<li>Sehr flexibel, Teuer, Schnell einsetzbar, Hohe Leistungsaufnahme, 

Nähe zwischen Entwicklungsumgebung 
und Betriebsumgebung
</li>
</ul>


<strong>DSP</strong>
<ul>
<li>Weniger Flexibilität
, Höhere Geschwindigkeit
, Höherer Entwicklungsaufwand,

 Optimierte Architektur für 
Signalverarbeitung
</li>
</ul>

<strong>Mikroprozessoren</strong>
<ul>
<li>Mittlere Flexibilität,
 Mittlere Geschwindigkeit,
Geringer Entwicklungsaufwand,
Günstig
</li>
</ul>

<strong>Spezialschaltungen </strong> (ASICs, FPGAs)
<ul>
<li>Hohe Geschwindigkeit,

Hohe Parallelisierbarkeit,         
Hohe Entwicklungskosten und 
Entwicklungsdauer
</li>
</ul>

<h3><em><strong>Fazit</h3></em></strong>

- Digitale Signalverarbeitung befasst sich mit der Analyse, Modellierung und Verarbeitung von Signalen
  
- Sie spielt eine entscheidende Rolle in zahlreichen Anwendungen wie Telekommunikation, Medizintechnik und Bildverarbeitung. 
- Wichtige Signalarten sind kontinuierliche und diskrete, periodische und aperiodische, deterministische und stochastische, eindimensionale und mehrdimensionale Signale

- Durch die richtige Signalverarbeitung können Muster erkannt, Trends vorhergesagt und komplexe Probleme gelöst werden





















 



