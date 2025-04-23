def soma(num1, num2):
    return num1 + num2

def subtracao(num1, num2):
    return num1 - num2

def multiplicacao(num1, num2):
    return num1 * num2

def divisao(num1, num2):
    if num2 == 0:
        raise ZeroDivisionError("Erro: divisão por zero!")
    return num1 / num2

def exibir_menu():
    print("\nEscolha uma operação:")
    print("1: Soma")
    print("2: Subtração")
    print("3: Multiplicação")
    print("4: Divisão")
    print("0: Sair")

def obter_operacao(opcao):
    operacoes = {
        "1": ("Soma", soma),
        "2": ("Subtração", subtracao),
        "3": ("Multiplicação", multiplicacao),
        "4": ("Divisão", divisao),
    }
    return operacoes.get(opcao, (None, None))

def calculadora():
    while True:
        exibir_menu()
        opcao = input("Digite o número da operação: ")

        if opcao == "0":
            print("Encerrando a calculadora...")
            break

        nome_operacao, func_operacao = obter_operacao(opcao)
        if func_operacao is None:
            print("Essa opção não existe."

        try:
            num1 = float(input("Digite o primeiro número: "))
            num2 = float(input("Digite o segundo número: "))

            resultado = func_operacao(num1, num2)
            print(f"Resultado da {nome_operacao}: {resultado}")

        except ValueError:
            print("Erro: digite apenas números válidos.")
        except ZeroDivisionError as e:
            print(e)
