menu = """
(1) depositar
(2) sacar
(3) extrato
(4) sair
"""

saldo = 0
limite = 500
extrato = ""
saque = 0
LIMITE_SAQUE = 3

while True:
opcao = input(menu)
if opcao == "1":
valor = float(input('deposite o valor '))
if valor >= 0:
saldo += valor
extrato += f'valor depositado {valor:.2f}'
else:
print("o deposito falhou!! valor informado invalido")

    elif opcao == "2":
        valor = float(input('digite o valor que deseja sacar'))

        atingiu_saldo = valor > saldo
        atingiu_limite = valor > limite
        atingiu_saque = saque >= LIMITE_SAQUE
        if atingiu_saldo:
            print("saque falhou !!, saldo insuficiente")
        elif atingiu_saque:
            print("saque falhou!!, atingiu o limite de tentativas")
        elif atingiu_limite:
            print("saque falkou!!, atingiu o limite da sua conta ")
        elif valor >= 0:
            saldo -= valor
            extrato += f" valor do saque {valor:.2f}"
            saque += 1
        else:
            print("o sistema detectou a entrada de numeros invalidos")
    elif opcao == "3":
        print("##########EXTRATO BANCARIO##########\n")
        print("sim movimento por aqui."if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("####################################")
    elif opcao == "4":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")
