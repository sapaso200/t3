# t3
import math
import random


def calcular_area_interseccion():
    print("=== ESTIMACIÓN DE ÁREA POR MÉTODO DE MONTECARLO ===")

    a = float(input("Ingrese el valor de a (semieje mayor elipse): "))
    b = float(input("Ingrese el valor de b (semieje menor elipse): "))
    c = float(input("Ingrese el valor de c (parámetro hipérbola): "))
    d = float(input("Ingrese el valor de d (parámetro hipérbola): "))
    n_puntos = int(input("Ingrese la cantidad de puntos aleatorios: "))

    puntos_elipse = 0
    puntos_interseccion = 0

    for _ in range(n_puntos):
        x = random.uniform(-a, a)
        y = random.uniform(-b, b)

        en_elipse = (x**2 / a**2) + (y**2 / b**2) <= 1

        if en_elipse:
            puntos_elipse += 1
  
            en_hiperbola = (x**2 / c**2) - (y**2 / d^2) >= 1

            if en_hiperbola:
                puntos_interseccion += 1

    area_elipse_teorica = math.pi * a * b

    if puntos_elipse > 0:
        area_interseccion_estimada = (
            puntos_interseccion / puntos_elipse
        ) * area_elipse_teorica
    else:
        area_interseccion_estimada = 0.0

    print("\n--- RESULTADOS ---")
    print(f"Puntos dentro de la elipse: {puntos_elipse}")
    print(f"Puntos en la intersección: {puntos_interseccion}")
    print(f"Área teórica de la elipse: {area_elipse_teorica:.4f}")
    print(
        f"Área estimada de la intersección: {area_interseccion_estimada:.4f}"
    )


if __name__ == "__main__":
    calcular_area_interseccion()
