# UNIFOR
**Nome**: Eduardo Dourado <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (0,5 ponto)
```
1  ALGORTIMO verifica_par_impar
2  DECLARE numero, resto: INTEIRO
3  ESCREVA "Digite um número: "
4  INICIO
4  LEIA numero
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"
9    SENAO
10     ESCREVA "O número é impar!"
11   FIM_SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"
13  FIM_SE
13 FIM
```

#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite seu sálario:}}
B --> C[/Salario1/]
C --> D{Salario1 >= 500}
D --TRUE--> E[Salario1 * 1.1 = S2]
D --FALSE--> F[Salario1 * 1.2 = S2]
E --> G{{S2}}
F --> G
G --> H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO salario
DECLARE S1, S2: REAIS
INICIO
ESCREVA "Digite seu salario: "
LEIA S1
SE S1 >= 500.00 ENTAO
	S2 = S1 * 1.1
SENAO
	S2 = S1 * 1.2
	ESCREVA "Seu novo salario é: ", S2
FIM
```

#### Teste de mesa (1.0 ponto)

| S1 | S1 >= 500.00 | S2 | SAIDA | 
|      --      |      --      |      --      |      --      |
| 200     | 200.00 >= 500.00       | 240.00    |  Seu novo salario é: 240.00     |
| 800   | 800.00 >= 500.00          | 880.00        | Seu novo salario é: 880.00 |

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite a primeira nota: }}
B --> C[/nota1/]
A --> D{{Digite a segunda nota: }}
D --> E[/nota2/]
C --> F[MEDIA = nota1 + nota2 / 2]
E --> F
F --> G{MEDIA >= 7}
G --TRUE--> H[O aluno está aprovado com media: MEDIA]
G --FALSE--> I[O aluno está reprovado com media: MEDIA]
H --> J([FIM])
I --> J
```  

#### Pseudocódigo (1 ponto)

```
ALGORITMO media
DECLARE N1, N2, M REAIS
INICIO
ESCREVA "Digite suas duas notas: "
LEIA N1, N2
M = N1 + N2 / 2
SE M >= 7.00 ENTAO
	ESCREVA "O aluno foi aprovado com media: ", M
SENAO 
	ESCREVA "O aluno foi aprovado com media: ", M
FIM

```

#### Teste de mesa (1 ponto)

| N1 | N2 | M | M >= 7.00 | SAIDA |
|      --      |      --      |      --      |      --      |      --      |
| 8.00     | 7.00      | 7.50    |  7.50 >= 7.00     | Aluno aprovado |
| 5.00   | 6.00          | 5.50        | 5.50 <= 7.00 | Aluno reprovado |

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO])--> B{{Declare uma idade}}
B --> C[/I1/]
C --> D{I1 >= 18}
D --TRUE--> E{{Já pode retirar a CNH}}
D --FALSE--> F[I2 = 18 - I1]
F --> G{I2 <= 18}
G --TRUE--> H{{Deve esperar o I2 ser = a 18}}
G --FALSE--> D
E --> I([FIM])
H --> I
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO CNH
VERIFICAR I1, I2 NUMERICOS
INICIO
ESCREVA "Digite sua idade: "
LEIA I1
SE I1 >= 18 ENTAO
	ESCREVA "Já pode tirar a CNH"
SENAO
	I2 = 18 - I1
	ESCREVA "O candidato devera esperar: ", I2
FIM
```

#### Teste de mesa (1.0 ponto)

| I1 | I1 >= 18 | I2 | SAIDA | 
|      --      |      --      |      --      |      --      |
| 18     | 18 >= 18       | 0    |  Já pode tirar a CNH     |
| 19   | 19 >= 18          | -1        | Já pode tirar a CNH |
