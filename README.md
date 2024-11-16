# Bot-de-reciclaje
import random
from discord.ext import commands
import time
#permisos
intents = discord.Intents.default()
intents.message_content = True
# Listas de consejos y retos
consejos = [
    "Usa frascos de vidrio para almacenar alimentos en lugar de plásticos. ",
    "Lleva bolsas reutilizables al supermercado para evitar el plástico. ",
    "Minimizar el desperdicio de alimentos.. ",
    "Reutiliza los tarros de mermelada como recipientes para especias o sobras.",
]


tareas = [
    "Evita plásticos de un solo uso. Lleva un termo y cubiertos reutilizables.",
    "Comienza a separar residuos orgánicos y haz compostaje en casa.",
    "Reduce tu consumo de papel, usa versiones digitales siempre que sea posible.",
    "Haz una limpieza en casa y dona lo que no uses en lugar de tirarlo.",
]

def mostrar_menu():
    print("\n Bienvenido a EcoReducer")
    print("1. Consejos rápidos")
    print("2. Reto semanal")
    print("3. Pregunta sobre residuos")
    print("4. Salir")


def generar_consejo():
    consejo = random.choice(consejos)
    mostrar_proceso("Generando un consejo rápido...")
    print(f"Consejo: {consejo}")

def generar_reto():
    reto = random.choice(retos)
    mostrar_proceso("Buscando un reto para esta semana...")
    print(f"Reto: {reto}")


def responder_pregunta(pregunta):
    mostrar_proceso("Pensando en la respuesta...")
    if "café" in pregunta:
        return "¡Buena pregunta! Usa los restos de café como abono para plantas o exfoliante natural."
    elif "aceite" in pregunta:
        return "Guarda el aceite usado en botellas y llévalo a un centro de reciclaje. Nunca lo tires al desagüe."
    elif "plástico" in pregunta:
        return "Lava y seca los plásticos antes de reciclarlos. Los centros de acopio suelen aceptarlos limpios y secos."

    elif "otras cosas" in pregunta:
    "Usa las cosas reutilizables que no uses para hacer cosas geniales"

    else:
        return "No tengo una respuesta específica, pero investigaré más sobre eso. "

def mostrar_proceso(mensaje):
    #Simula un proceso con un mensaje y una pausa.
    print(f"\n{mensaje}")
    time.sleep(1.5) 


def eco_reducer_bot():
    while True:
        mostrar_menu()
        opcion = input("\nElige una opción: ")

        if opcion == "1":
            generar_consejo()
        elif opcion == "2":
            generar_reto()
        elif opcion == "3":
            pregunta = input("\nEscribe tu pregunta: ")
            respuesta = responder_pregunta(pregunta)
            print(f"\n{respuesta}")
        elif opcion == "4":
            print("\n¡Gracias por cuidar el planeta! Con estos pequeñas cosas faciles de hacer ayudas a cuidar el mundo. Hasta pronto.")
            break
        else:
            print("\nPor favor, elige una opción válida (1, 2, 3 o 4).")    

eco_reducer_bot()

bot.run(("5a842abe16a28149bbd7f909459003c3ecdfedb2412f6553249843d45d613f9e"))
