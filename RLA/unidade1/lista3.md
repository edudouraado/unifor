# UNIFOR
**Nome**: Eduardo Dourado <br>
**Disciplina**: Raciocínio lógico algorítm

## Exercício exemplo 1
Implemente e teste um programa que imprima os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\num = 1\]
D --> E{num <= n}
E --FALSE--> I([FIM])
E --TRUE--> F{{"Num", num}}
F --> G[num =+ 1]
G --LOOP--> E
```

#### Pseudocódigo
```
1 ALGORITMO print_n_primeiros
2 DECLARE n, num: INTEIRO
3 INICIO
4 ESCREVA “Digite um número: ”
4 LEIA n			// variável de entrada n
4 num ← 1			// variável num inicializada
5 ENQUANTO num <= n FAÇA	// n iterações
7	ESCREVA “Número ”, num
8	num ← num + 1		// num =+ 1 (incremento)
8 FIM_ENQUANTO
9 FIM
```

#### Teste de mesa
| it | n  | num | num <= n | Saída      | num =+ 1 |
| -- | -- | --  | --       | --         | --       |
| 1  | 10 | 1   | True     | Número 1   | 2        |
| 2  | 10 | 2   | True     | Número 2   | 3        |
| 3  | 10 | 3   | True     | Número 3   | 4        |
| 4  | 10 | 4   | True     | Número 4   | 5        |
| 5  | 10 | 5   | True     | Número 5   | 6        |
| 6  | 10 | 6   | True     | Número 6   | 7        |
| 7  | 10 | 7   | True     | Número 7   | 8        |
| 8  | 10 | 8   | True     | Número 8   | 9        |
| 9  | 10 | 9   | True     | Número 9   | 10       |
| 10 | 10 | 11  | True     | Número 10  | 11       |
| 11 | 10 | 11  | False    |            |          |

## Exercício exemplo 2
Implemente e teste um programa que some os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\soma = 0\]
D --> E[[i=1 ATÉ n PASSO 1]]
E --FALSE--> G([FIM])
E --TRUE--> F[soma =+ i]
F --LOOP--> E
```

#### Pseudocódigo
```
1  ALGORITMO	soma_n_numeros()
2  DECLARE	n, i, soma: INTEIRO
3  INICIO
4  ESCREVA “Digite a quantidade de números: ”
5  LEIA n		// variável de entrada n
7  soma ← 0		// variável soma inicializada
6  PARA i DE 1 ATÉ n PASSO 1 FAÇA
7	soma ← soma + i	// soma =+ i (incremento)
8  FIM_PARA
9  ESCREVA “A soma é igual a ”, soma
10 FIM
```

#### Teste de mesa
| it | n  | soma | i  | soma =+ i |
| -- | -- | --   | -- | --        |
| 1  | 10 | 0    | 1  | 1         |
| 2  | 10 | 1    | 2  | 3         |
| 3  | 10 | 3    | 3  | 6         |
| 4  | 10 | 6    | 4  | 10        |
| 5  | 10 | 10   | 5  | 15        |
| 6  | 10 | 15   | 6  | 21        |
| 7  | 10 | 21   | 7  | 28        |
| 8  | 10 | 28   | 8  | 36        |
| 9  | 10 | 36   | 9  | 45        |
| 10 | 10 | 45   | 10 | 55        | 

## Lista de exercícios 03

### Exercício 01 (2.5 pontos)
Atualize o algoritmo para determinar se um número inteiro e positivo é par ou ímpar, usando uma laço condicional para aceitar apenas números maiores ou iguais a zero. 

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um numero inteiro e positivo}}
B --> C[/Num1/]
C --> D{Num1 >= 0}
D --LOOP--> B
D --TRUE--> F[R = Num1 % 2]
F --> G{R = 0}
G --TRUE--> H{{O numero é par}}
G --FALSE--> I{{O numero é impar}}
H --> J([FIM])
I --> J
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO par_impar
DECLARE Num1, R : INTEIROS
INICIO
REPITA
	ESCREVA "Digite um numero inteiro e positivo"
	LEIA Num1
	ATE_QUE Num1 >= 0 ENTAO
	R = Num1 % 2
	SE R = 0 ENTAO
		ESCREVA "O numero é par"
	SENAO 
		ESCREVA "O numero é impar"
	FIM_SE
FIM
```

#### Teste de mesa (0.5 ponto)

| Num1 | Num1 >= 0 | R | R = 0 | SAIDA | 
| -- | -- | -- | -- | -- | 
| 2 | TRUE | 0 | TRUE | O numero é par |
| 10 | TRUE | 0 | TRUE | O numero é par |
| 13 | TRUE | 1 | FALSE | O numero é impar |
| 25 | TRUE | 1 | FALSE | O numero é impar |

### Exercício 02 (2.5 pontos)
Faça um algoritmo que exiba na tela uma contagem de 0 até 30, exibindo apenas os múltiplos de 3.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B[/Num1 = 0/]
B --> C{Num1 <= 30}
C --TRUE--> D{{Numero = Num1}}
D --> E[Num1 =+ 3]
E --LOOP--> C
C --FALSE--> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO multiplos_3
DECLARE Num1 : NUMERICOS
INICIO
Num1 = 0
ENQUANTO Num1 <= 30 FAÇA
	ESCREVA "Numero = Num1"
	Num1 =+ 3
FIM_ENQUANTO
```

#### Teste de mesa (0.5 ponto)

|  | Num1 | Num2 | Num1 <= Num2 | SAIDA | Num1 =+ 3 |  
| -- | -- | -- | -- | -- | -- |  
| 1 | 0 | 30 | TRUE | 0 | 3 |  
| 2 | 3 | 30 | TRUE | 3 | 6 |  
| 3 | 6 | 30 | TRUE | 6 | 9 |  
| 4 | 9 | 30 | TRUE | 9 | 12 |  
| 5 | 12 | 30 | TRUE | 12 | 15 |
| 6 | 15 | 30 | TRUE | 15 | 18 | 
| 7 | 18 | 30 | TRUE | 18 | 21 | 
| 8 | 21 | 30 | TRUE | 21 | 24 | 
| 9 | 24 | 30 | TRUE | 24 | 27 | 
| 10 | 27 | 30 | TRUE | 27 | 30 | 
| 11 | 30 | 30 | TRUE | 30 | 33 |
| 12 | 33 | 30 | FALSE | 33 | 36 |

### Exercício 03 (2.5 pontos)
Dada uma sequência de números inteiros, calcular a sua soma. 
Por exemplo, para a sequência {12, 17, 4, -6, 8, 0}, o seu programa deve escrever o número 35.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite 3 numeros inteiros}}
B --> C[/Num1, Num2, Num3/]
C --> D[R = Num1 + Num2 + Num3]
D --> E{{Sua soma é igual a: R}}
E --> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO soma
DECLARE Num1, Num2, Num1, R : INTEIROS
INICIO
ESCREVA "Digite 3 numeros inteiros"
LEIA Num1, Num2, Num3
R = Num1 + Num2 + Num3 ENTAO
	ESCREVA "Sua soma é igual: ", R
FIM
```

#### Teste de mesa (0.5 ponto)

| Num1 | Num2 | Num3 | R | SAIDA | 
| -- | -- | -- | -- | -- | 
| 1 | 3 | 5 |  9 | A soma dos 3 numeros é: 9 |
| 2 | 4 | 6 | 12 | A soma dos 3 numeros é: 12 |
| 8 | 3 | 4 | 16| A soma dos 3 numeros é: 16 |
| 9 | 6 | 1 | 14 | A soma dos 3 numeros é: 14|

### Exercício 04 (2.5 pontos)
Escreva um programa que leia a nota de diversos alunos, até que seja digitada uma nota negativa. 
Nesse momento, ele mostra a média aritmética de todas as notas lidas e quantas notas foram lidas. 
Ex. Foram lidas 14 notas. A média aritmética é 6.75!

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
Algoritmo ClassificaCategoria
FIM_ALGORITMO
```

#### Teste de mesa (0.5 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |
