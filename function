#Maximale Iterationenzahl bis zu welcher das Divergenzkriterium getestet wird
MAX_ITER = 200

#Erstellung der Mandelbrotfunktion mit dem komplexen Zahlenparameter c
def mandelbrot(c):

    #Start der Variablen z und n
    z = 0
    n = 0

    #Durchlauf der Rekursionsformel
    while abs(z) <= 2 and n < MAX_ITER:
        z = z*z + c
        n += 1
    
    #Ausgabe von n
    return n

#Testteil, der nur dann ausgeführt wird, wenn mandelbrot.py als main ausgeführt wird
if __name__ == "__main__":
    for a in range(-10, 10, 5):
        for b in range(-10, 10, 5):
            c = complex(a / 10, b / 10)
            print(c, mandelbrot(c))
