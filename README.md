# Sistema-Banc-rio-com-Python
PROJETO1

menu = """
    Depósito [1]
    Saque [2]
    Extrato [3]
    Sair [4]
"""

saldo = 0
limite_saque = 500
limite_diario = 1500
numero_saque = 0
transacao = []

while True:
    opcao = int(input(menu))
    
    if opcao == 1:
        dep1 = int(input("Insira o valor para depósito: "))
        if dep1 >= 0:
            saldo += dep1
            transacao.append(f"Depósito: +{dep1}")
            print("Insira as cédulas no local indicado.")
            print("Obrigado por usar nossos serviços!")
        else:
            print("Valor inválido.")
    elif opcao == 2:
        if numero_saque < 3:
            saque1 = int(input("Digite o valor do saque desejado: "))
            if 0 < saque1 <= limite_saque and (limite_diario - saque1) >= 0:
                saldo -= saque1
                limite_diario -= saque1
                numero_saque += 1
                transacao.append(f"Saque: +{saque1}")
                print("Retire as cédulas no local indicado!\nObrigado por utilizar nossos serviços.\nDeseja realizar outro serviço?")
            else:
                print("Sem saldo suficiente ou valor de saque inválido.")
        else:
            print("Limite diário de saques atingido!")
    elif opcao == 3:
        print("Exibindo Extrato: ")
        print(transacao)
        
    elif opcao == 4:
        print("Saindo")
        break
    else:
        print("Opção inválida")

print("Fim do programa")
