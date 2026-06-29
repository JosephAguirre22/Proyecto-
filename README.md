# Proyecto-
Nombre: Joseph Stephano Aguirre Jurado
Fecha: 28 de Junio 2026
Tema: El impacto de las nuevas tecnologías en la sociedad: desarrollo de un generador de contraseñas
Objetivo del sistema

Desarrollar un programa que sirva para generar contraseñas de manera sensilla para el usuario unicamente haciendole preguntas sencillas}
<img width="556" height="780" alt="diagrama" src="https://github.com/user-attachments/assets/f640d134-a058-48a3-9303-99c1fcd6e24a" />
[juego.py](https://github.com/user-attachments/files/29451030/juego.py)
# Generador de contrasenas de autonomo 2

#el import random me ayuda con una libreria de python que permite hacer cosas al azar 
import random
from turtle import st

# requisitos de caracteres
mayusculas = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
minusculas = "abcdefghijklmnopqrstuvwxyz"
numeros = "0123456789"
simbolos = "!@#$%&*?-_;"

# Variable booleana que controla si el programa sigue
continuar = True

while continuar:
    print("-GENERADOR DE CONTRASENAS-")

    longitud = int(input("De cuantos caracteres la quieres? "))

    # Preguntar que tipos incluir (se guarda True o False)
    usar_mayus = input("Quieres mayusculas? (si/no): ").strip().lower() == "si"
    usar_minus = input("Quieres minusculas? (si/no): ").strip().lower() == "si"
    usar_nums = input("Quieres numeros? (si/no): ").strip().lower() == "si"
    usar_simbolos = input("Quieres simbolos? (si/no): ").strip().lower() == "si"

    # Juntar en un solo texto los caracteres elegidos
    permitidos = ""
    if usar_mayus:
        permitidos = permitidos + mayusculas
    if usar_minus:
        permitidos = permitidos + minusculas
    if usar_nums:
        permitidos = permitidos + numeros
    if usar_simbolos:
        permitidos = permitidos + simbolos

    # Revisar que se haya elegido al menos un tipo
    if permitidos == "":
        print("Tienes que elegir al menos un tipo de caracter.")
        continue

    # Crear la contrasena caracter por caracter con random.choice()
    contrasena = ""
    for i in range(longitud):
        contrasena = contrasena + random.choice(permitidos)

    print("Tu contrasena es:", contrasena)

    correcta = input("¿La contraseña está correcta? (si/no): ").strip().lower()
    if correcta == "si":
        continuar = False
    else:
        otra = input("Quieres generar otra? (si/no): ").strip().lower()
        if otra != "si":
            continuar = False

print("Listo, programa terminado.")
