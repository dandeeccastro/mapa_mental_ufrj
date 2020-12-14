# Múltiplas Fitas na Máquina de Turing

## Introdução

- E se aumentarmos os recursos dela? Podemos aumentar o poder computacional?
- Exemplos de ideias:
	- Fita infinita para os dois lados
	- Mais de um cabeçote de leitura/escrita
	- Mais fitas para leitura/escrita
	- Movimentação de cabeçote com menos restrições
- Resultado: não obtemos mais poder computacional (por que?)

- Qualquer linguagem decidida, semi-decidida, ou funções, computadas por Máquinas de Turing "turbinadas", podem ser computadas por uma máquina de turing padrão
	- E demora mais (mais passos por causa dos recursos maiores)

## Máquinas de Turing com Múltiplas Fitas

- A função de transição mostra que ações realizadas em uma fita dependem dos símbolos lidos em todas as outras fitas
- Ela depende de todos os símbolos lidos em todas as fitas para computar um símbolo em uma fita
- Não existe processamento paralelo aqui, precisariamos de mais máquinas de Turing ao mesmo tempo, não uma só
- Simulando MT com múltiplas fitas em uma MT de uma fita só
	- Lembrando: cada fita possui uma quantidade finita de espaços que não estão em branco
	- Tem sempra uma casa a partir da qual todas à direita estão em branco
	- Adicionamos um símbolo no alfabeto que serve como separador de fitas 
	- Aí fica fita 1 > separador > fita 2 > separador...
- Também temos que representar os k cabeçotes de fita pra uma fita com um cabeçote só
	- Fazemos isso diferenciando os alfabetos de cada fita na nossa fita única
	- Símbolos com ponto em cima deles => O símbolo que tem o cabeçote na fita
- Detalhes importantes 
	- Movi o pseudo cabeçote pra esquerda e parei no divisor? Cheguei no triangulo da fita
	- Fui pra direita e cheguei no divisor? Fui para o espaço vazio 
		- E se é pra escrever no branco? A gente ia escrever no divisor e fuder o role
		- Nesse caso a gente faz um shift right na fita, liberando um espaço
		- Símbolo desse espaço: espaço em branco com ponto
	- Indicador disso: marcador com ponto

## Máquina de Turing não Determinística

- Função de transição agora é em $\Delta$ ao invés de $\delta$
- Entradas iguais da determinística, mas as saídas mudaram
	- Antes era um par de estados e tal
	- Agora temos um conjunto de pares com ação e estado, e a máquina escolhe um pra fazer
- Máquinas de Turing Não Determinísticas Decisórias 
	- Ao menos uma palavra tem que terminar com S pra linguagem ser decidida pela máquina
	- Pra elas, TODAS AS COMPUTAÇÕES tem que dar o resultado desejado pra uma função f
	- Não podemos dizer que uma máquina decide uma função se 1 + 1 dá 2 mas às vezes 3
- Simulando não determinismo com determinismo
	- Ordenamos as transições para que a gente possa executá-las de forma ordenada
	- Primeiro: o estado inicial é o estado final?
	- Vamo fazer uma máquina de turing determinística com 3 fitas
		- Podemos fazer ela virar de uma fita, como provado anteriormente
		- Primeira fita: palavra w, para poder ser usada em configurações diferentes
		- Segunda fita: onde as coisas vão ser computadas	
		- Terceira fita: Usa o alfabeto 1 à $\Beta$, esse último sendo o máximo de possíveis transações em uma determinada configuração da não determinística
	- Funcionamento
		- Usamos a primeira pra conferir os símbolos da palavra, sem sobrescrever ela
		- A segunda vamos usando para escrever os resultados e etc
		- A terceira fita indica qual transição vai ser usada, sendo o número representante da transação ordenada que pode ser utilizada
		- Ele vai escrevendo na terceira a ordem da escrita, tipo 1423, indicando que usamos primeira, quarta, segunda e terceira
		- Vamos testando um por um, primeiro com 1,2,3,4,... depois 11,12,13,14....
	- Complexidade do número de passos: exponencial
		- Não se sabe se isso é intrínseco do não determinismo ou só pq a gente é burro
		- PROBLEMA ABERTO DE COMPUTAÇÃO!!
