# UNIFOR
**Nome**: Eduardo Dourado Sales de Oliveira <br>
**Disciplina**: Raciocínio lógico algorítm

## Exercício exemplo
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o adicional de salário de funcionário por cargo de uma empresa fictícia. Sabe-se que os funcionários de cargo técnico receberão reajuste de 50%, cargo de gerência, um reajuste de 30% e demais, um reajuste de 10%. 

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o salário e profissão}}
B --> C[\sal, prof\]
C --> D{prof == 'Tecnico'}
D --FALSE--> E{prof == 'Gerente'}
D --TRUE--> F[sal_reaj = 1.5 * sal]
E --FALSE--> H[sal_reaj = 1.1 * sal]
E --TRUE--> G[sal_reaj = 1.3 * sal]
G --> I([FIM])
F --> I
H --> J{{'Salário Reajustado = ', sal_reaj}}
J --> I
```

#### Pseudocódigo
```
1  ALGORITMO calReajuste
2  DECLARE  sal, sal_reaj: real, prof: caractere
3  INICIO
4  LEIA sal, prof
5  ESCOLHA
6   CASO prof == “Técnico”		// caso 1
7     sal_reaj ← 1.5 * sal
8   CASO prof = “Gerente”		// caso 2
9     sal_reaj ← 1.3 * sal
10  SENÃO
11    sal_reaj ← 1.1 * sal
12 FIM_ESCOLHA
13 ESCREVA “Salário Reajustado = “, sal_reaj
14 FIM
```

#### Teste
| sal | prof | prof == “Técnico” | prof = “Gerente” | sal_reaj | Saída |
| -- | -- | -- | -- | -- | -- |
| 1000 | Técnico | V | F | 1500 | “Salário Reajustado = 1500“ |
| 2000 | Gerente | F | V | 2600 | “Salário Reajustado = 2600“ |
| 9000 | Diretor | F | F | 9900 | “Salário Reajustado = 9900“ |

## Lista de exercícios 02

### Exercício 01 (2.5 pontos)
Calcule a média de quatro números inteiros dados.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite quatro numeros inteiros}}
B --> C[/N1, N2, N3, N4/]
C --> D[M = N1 + N2 + N3 + N4 / 4]
D --> E{{"A media desses quatro numeros é: ", M}}
E --> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO media
DECLARE N1, N2, N3, N4 INTEIROS
INICIO
ESCREVA "Digite quatro numeros inteiros: "
LEIA N1, N2, N3, N4
M = N1 + N2 + N3 + N4 / 4 ENTAO
	ESCREVA "A media desses quatro numeros é: ", M
FIM
```

#### Teste de mesa (0.5 ponto)

| N1 | N2 | N3 | N4 | M | SAIDA | 
|      --      |      --      |      --      |      --      |      --      |      --      | 
| 4    | 8       | 4    |  10     | 6.5    |      A media é: 6.5      |
| 7    | 9       | 6    |  8     | 7.5    |      A media é: 7.5 |
| 2    | 4       | 6    |  8     | 5.5    |      A media é: 5.0 | 
| 3    | 5       | 7    |  9     | 5.5    |      A media é: 6.0 |     

### Exercício 02 (2.5 pontos)
Leia uma temperatura dada em Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite uma temperatura em celcius: }}
B --> C[/C/]
C --> D[F = 9 * C / 5 + 32]
D --> E{{"A temperatura em fahrenheit é: ", F}}
E --> F([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO temperatura
DECLARE C, F REAIS
INICIO
ESCREVA "Digite uma temperatura em celcius: "
LEIA C
F = 9 * C / 5 + 32 ENTAO
	ESCREVA "A temperatura em fahrenheit é: ", F
FIM
```

#### Teste de mesa (0.5 ponto)

|  ºC  |  ºF  | SAÍDA  |
|  --  |  --  |  --  |
| 20 | 71.6 | A temperatura em fahrenheit é: 71.6|
| 25 | 68 | A temperatura em fahrenheit é: 68|
| 30 | 86 | A temperatura em fahrenheit é: 86|
| 35 | 95 | A temperatura em fahrenheit é: 95|

### Exercício 03 (2.5 pontos)
Receba dois números reais e um operador e efetue a operação correspondente com os valores recebidos (operandos). 
O algoritmo deve retornar o resultado da operação selecionada simulando todas as operações de uma calculadora simples.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite dois numeros reais e um operador}}
B --> C[/Num1, Num2, Operacao/]
C --> D{Operacao =+}
D --TRUE--> E[R = Num1 + Num2]
E --> F{{O resultado da Operacao é: R}}
F --> G([FIM])
D --FALSE--> H{Operacao =-}
H --TRUE--> I[R = Num1 - Num2]
I --> F
H --FALSE--> J{Operacao = x}
J --TRUE--> K[R = Num1 x Num2]
K --> F
J --FALSE--> L{Operacao =/}
L --> M[R = Num1 / Num2]
M --> F
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO operadores
DECLARE Num1, Num2, R : REAIS, Operacao: CARACTERES
INICIO 
ESCREVA "Digite dois numeros reais e um operador"
LEIA Num1, Num2, Operacao 
SE Operacao =+ ENTAO
	R = Num1 + Num2
SENAO 
Operacao =- ENTAO
	R = Num1 - Num2
	SENAO 
	Operacao =x ENTAO
		R = Num1 x Num2
		SENAO
		Operacao =/ ENTAO
			R = Num1 / Num2
ESCREVA "O resultado da Operacao é: R"
FIM	
```

#### Teste de mesa (0.5 ponto)

| Num1 | Num2 | Operacao | Operacao =+ | Operacao =- | Operacao =x | Operacao =/ | R | SAIDA |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | 
| 12 | 8 | + | TRUE | FALSE | FALSE | FALSE | 20 | O resutado da soma é: 20 |
| 10 | 5 | - | FALSE | TRUE | FALSE | FALSE | 5 | O resultado da subtração é: 5 |
| 5 | 3 | x | FALSE | FALSE | TRUE | FALSE | 15 | O resultado da multiplicação é: 15 |
| 99 | 33 | / | FALSE | FALSE | FALSE | TRUE | 3 | O resultado da divisão é: 3 |

### Exercício 04 (2.5 pontos)
Elaborar um algoritmo que, dada a idade, classifique nas categorias: infantil A (5 - 7 anos), infantil B (8 -10 anos), juvenil A (11 - 13 anos), juvenil B (14 -17 anos) e adulto (maiores que 18 anos).

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite uma idade: }}
B --> C[/I1/]
C --> D{5 >= I1 <=7}
D --TRUE--> E{{A categoria é infantio A}}
E --> F([FIM])
D --FALSE--> G{8 >= I1 <= 10}
G --TRUE--> H{{A categoria é infantia B}}
H --> F
G --FALSE--> I{11 >= I1 <= 13}
I --TRUE--> J{{A categoria é juvenil A}}
J --> F
I --FALSE--> L{14 >= I1 <= 17}
L --TRUE--> K{{A categoria é juvenil B}}
K --> F
L --FALSE--> M{I1 >= 18}
M --> N{{A categoria é adulto}}
N --> F
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO categoria
DECLARE I1 NUMERAIS
INICIO
ESCREVA "Digite uma idade: "
LEIA I1
SE I1 5 >= I1 <= 7 ENTAO
	ESCREVA "A categoria é infantil A"
	SENAO
	8 >= I1 <= 10 ENTAO
		ESCREVA "A categoria é infantil B"
		SENAO 
		11 >= I1 <= 13 ENTAO
			ESCREVA "A categoria é juvenil A"
			SENAO 
			14 >= I1 <= 17 ENTAO
				ESCREVA "A categoria é juvenil B"
				SENAO
				I1 >= 18 ENTAO 
					ESCREVA "A categoria é adulto"
				FIM_SE
			FIM_SE
		FIM_SE
	FIM_SE
FIM
```

#### Teste de mesa (0.5 ponto)

| I1 | SAIDA | 
|      --      |      --      | 
| 6     | A categoria é infantil A |
| 9   | A categoria é infantil B |
| 12   | A categoria é juvenil A |
| 15   | A categoria é juvenil B |
| 20| A categoria é adulto |
