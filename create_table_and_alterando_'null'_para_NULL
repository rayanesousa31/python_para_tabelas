#Esse código tem como objetivo ajudar na criação de tabela (CREATE TABLE) e fazer a alteração de '\\N' e 'null'(string) passando ambos para NULL.
#O código ainda esta sendo melhorado, mas quem precisa mexer com SQL e tem MUITAS colunas, isso ja ajuda bastante.

lista=[
    'col_name1',
    'col_name2',
    'col_name3',
    'col_name4',
    'col_name5',
    'col_name6',
    'col_name7'
    ]

opcao = int(input('''Qual opção deseja? Digite o número das opções abaixo:
1 - Alteração dos nulos ('\\N' ou 'null' para NULL)
2 - Criação de tabela \n'''))

if opcao == 1:
    tabela = input("Qual o nome da tabela para fazer UPDATE? \n")
    arquivo1 = 'alteracao_nulos_{}.txt'.format(tabela)
    with open(arquivo1, 'w') as arquivo:
        arquivo.write("UPDATE [{}]".format(tabela))
        for index, campo in enumerate(lista):
            if index == len(lista) -1 : # Verifica se é o último campo da lista
                arquivo.write(f"    {campo} = iif(lower({campo}) = '\\N' or lower({campo}) = 'null', null, {campo} \n")
            else:
                arquivo.write(f"    {campo} = iif(lower({campo}) = '\\N' or lower({campo}) = 'null', null, {campo}, \n")
elif opcao == 2:
    tabela = input("Qual o nome da tabela que deseja criar? \n")
    arquivo1 = 'criacao_tabela_{}.txt'.format(tabela)
    with open(arquivo1, 'w') as arquivo:
        arquivo.write(f"CREATE TABLE {tabela}\n")
        for index, campo in enumerate(lista):
            if index == len(lista) - 1:  # Verifica se é o último campo da lista
                arquivo.write(f"    {tabela}.{campo}\n")
            else:
                arquivo.write(f"    {tabela}.{campo},\n")
else:
    print("Opção Inválida")

print(f"Arquivo '{arquivo1}' foi criado com sucesso.")
