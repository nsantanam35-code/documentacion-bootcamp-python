# ESTRUCTURAS DE DATOS: DICCIONARIOS

> Autor: Alex Martinez (gambito700)
> Fecha: 16 de marzo de 2026
> Issue relacionada: #17

#========================================================================#

# definicion

# un diccionario es una estructura de datos que guarda datos en formato clave : valor
# en python existen 5 operaciones principales y 3 formas de recorrerlos:

# operaciones:
# crear    → define el diccionario con sus pares clave : valor
# acceder  → obtiene un valor usando su clave con ["clave"]
# modificar→ cambia el valor de una clave existente
# agregar  → agrega un nuevo par clave : valor
# eliminar → borra un par clave : valor con del o .pop()

# recorrido con for:
# keys     → itera solo las claves
# values   → itera solo los valores
# items    → itera claves y valores juntos

#========================================================================#

# para que sirve?

# sirven para organizar datos relacionados bajo un mismo nombre.
# son fundamentales porque permiten:

# 1. agrupar informacion: guardar multiples datos de una entidad en un solo objeto.
# 2. acceso directo: obtener cualquier valor al instante usando su clave.
# 3. modificar datos: actualizar, agregar o eliminar valores en cualquier momento.
# 4. recorrer informacion: iterar sobre claves, valores o ambos usando loops.

#========================================================================#

# sintaxis

#========================================================================#

# CREAR - estructura basica
# - variable        nombre del diccionario
# - "clave"         identificador del dato, siempre entre comillas si es string
# - valor           el dato almacenado, puede ser string, int, lista, etc.
# - {}              delimitan el diccionario
# - :               separa la clave del valor
# - ,               separa cada par clave-valor

persona = {
    "nombre"   : "carlos",
    "edad"     : 28,
    "direccion": "calle falsa 123",
    "ciudad"   : "valparaiso"
}

#========================================================================#

# ACCEDER a un valor con ["clave"]
# - persona["ciudad"]   accede al valor asociado a la clave "ciudad"
# - si la clave no existe lanza un KeyError

print(persona["ciudad"])

# resultado:
# valparaiso

#========================================================================#

# MODIFICAR un valor existente
# - se accede por clave y se asigna el nuevo valor con =
# - si la clave ya existe sobreescribe el valor anterior

persona["edad"]   = 35
persona["nombre"] = "carla"

# flujo completo:
# antes → persona["edad"]   = 28       → despues → persona["edad"]   = 35
# antes → persona["nombre"] = "carlos" → despues → persona["nombre"] = "carla"

#========================================================================#

# AGREGAR un dato nuevo
# - si la clave no existe python la crea automaticamente
# - la sintaxis es identica a modificar

persona["pais"]   = "chile"
persona["altura"] = 190

# resultado:
# persona = {
#     "nombre"   : "carla",
#     "edad"     : 35,
#     "direccion": "calle falsa 123",
#     "ciudad"   : "valparaiso",
#     "pais"     : "chile",
#     "altura"   : 190
# }

#========================================================================#

# ELIMINAR un dato - 2 formas
# - del              elimina la clave y su valor directamente
# - .pop("clave")    elimina la clave y ademas retorna el valor eliminado

# con del:
# - si la clave no existe lanza un KeyError
del persona["altura"]

# flujo completo:
# antes   → persona tiene la clave "altura" : 190
# del     → elimina el par "altura" : 190
# despues → persona ya no tiene la clave "altura"

# con .pop():
# - a diferencia de del, retorna el valor que elimino
# - si la clave no existe lanza un KeyError
valor_eliminado = persona.pop("pais")

# flujo completo:
# antes           → persona tiene la clave "pais" : "chile"
# .pop("pais")    → elimina el par y retorna "chile"
# valor_eliminado = "chile"
# despues         → persona ya no tiene la clave "pais"

#========================================================================#

# RECORRER con FOR - 3 formas
# - keys     for k in persona
# - values   for v in persona.values()
# - items    for k, v in persona.items()

#========================================================================#

# FOR iterando KEYS
# - por defecto iterar un diccionario devuelve sus claves
# - k   recibe cada clave en cada vuelta

for k in persona:
    print(k)

# flujo completo:
# vuelta 1 → k = "nombre"    → imprime "nombre"
# vuelta 2 → k = "edad"      → imprime "edad"
# vuelta 3 → k = "direccion" → imprime "direccion"
# vuelta 4 → k = "ciudad"    → imprime "ciudad"
# no hay mas claves → se detiene

#========================================================================#

# FOR iterando VALUES
# - .values()   devuelve unicamente los valores del diccionario
# - v           recibe cada valor en cada vuelta

for v in persona.values():
    print(v)

# flujo completo:
# vuelta 1 → v = "carla"           → imprime "carla"
# vuelta 2 → v = 35                → imprime 35
# vuelta 3 → v = "calle falsa 123" → imprime "calle falsa 123"
# vuelta 4 → v = "valparaiso"      → imprime "valparaiso"
# no hay mas valores → se detiene

#========================================================================#

# FOR iterando ITEMS
# - .items()   devuelve cada par como tupla (clave, valor)
# - k, v       dos variables que desempaquetan el par en el mismo for

for k, v in persona.items():
    print(k, v)

# flujo completo:
# vuelta 1 → k = "nombre",    v = "carla"           → imprime "nombre carla"
# vuelta 2 → k = "edad",      v = 35                → imprime "edad 35"
# vuelta 3 → k = "direccion", v = "calle falsa 123" → imprime "direccion calle falsa 123"
# vuelta 4 → k = "ciudad",    v = "valparaiso"      → imprime "ciudad valparaiso"
# no hay mas pares → se detiene

#========================================================================#

# EJERCICIO 1 - recorrer tu propio diccionario con las 3 formas
# crear un diccionario con datos propios y recorrerlo con keys, values e items

gambito = {
    "nombre" : "alex",
    "edad"   : 34,
    "ciudad" : "mallolafken"
}

for k in gambito:
    print(k)

for v in gambito.values():
    print(v)

for k, v in gambito.items():
    print(k, v)

# flujo completo keys:
# vuelta 1 → k = "nombre" → imprime "nombre"
# vuelta 2 → k = "edad"   → imprime "edad"
# vuelta 3 → k = "ciudad" → imprime "ciudad"

# flujo completo values:
# vuelta 1 → v = "alex"      → imprime "alex"
# vuelta 2 → v = 34          → imprime 34
# vuelta 3 → v = "mallolafken"→ imprime "mallolafken"

# flujo completo items:
# vuelta 1 → k = "nombre", v = "alex"        → imprime "nombre alex"
# vuelta 2 → k = "edad",   v = 34            → imprime "edad 34"
# vuelta 3 → k = "ciudad", v = "mallolafken" → imprime "ciudad mallolafken"

#========================================================================#

# EJERCICIO 2 - for + if + acceso por clave
# dada una lista de diccionarios de alumnos
# imprimir solo los que tengan edad mayor a 20

alumnos = [
    {"nombre": "ana",    "edad": 19},
    {"nombre": "carlos", "edad": 23},
    {"nombre": "luis",   "edad": 17},
    {"nombre": "maria",  "edad": 21}
]

for alumno in alumnos:
    if alumno["edad"] > 20:
        print(alumno["nombre"], alumno["edad"])

# flujo completo:
# vuelta 1 → alumno["edad"] = 19 → 19 > 20 → False → no imprime
# vuelta 2 → alumno["edad"] = 23 → 23 > 20 → True  → imprime "carlos 23"
# vuelta 3 → alumno["edad"] = 17 → 17 > 20 → False → no imprime
# vuelta 4 → alumno["edad"] = 21 → 21 > 20 → True  → imprime "maria 21"

#========================================================================#

# PROYECTO PRACTICO: lista de peliculas

# ejemplo real usando una lista de diccionarios
# cada pelicula es un diccionario
# todas las peliculas se guardan en una lista

# estructura de datos:
# pelicula  = { "nombre": nombre, "anio": anio, "genero": genero }
# peliculas = [ pelicula1, pelicula2, ... ]

peliculas = []

while True:
    print("menu")
    print("1. agregar pelicula")
    print("2. borrar pelicula")
    print("3. ver lista")
    print("4. buscar pelicula")
    print("5. salir")

    opcion = input("ingrese la opcion: ")

    if opcion == "1":
        nombre = input("nombre de la pelicula: ")
        genero = input("genero de la pelicula: ")
        anio   = input("anio de la pelicula: ")

        pelicula = {
            "nombre" : nombre,
            "anio"   : anio,
            "genero" : genero
        }
        peliculas.append(pelicula)
        print("pelicula guardada!")

    elif opcion == "2":
        peli_borrar = input("nombre de la peli a borrar: ")

        for peli in peliculas:
            if peli["nombre"] == peli_borrar:
                peliculas.remove(peli)
                print("peli borrada!")
                break

    elif opcion == "3":
        for peli in peliculas:
            print(peli["nombre"], "-", peli["anio"], "-", peli["genero"])

    elif opcion == "4":
        peli_buscar = input("nombre de la peli a buscar: ")
        encontrada  = False

        for peli in peliculas:
            if peli["nombre"] == peli_buscar:
                print("nombre :", peli["nombre"])
                print("anio   :", peli["anio"])
                print("genero :", peli["genero"])
                encontrada = True
                break

        if not encontrada:
            print("pelicula no encontrada")

    elif opcion == "5":
        print("programa terminado!")
        break

    else:
        print("opcion no valida, intenta de nuevo")
#        break

# flujo completo:
# opcion 1 → pide datos → crea diccionario → append a la lista → mensaje confirmacion
# opcion 2 → pide nombre → recorre lista   → encuentra y borra → break
# opcion 3 → recorre lista → imprime nombre, año y genero de cada peli
# opcion 4 → pide nombre → recorre lista   → si encuentra imprime datos → si no "no encontrada"
# opcion 5 → imprime mensaje → break → programa termina
# otro     → mensaje de error → reinicia el menu

#========================================================================#

# ERROR COMUN - TypeError al acceder mal la lista de diccionarios
# dentro de un for sobre una lista de diccionarios
# la variable del for es cada diccionario individual, no la lista completa

# incorrecto:
# for peli in peliculas:
#     print(peliculas["nombre"])   → TypeError: list indices must be integers, not str
#                                      TypeError: los indices de una lista deben ser enteros, no str
#
# por que falla:
# peliculas   es la lista → no se accede con ["nombre"]
# peli        es el diccionario de esa vuelta → este si acepta ["nombre"]

# correcto:
# for peli in peliculas:
#     print(peli["nombre"])        → imprime el nombre de cada pelicula

# flujo del error:
# peliculas = [ {pelicula1}, {pelicula2} ]
# peliculas["nombre"] → python intenta buscar el indice "nombre" en una lista  → TypeError
# peli["nombre"]      → python busca la clave "nombre" en el diccionario       → correcto

#========================================================================#

# FIN