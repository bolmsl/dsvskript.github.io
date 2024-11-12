```python
import numpy as np
from PIL import Image
import IPython.display as display


```

# Fourier - Transformation
### vrl : 06

# Inhalt:

▪ Diskrete Fourier-Transformation 

▪ Grundlagen und Motivation 

▪ Fourier-Reihe 

▪ Fourier-Transformation


# Nutzung Der Fourier-Reihe

1.Messen der Spannung 
   
      ZB: wenn man wissen möchte, aus 50 Hz welche Frequenz(sin) hat (Spektum).
      
2.Die Frequenzen filtern
  
3.Die Darstellung des Spektrums des Signals

  
  

Wir nehmen den periodische Signale ,weil sie in der Natur sehr auftreten
die Fourier-Reihe wird verwendet, um Signale in ihre Frequenzkomponenten zu zerlegen und sie zu analysieren.



```python
from IPython.display import Image
Image(filename='Prisma_de_Newton.jpg')
```




    
![jpeg](/_static/lecture_specific/Fouriertransformation/output_5_0.jpg)
    



# Art der Fourier – Reihe

⦁	Fourier Zerlegung oder Fourier Analyse

⦁	Fourier Synthese ,um ursprüngliche Signal zu bilden


Signal ist eine Funktion

$x_p$(t) = $\frac{a_0}{2}$ +$\sum_{k=1}^\infty $ a_k * cos(2πf_0t) + a2 * cos(2π2f0t) + a3 * cos(2π3f0t) + ...

# Ein praktisches Beispiel
Audio Signal
Am Anfang ist ein sauber Sinus Signal   
Am Ende hat man andere Frequenzteile 


# ⦁	Köffezienten Berechnen
Anmerkung : Für Vereinfachung '&omega;' wird weggelassen

# ⦁	Rekapitulation Vereinbarung


$$\int_{-\pi}^{\pi}sin(mt)\,dt =0$$

Periodische Signal kann ich schreiben  als  konstante * die Summe von cos und sin


# a0 Rechnen


wie bilden das bestimmte integral der rechten Seite über das Interval[-pi,pi]:



```python
from IPython.display import Image
Image(filename='Screenshot (53).png')
#![aus der Vorlesung](Screenshot (53).png)
```




    
![png](/_static/lecture_specific/Fouriertransformation/output_15_0.png)
    



# ak Rechnen


```python
#![aus der Vorlesung](C:\Users\LENOVO\Desktop\Fourier Skript\Screenshot (54).png)
from IPython.display import Image
Image(filename='Screenshot (54).png')
```




    
![png](/_static/lecture_specific/Fouriertransformation/output_17_0.png)
    




```python
#![aus der Vorlesung](C:\Users\LENOVO\Desktop\Fourier Skript\Screenshot (56).png)
from IPython.display import Image
Image(filename='Screenshot (56).png')
```




    
![png](/_static/lecture_specific/Fouriertransformation/output_18_0.png)
    



# Fourier -Transformation

# ▪ Fourier-Transformation ist eine Erweiterung der Fourier-Reihe für aperiodische Signale mit 
unendlicher Periodendauer 𝑇0 → ∞, 𝜔 → 0

▪ Das Spektrum besteht nicht mehr aus absoluten Amplitudenwerten an diskreten Frequenzen 𝑛𝜔0
(also Vielfachen der Grundfrequenz), sondern es besteht aus der Amplitudendichte über einer kontinuierlichen Frequenzachse. 

(Gleiches gilt für die Phasen.)


```python
#![aus der Vorlesung]("C:\Users\LENOVO\Desktop\Fourier Skript\Screenshot (57).png")
from IPython.display import Image
Image(filename='Screenshot (57).png')
```




    
![png](/_static/lecture_specific/Fouriertransformation/output_21_0.png)
    



# Zweck Fourier Transformation


Die Fourier transformation macht die nicht sichtbare Funktion (bestimmte Information ) sichtbar 



```python
#![aus der Vorlesung]("C:\Users\LENOVO\Desktop\Fourier Skript\Screenshot (51).png")
from IPython.display import Image
Image(filename='Screenshot (51).png')
```




    
![png](/_static/lecture_specific/Fouriertransformation/output_24_0.png)
    



------>


```python
#![aus der Vorlesung]("C:\Users\LENOVO\Desktop\Fourier Skript\Screenshot (52).png")
from IPython.display import Image
Image(filename='Screenshot (52).png')
```




    
![png](/_static/lecture_specific/Fouriertransformation/output_26_0.png)
    



Fourier Transformation         
log(ab) = log a + log b

# Beispiel 1 



10. 10000 =10^5
Transformation in anderen Art
Über log(10.10000)
= log(10) + log(10000)
= 1 + 4 = 5


# Beispiel 2
# Laplace Transformation 

U(t) + Rc Uc(t) + Uc(t) 

----laplace--->    

U(s) = RcSUc(s) + LS²Uc(s)+Uc(s)    

Hintergrund Warum wir Fourier Transformation überhaupt brauchen?

Wir möchten etw rechnen (ZB ableiten) 

Durch diese Transformation wir könnten diese Signal von Domän (ZB Zeit Bereich) 
in andere Domän (ZB Frequenz Bereich) verwandel so können wir es einfacher rechnen.

# lernziele


 • Sie verstehen die Anwendung von Fourier in der Signalverarbeitung.
 
 • Sie wissen, wie periodische Signale durch Fourier-Reihen zerlegt werden können.
 
 • Sie können die Fourier-Reihe in der komplexen Form beschreiben.
 
 • Sie können das Prinzip der FourierTransformation nachvollziehen. 



# kontrollfragen

 ### Beschreiben Sie die Rolle von Fourier in der Signalverarbeitung anhand eines Beispiels. 

   (Audio Signal)
    
 ### Schreiben Sie die Gleichung der Fourier-Reihe für eine periodische Funktion in komplexer Form auf.

   Die Fourier-Reihe einer periodischen Funktion \(f(t)\) in komplexer Form zerlegt die Funktion in eine unendliche Summe von harmonischen Schwingungen.

 ### Beschreiben Sie den Unterschied zwischen Fourier-Reihe und Fourier-Transformation
   
   Fourier Reihe ist Periodisch Darstellung 
   Fourier -Transformation ist Apperiodisch Darstellung


#### alle photos sind aus der Vorlesung

##### judy Abou Rmeh & Julian Duchschere 
