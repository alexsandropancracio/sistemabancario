import time

def sacar(valor):
    saldo = 500  # acesso ao banco de dados
    saques = 0
    limite = 500

    while True:
        time.sleep(1)
        saque = input('Pressione Enter para acessar sua conta. \n')
        enter = ""

        if saque == enter:
            login = input('Login: ').strip()
            senha = input('Senha: ').strip()
            time.sleep(0.8)
            print('Aguarde um momento, estamos processando...\n')
            time.sleep(3)
            print('Olá, seja bem vindo/a!')
            time.sleep(1)

            while True:
                print('-' * 50)
                print('Saldo atual: R${:.2f}'.format(saldo))
                opcao = int(input('Informe uma opção: \n[1]Sacar\n[2]Depositar\n[3]Extrato\n[0]Sair\nOpção: '))
                print('-' * 50)

                if opcao == 1 or saques <= 3:
                    saques += 1

                    while True:
                        total = input('Valor: R$')

                        if total == "":
                            print('Valor inválido. Por favor, tente novamente.\n')
                            time.sleep(1)

                        else:
                            total = float(total)

                            if total <= saldo and total <= 500:
                                saldo -= valor
                                print('Analisando saldo...')
                                time.sleep(2)
                                print('Valor aprovado.')
                                time.sleep(1)
                                print('Retire o seu dinheiro na boca do caixa.')
                                time.sleep(2)
                                print('Obrigado pela preferência. Volte sempre!\n')
                                time.sleep(2)
                                saldo -= total
                                break

                            elif total > 500:
                                print(f'Seu saque ultrapassa o saldo limite de R${limite:.2f}, tente novamente.\n')
                                time.sleep(1)

                            elif total > saldo:
                                print('Analisando saldo...')
                                time.sleep(2)
                                print(f'Seu saldo é de R$ {float(saldo)} e você deseja sacar R$ {float(total)}')
                                time.sleep(1)
                                tente = input('Saldo insuficiente. Deseja transferir algum valor pra sua conta? Sim/Não \n').lower()

                                if tente == "sim":
                                    transferir = int(input('Valor a ser transferido: '))
                                    saldo += transferir
                                    print('Transferindo o valor...')
                                    time.sleep(3)
                                    print('Valor transferido com sucesso.\n')
                                    time.sleep(2)
                                    break

                                elif tente == "não":
                                    print('Fim de transação. \n')
                                    time.sleep(2)
                                    break

                                if total == "":
                                    print('Informação inválida. Por favor, tente novamente.\n')
                                    time.sleep(1)
                    break
                else:
                    print('''Você atingiu o limite de saque diário. 
Por favor, volte amanhã para mais saques ou entre em contato com nossa central.''')
                    print('')
                    time.sleep(1)
                    break

                '''if opcao == 2:

                    while True:
                        deposito = float(input('Valor: R$'))
                        saldo += deposito
                        print('Deposito efetuado!')'''
                        

                if opcao == 3:
                    while True:
                        time.sleep(1)
                        print('Processando extrato...')
                        time.sleep(2)
                        print('Extrato processado: ')
                        voltar = input('Aperte Enter para voltar às opções anteriores.\n')

                        if voltar == "":
                            print('Operação concluída! \n')
                            time.sleep(2)
                            break

                if opcao == 0:
                    print('Obrigado pela preferência. Volte sempre!\n')
                    time.sleep(2)
                    break

sacar(0)
