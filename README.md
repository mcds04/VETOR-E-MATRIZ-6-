# VETOR-E-MATRIZ-6-
TÉCNICAS DE PROGRAMAÇÃO I  - EXERCICIO VALENDO 2,0 PTS
DISCIPLINA: TÉCNICAS DE PROGRAMAÇÃO I  
DOCENTE: EDVAR DA LUZ OLIVEIRA  
DISCENTE: MARIA CRISTINA SOUSA 
ASSUNTO: VETOR E MATRIZ [6], Pontuação: 2,0 pontos

GoogleColab https://colab.research.google.com/drive/1WVoHLtEHyQyX_RRsZywutk9n50TIRoOX?usp=sharing

Utilizando a linguagem Python (módulo numpy) faça:

a)	um programa que receba um vetor A de 6 posições de números reais, imprimi-lo na ordem inversa de armazenamento.
Resposta: 
import numpy as np

A = np. array ([1.0, 2.0, 3.0, 4.0, 5.0, 6.0])
print(A[::-1])

Saída: 
[6. 5. 4. 3. 2. 1.]
b)	um programa que receba um vetor A de 10 posições de números reais, armazenar em um segundo vetor B (na ordem inversa de armazenamento do vetor A).
Resposta: 
A = np. array ([1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0, 8.0, 9.0, 10.0])
B = A[::-1]
print(B)

Saída: 
[10.  9.  8.  7.  6.  5.  4.  3.  2.  1.]
c)	Um programa que solicite os 12 salários recebidos de um trabalhador, faça a passagem desse vetor de salários para uma função chamada calc, onde, nesta função, deve ser calculado o valor total recebido durante o ano e a média salarial.
Resposta: 
def calc(salarios):
    total = sum(salarios)
    media = total / len(salarios)
    return total, media

salarios = []
for i in range (1, 13):
    salario = float (input (f"Digite o salário do mês {i}: "))
    salarios. append(salario)

total, media = calc(salarios)
print (f"O valor total recebido durante o ano foi de R${total:.2f}")
print (f"A média salarial foi de R${média:.2f}")

Saída:
Digite o salário do mês 1: 1000
Digite o salário do mês 2: 2000
Digite o salário do mês 3: 3000
Digite o salário do mês 4: 4000
Digite o salário do mês 5: 5000
Digite o salário do mês 6: 6000
Digite o salário do mês 7: 7000
Digite o salário do mês 8: 8000
Digite o salário do mês 9: 9000
Digite o salário do mês 10: 10.000
Digite o salário do mês 11: 11.000
Digite o salário do mês 12: 12.000
O valor total recebido durante o ano foi de R$45033.00
A média salarial foi de R$3752.75

função calc recebe um vetor de salários como entrada e retorna o valor total recebido durante o ano e a média salarial. O loop for solicita ao usuário os salários de cada mês e os armazena no vetor salarios. A linha total, média = calc(salarios) chama a função calc com esse vetor. 


d)	Um programa que leia um conjunto de 5 alunos, cada uma com o nome e a nota. Em seguida exiba o nome dos alunos que possuem a nota maior do que a média da turma.
Resposta: 
alunos = []
for i in range (1, 6):
    nome = input (f"Digite o nome do aluno {i}: ")
    nota = float (input (f"Digite a nota do aluno {i}: "))
    alunos. append ((nome, nota))

média = sum (nota for nome, nota in alunos) / len(alunos)

print ("Alunos com nota acima da média:")
for nome, nota in alunos:
    if nota > média:
        print(nome)

Saída: 
Digite o nome do aluno 1: Joao
Digite a nota do aluno 1: 9
Digite o nome do aluno 2: Maria
Digite a nota do aluno 2: 10
Digite o nome do aluno 3: Pedro
Digite a nota do aluno 3: 7
Digite o nome do aluno 4: Ana
Digite a nota do aluno 4: 8
Digite o nome do aluno 5: Carlos
Digite a nota do aluno 5: 6
Alunos com nota acima da média:
Joao
Maria

o loop for inicial solicita ao usuário o nome e a nota de cada aluno e os armazena na lista alunos. A linha média = sum (nota for nome, nota in alunos) / len(alunos) calcula a média da turma. 

e)	Um programa que armazene em dois vetores 10 valores numéricos e, em um terceiro vetor, armazene a soma relativa as posições iguais nas 3 estruturas.
Resposta: 
vetor1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
vetor2 = [11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
vetor3 = []

for i in range(len(vetor1)):
    soma = vetor1[i] + vetor2[i]
    vetor3.append(soma)

print(vetor3)
Saida:
[12, 14, 16, 18, 20, 22, 24, 26, 28, 30]

vetor1 e vetor2 são os vetores que armazenam 10 valores numéricos. O loop for percorre cada posição dos vetores e calcula a soma dos valores na mesma posição em vetor1 e vetor2, armazenando o resultado em vetor3

f)	Dada a seguinte matriz abaixo, desenvolver um programa que informe alguns dados estatísticos:
a.	Moda (dado(s) mais frequente(s))
b.	Média geral
c.	Média individual (de cada linha e de cada coluna)
Matriz:
int c[][] = { { 1, 2, 1, 3, 6, 5, 4}, 
                      { 3, 4, 5, 7, 7, 9, 8},
                      { 1, 0, 5, 7, 0, 0, 2},
                      { 3, 2, 2, 1, 0, 3, 4},
                      { 1, 2, 3, 4, 5, 6, 7},
                      { 0, 3, 6, 0, 0, 0, 1},
                      { 9, 2, 6, 0, 0, 0, 2},
                      { 8, 1, 6, 0, 0, 0, 3}};

Resposta: 

import numpy as np
from scipy import stats

c = np. array ([[1, 2, 1, 3, 6, 5, 4], 
              [3, 4, 5, 7, 7, 9, 8],
              [1, 0, 5, 7, 0, 0, 2],
              [3, 2, 2, 1, 0, 3, 4],
              [1, 2, 3, 4, 5, 6, 7],
              [0, 3, 6, 0, 0, 0, 1],
              [9, 2, 6, 0, 0, 0, 2],
              [8, 1, 6, 0, 0, 0, 3]])

moda = np. unique (c, axis=None) [0]

media_geral = np.mean(c)

media_linhas = np. mean(c, axis=1)

media_colunas = np.mean(c, axis=0)

print (f"Moda: {moda}")
print (f"Média geral: {media_geral}")
print (f"Média individual de cada linha: {media_linhas}")
print (f"Média individual de cada coluna: {media_colunas}")

Saida:
Moda: 0
Média geral: 3.0357142857142856
Média individual de cada linha: [3.14285714 6.14285714 2.14285714 2.14285714 4.         1.42857143
 2.71428571 2.57142857]
Média individual de cada coluna: [3.25 2.    4.25 2.75 2.25 2.875 3.875]

OBS: Tive bastante dificuldade para fazer o código, não sei está correto acredito ter alguns erros, linha calculando a moda, próprio google colab indicou o erro, Para corrigir o erro, altere a linha moda = stats.mode(c, axis=None).mode[0] para moda = np.unique(c, axis=None)[0], porem a saída não sei se está correta.

g)	A multiplicação de matrizes é realizada de acordo com a condição em que o número de colunas da 1ª matriz deve ser igual ao número de linhas da 2ª matriz, de acordo com esta definição, desenvolva um programa que realize a multiplicação de duas matrizes, A [2][5] e B [5][2]. Popular as matrizes com números inteiros e mostre o resultado.

 Resposta: 
import numpy as np

A = np. random. randint (10, size= (2, 5))
B = np. random. randint (10, size= (5, 2))

print ("Matriz A:")
print(A)

print ("\nMatriz B:")
print(B)

resultado = np.dot (A, B)

print ("\nResultado da multiplicação de A e B:")
print(resultado)
Saída: 
Matriz A:
[[9 9 4 0 2]
 [2 8 4 3 6]]

Matriz B:
[[2 9]
 [0 5]
 [5 4]
 [1 6]
 [8 7]]

Resultado da multiplicação de A e B:
[[54 156]
 [75 134]]

O código criou duas matrizes aleatórias de tamanhos 2x5 e 5x2, e mostra como resultado a multiplicação de A e B. 


h)	Criar um programa e popular uma matriz m 5x5; solicitar um número do usuário. Pesquisar se esse número existe na matriz. Se existir, imprimir em qual posição da matriz. Se não existir, imprimir que não existe.
Resposta:

import random

matriz = [[random. randint (1, 100) for _ in range (5)] for _ in range (5)]

for linha in matriz:
    print(linha)

num = int (input ("Digite um número: "))

existe = False
for i in range (5):
    for j in range (5):
        if matriz[i][j] == num:
            print (f"O número {num} foi encontrado na posição ({i+1}, {j+1}) da matriz.")
            existe = True

if not existe:
    print (f"O número {num} não existe na matriz.")

Saída: 

[81, 56, 14, 59, 65]
[16, 9, 1, 86, 32]
[91, 89, 13, 39, 53]
[5, 74, 2, 64, 81]
[81, 86, 95, 52, 57]
Digite um número: 53
O número 53 foi encontrado na posição (3, 5) da matriz.

i)	Criar um programa que leia os elementos de uma matriz inteira de 3 x 3 e imprimir todos os elementos, exceto os elementos da diagonal principal.
Resposta: 
matriz = []
for i in range (3):
    linha = []
    for j in range (3):
        num = int (input (f"Digite o elemento da posição ({i+1}, {j+1}): "))
        linha. append(num)
    matriz. append(linha)

print("Matriz:")
for linha in matriz:
    print(linha)

print ("Elementos fora da diagonal principal:")
for i in range (3):
    for j in range (3):
        if i! = j:
            print(matriz[i][j])

Saída: 
Digite o elemento da posição (1, 1): 2
Digite o elemento da posição (1, 2): 3
Digite o elemento da posição (1, 3): 4
Digite o elemento da posição (2, 1): 5
Digite o elemento da posição (2, 2): 2
Digite o elemento da posição (2, 3): 0
Digite o elemento da posição (3, 1): 1
Digite o elemento da posição (3, 2): 5
Digite o elemento da posição (3, 3): 3
Matriz:
[2, 3, 4]
[5, 2, 0]
[1, 5, 3]
Elementos fora da diagonal principal:
3
4
5
0
1
5

j)	Criar um programa que leia os elementos de uma matriz inteira de 3 x 3 e imprimir outra matriz multiplicando cada elemento da primeira matriz por um número inteiro informado pelo usuário.
Resposta: 
matriz = []
for i in range (3):
    linha = []
    for j in range (3):
        num = int (input (f"Digite o elemento da posição ({i+1}, {j+1}): "))
        linha. append(num)
    matriz. append(linha)

multiplicador = int (input ("Digite um número inteiro: "))

nova_matriz = [[elemento * multiplicador for elemento in linha] for linha in matriz]

print ("Nova Matriz:")
for linha in nova_matriz:
    print(linha)


Saída: 
Digite o elemento da posição (1, 1): 1
Digite o elemento da posição (1, 2): 2
Digite o elemento da posição (1, 3): 3
Digite o elemento da posição (2, 1): 4
Digite o elemento da posição (2, 2): 1
Digite o elemento da posição (2, 3): 3
Digite o elemento da posição (3, 1): 2
Digite o elemento da posição (3, 2): 5
Digite o elemento da posição (3, 3): 6
Digite um número inteiro: 4
Nova Matriz:
[4, 8, 12]
[16, 4, 12]
[8, 20, 24]


k)	Preencher uma matriz 4x4 de elementos inteiros. Mostrar a matriz e informar quantos números são maiores do que 30, somar todos e mostrar estes números, bem como a soma. 
Resposta: 
import random

matriz = [[random. randint (1, 100) for _ in range(4)] for _ in range(4)]

print("Matriz:")
for linha in matriz:
    print(linha)

numeros_maiores_que_30 = [num for linha in matriz for num in linha if num > 30]

print (f"Há {len(numeros_maiores_que_30)} números maiores do que 30.")

soma = sum(numeros_maiores_que_30)
print (f"Os números maiores do que 30 são: {numeros_maiores_que_30}")
print (f"A soma desses números é: {soma}")


Saída:
Matriz:
[54, 63, 71, 26]
[96, 92, 63, 21]
[50, 17, 76, 48]
[68, 59, 98, 7]
Há 12 números maiores do que 30.
Os números maiores do que 30 são: [54, 63, 71, 96, 92, 63, 50, 76, 48, 68, 59, 98]
A soma desses números é: 838
