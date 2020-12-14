# Máquina de Turing Extended

## Diagramas de Composição

- Forma compacta de descrever uma Máquina de Turing
- Como elas podem fazer tarefas não tão simples, a tabela de função cresce
- Podemos descrever o funcionamento com um _diagrama de composição_
- Componentes do diagrama
	- Máquinas Básicas 
		- Máquina $D$: A máquina que move o cabeçote para a direita
		- Máquina $E$: Move a máquina para a esquerda se possível (sem ir para o triângulo)
		- Máquina $W_a$: Escreve o símbolo a na posição atual na fita
			- É uma familia de máquinas, cada uma escreve um símbolo
		- Máquina $P$: Máquina que não faz nada na fita
		- Para construir decisores:
			- Máquina S: Para no estado de aceitação
			- Máquina N: Para no estado de rejeição
	- Regras de Composição
		- Regras que definem como as máquinas básicas se juntam 
		- Descrição do Diagrama que eu to vendo
			- Uma caixa tracejada com um M fora (representa a máquina M)
			- >M0 no começo, várias setas com sigma 1 a k indo pra M 1 a k
		- A composição
			- Computação começa com M0, e quando M0 terminar sobra um símbolo na fita
			- M continua a computação 
				1. Verificando qual símbolo é (sigma 1 a k)
				2. Levando para a máquina que deve continuar (M 1 a k)
				3. Caso o símbolo n seja sigma 1 a k, M para quando M0 para
		- Convenções de Notação
				- Diagramas em que símbolos a e b levam para outra máquina
					- Ao invés de desenhar duas setas de M1 pra M2
					- Desenhamos uma seta com os dois símbolos a,b em cima
		 		- Diagramas em que qualquer símbolo leva M1 pra M2
					- Ao invés de desenhar a seta de M1 pra M2 sem símbolo	
					- Escrevemos M1M2, um do lado do outro
				- Diagrama em que qualquer símbolo leva M1 pra M2 MENOS sigma
					- Ao invés de escrever seta com a =/= sigma em cima
					- Escrevemos sigma com uma linha por cima (sinal de negação)
				- Máquinas que representam diagramas
					- E_sigma: Máquina que vai pra esquerda até achar o sigma
					- É representado pelo E com seta sigma linha pra si mesmo
					- D_sigma: Mesma coisa que o E_sigma mas pra direita
					- E_sigma barra: Vai pra esquerda até achar algo diferente de sigma
					- D_sigma barra: Análogo ao E_sigma barra mas pra direita

## Exemplos de Máquinas de Turing

- Máquina que computa f(x) = x + 1
	- Vamo mudando todos os uns para zero 
	- Se achamos um zero, mudamos para um e a máquina para
	- Único caso não coberto? Máquina só com uns (ele chega no triângulo, F)
