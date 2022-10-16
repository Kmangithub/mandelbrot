# mandelbrot
Erstellung einer Mandelbrot-Zoom-Animation im GIF Format (Python)

Benötigte Packages: 
  PIL

Animationsparameter:
  
  (mandelbrot.py) MAX_ITER = Folgenglied, bis zu dem auf Divergenz geprüft wird
  
  (zoom.py)       BREITE = Breite der erstellten Bilder in Pixeln
                  HOEHE = Höhe der erstellten Bilder in Pixeln
                  ANZAHL = Anzahl insgesamt in der Animation enthaltenen Bilder
                  ZOOM = Faktor um den das dargestellte Intervall von Bild zu Bild verkürzt wird
                  RE_START = linkes Ende Startintervall
                  RE_ENDE = rechtes Ende Startintervall
                  IM_START = unteres Ende Startintervall
                  IM_ENDE = oberes Ende Startintervall
                  allebilder = Liste in der die erstellten Bilder landen
                  r,g,b = Farbwerte im RGB Format
                  duration = Anzeigedauer einzelner Bilder in Milisekunden
                  loop = Wiederholungsanzahl der Animation, 0 bedeutet fortlaufend
                  
Benutzungsanleitung: 
  installiere PIL
  lade mandelbrot.py und zoom.py in einen Ordner
  ändere den Speicherpfad in Zeile 73 in den Ordnerpfad
  passe deine Animationsparameter an
  Starte das Skript
  warte :D
  
  
  





