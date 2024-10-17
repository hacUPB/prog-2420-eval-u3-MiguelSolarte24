[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/MuElT52l)
# Unidad 3
---
## Documentación del proyecto
Nombre:  Miguel Solarte Pabon
ID:  000493594
---

#salas disponibles y ocupadas
salas_ocupadas = []

salas = {'Sala A1': 10, 'Sala A2': 10, 'Sala A3': 10, 'Sala A4': 10, 'Sala A5': 10}

funciones = {'Sala A1': 'Dracula', 'Sala A2': 'Frankenstein', 'Sala A3':'El Exorcista'}

precios = {'Sala A1': 20000, 'Sala A2': 15000, 'Sala A3': 7000, 'Sala A4': 10000, 'Sala A5': 10000}

def comprar_asientos(sala, cantidad,funcion):
    if sala in salas:
        if salas[sala] >= cantidad:
            salas[sala] -= cantidad
            precio = cantidad * precios[sala]
            print(f'Se han comprado {cantidad} asientos para la sala {sala} para la funcion {funcion}')
            print(f'Quedan {salas[sala]} asientos disponibles en la sala {sala}')
            print(f'El precio total es de ${precio}')
        elif salas[sala] == 0:
            salas_ocupadas.append(sala)
            print(f'No hay asientos disponibles en la sala {sala}')
        else:
            print(f'No hay suficientes asientos disponibles en la sala {sala}')
    else:
        print(f'La sala {sala} no existe')


def mostrar_asientos():
    print('Asientos disponibles:')
    for sala, asientos in salas.items():
        print(f'{sala}: {asientos} asientos disponibles')
        print('Asientos ocupados:')
        for sala in salas_ocupadas:
            print(f'{sala}: Esta sala se encuentra ocupada')

comprar_asientos('Sala A1', 3, 'Dracula')
comprar_asientos('Sala A2', 3, 'Frankesntein')
comprar_asientos('Sala A3', 10, 'El Exorcista')
comprar_asientos('Sala A3', 1, 'El Exorcista')
