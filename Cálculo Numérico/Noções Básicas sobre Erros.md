# Noções Básicas sobre Erros
## Introdução

Quando lidamos com cálculos dentro de um computador, as coisas não são tão precisas quanto gostariamos que fossem. Certos cálculos podem dar resultados um tanto quanto estranhos, se comparados com a solução feita por um humano

- Ex: Somatório de 30 mil vezes do número 0,11	
	- Se fizermos isso manualmente, sabemos que o resultado é 30.000 x 0,11 = 3300
	- Em computadores, o resultado pode aparecer como 3299,99691

## Por que isso acontece?
Números podem ser representados por meio de várias bases numéricas diferentes. Como seres humanos, estamos acostumados a utilizar a _base decimal_ (já que temos 10 dedos, faz bastante sentido o digito virar quando chegamos no décimo).

Em computadores, vemos o uso da _base binária_, dado que eles são feitos de círcuitos que possuem dois estados: ligado ou desligado. Esses dois podem ser representados com dígitos: 0 ou 1.

Logo, quando lidamos com computadores, o que acontece é:
1. **Inserimos** a informação em base decimal no computador
2. Ele **transforma** isso em base binária 
3. Ele faz os **cálculos** necessários para a resolução do problema
4. Ele **transforma** o resultado em base decimal
5. Ele nos retorna o resultado na nossa base

Todos os processos que estão marcados nos itens acima estão propensos à erros, tanto _na entrada dos valores_ quanto _dentro da máquina_

- Inserindo os números
	- Certos números não tem representação finita na base 10, levando a aproximações
		- Ex: pi, constante de Euler
	- Valores medidos manualmente podem ter inconsistências
- Dentro da máquina
	- Alguns números tem representação finita na base 10, mas infinita na base 2, forçando a [[Conversão Decimal - Binária|conversão]] a aproximar o valor
	- Certos cálculos matemáticos com esses números podem ser imprecisos, considerando o [[Aritmética de Ponto Flutuante| limite de dígitos ]] de um computador
