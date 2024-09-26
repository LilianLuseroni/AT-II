# AT-II
import random


def gerar_pergunta(nivel):
    global num1, num2
    if nivel == 1:
        num1 = random.randint(0, 10)
        num2 = random.randint(0, 10)
    elif nivel == 2:
        num1 = random.randint(10, 100)
        num2 = random.randint(10, 100)
    return num1, num2


def verificar_resposta(num1, num2, resposta, nivel):
    return resposta == num1 * num2


def jogo_tabuada():
    nivel = 1
    acertos = 0

    while True:
        num1, num2 = gerar_pergunta(nivel)
        print(f"Qual é o resultado de {num1} x {num2}?")
        resposta = int(input("Resposta: "))

        if verificar_resposta(num1, num2, resposta, nivel):
            acertos += 1
            print("Parabéns, você está indo muito bem!")
        else:
            print(f"Continue, você está indo bem! A resposta correta é {num1 * num2}")

        if acertos == 10:
            if nivel == 1:
                nivel = 2
                acertos = 0
                print("Você avançou para o nível 2!")
            else:
                print("Parabéns! Você completou todos os níveis!")
                break


# Iniciar o jogo
jogo_tabuada()
