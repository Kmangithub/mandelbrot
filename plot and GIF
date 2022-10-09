#Import der benötigten Libraries
from PIL import Image, ImageDraw
from mandelbrot import mandelbrot, MAX_ITER

#Bildgröße in Pixeln
BREITE = 1000
HOEHE = 1000

#Anzahl Frames die erstellt werden
ANZAHL = 10

#Zoomfaktor zwischen den einzelnen Frames
ZOOM = 0.95

#Dargestelltes Intervall der komplexen Ebene (hier zentriert um den Punkt (-0.7463, 0.1102)
#Andere interessante Punkte findet man im Internet)
RE_START = -0.7463 -1.2
RE_ENDE = -0.7463 + 1.2
IM_START = 0.1102 - 1.2
IM_ENDE = 0.1102 + 1.2

#Liste an Frames
allebilder = []

#Beginn einer Schleife von 1 bis ANZAHL 
for j in range(1, ANZAHL):
    
    #Für jeden Frame wird der dargestellte Bereich verkleinert
    RE_START = -0.7463 - 1.2 * (ZOOM**j)
    RE_ENDE = -0.7463 + 1.2 * (ZOOM**j) 
    IM_START = 0.1102 - 1.2 * (ZOOM**j) 
    IM_ENDE = 0.1102 + 1.2 * (ZOOM**j) 
    
    #Erstellung eines Bilds des Typ RGB mit den Pixellängen BREITE und HÖHE, RGB 0 0 0
    im = Image.new('RGB', (BREITE, HOEHE), (0, 0, 0))

    #Zeicheninterface öffnen
    draw = ImageDraw.Draw(im)

    #Beginn Schleife von Pixel (0,0) bis Pixel (BREITE, HÖHE)
    for x in range(0, BREITE):
        for y in range(0, HOEHE):
            
            #Konvertierung von Pixelkoordinaten in eine komplexe Zahl c
            c = complex(RE_START + (x / BREITE) * (RE_ENDE - RE_START),
                         IM_START + (y / HOEHE) * (IM_ENDE - IM_START))

            #Berechnung der Iterationenzahl m von c
            m = mandelbrot(c)

            #Farbvariation basierend auf der Iterationenzahl, falls m < MAX_ITER
            if m < MAX_ITER: 
                r = 43 - int(m * 255 / MAX_ITER)
                g = 153 - int(m * 255 / MAX_ITER)
                b = 243 - int(m * 255 / MAX_ITER)

            #Feste Farbe falls Divergenz auch bei Iteration 200 nicht nachweisbar
            else: 
                r = 255
                g = 184
                b = 31

            #Aufmalen von Punkt x,y auf das Bild mit der zugewiesenen Farbe
            draw.point([x, y], (r, g, b))

    #im hinzufügen zu allebilder        
    allebilder.append(im)

    #Erstellen eines rekursiven Speicherformats nach Schema outputj.png
    speicher = 'outputneu{}.png'.format(j)
    im.save(speicher, 'PNG')

allebilder[0].save("C:\\Users\\jonas\\Mandelbrot3\\gifpython.gif", save_all=True, append_images=allebilder[1:], optimize=False, duration = 100, loop = 0)
