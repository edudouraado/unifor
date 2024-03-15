# UNIFOR
**Nome**: Eduardo Dourado Sales de Oliveira <br>
**Disciplina**: Raciocínio lógico algorítimo

## Listas de exercícios 01

### Exercício 3
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou ímpar.

### FLUXOGRAMA

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[/num/]
C --> D{num >= 0}
D --FALSE--> E{{O número deve ser positivo!}}
E --> F([FIM])
D --TRUE--> G[resto = num % 2]
G --> H{resto == 0}
H --FALSE--> I{{O número é ímpar}}
H --TRUE--> J{{O número é par}}
I --> F
J --> F
```
#### PSEUDOCÓDIGO
```
ALGORITMO verifica_par_impar
DECLARE num, resto: INTEIRO
INICIO
ESCREVA "Digite o número: "
LEIA num
SE num > 0 ENTAO 
	resto <- num % 2
	SE resto == 0 ENTAO
		ESCREVA "O número é par!"
	SENÃO
		ESCREVA "O número é ímpar!"
	FIM_SE
SENAO
	ESCREVA "O número deve ser positivo!"
FIM_SE
FIM
```

#### TESTE DE MESA
| num | num >= 0 | resto | resto = 0 | saída |
| -- | -- | -- | -- | --|
|  -1  |  False  |    |    |  "O número deve ser positivo"  |
|  0  |  True  |  0  |  True  |  "O número é par!"  |
|  10  | True  |  0  | True  |  "O número é par!"  |
|  11  | True  | 1  |  False  |  "O número é ímpar!"  |
