# Sistemas Lineares
## Definindo o problema
- Múltiplas equações para determinar o valor de uma ou mais variáveis
- Problemas oriundos da Álgebra Linear
	- Equações são uma tranformação que pode ser representada como matriz
	- Valores a serem obtidos podem ser representados como um vetor
	- Queremos achar $x$ tal que $x=Ab$, $A$ sendo o sistema de equações em forma de matriz
- Nomenclaturas
	- $A$ = matriz do problema
	- $x*$ = solução exata de $x = Ab$
	- $\overline{x}$ = solução aproximada de $x = Ab$
## Visualizações
- Possíveis soluções para um sistema linear
	- Uma única solução
		- Quando a matriz $A$ transforma um vetor em outro vetor na mesma dimensão
			- $\mathbb{R}^2 \to \mathbb{R}^2$
		- Graficamente podemos imaginar que a solução $x*$ é o ponto de cruzamento dos vetores que compõem a matriz $A$
	- Infinitas soluções 
		- Quando a matriz $A$ "achata" o vetor, reduzindo a dimensão dele
			- $\mathbb{R}^2 \to \mathbb{R}$
		- Graficamente, os vetores que compõem $A$ são coincidentes, ou seja, a mesma linha
			- Existem infinitos $x$ em $\mathbb{R}^2$ que podem pertencer à uma reta
	- Não há solução 
		- Quando a matriz $A$ não admite solução
		- Graficamente, a matriz $A$ é feita de retas paralelas
			- Sem interseção entre elas, é impossível achar um vetor $x$

## Generalização
- Generalizando a matriz $A$
	- Agora temos uma matriz $A: m \times n$
		- $m$ é a dimensão de $b$
		- $n$ é a dimensão de $x$
	- O problema em português: "dado um $b$ de dimensão $m$, se possível, tenho que obter um vetor $x$ com $n$ dimensões tal que $Ax = b$"
	- Perguntas que temos que responder:
		- Tem um $x*$ de $n$ dimensões tal que $Ax* = b$?
		- Se ele existe, ele é único?
		- Como eu posso obter ele?

## Conceitos
- Imagem de uma matriz $A$: conjunto de vetores $y$ de $m$ dimensões que podem ser obtidos por vetores $x$ de $n$ dimensões tal que $y = Ax$
- O Posto de uma matriz $A$ é a dimensão na qual a imagem dela pertence
- Analisando os tipos de soluções com os conceitos
	- $A$ é feito de vetores _linearmente independentes_.
		- Gera vetores que servem como base para $\mathbb{R}^2$, logo a imagem é $\mathbb{R}^2$
		- Possuem solução única
		- Chamamos sistemas assim de **compatível determinado**
	- $A$ é feito de vetores _lineramente dependentes_, que não formam base para $\mathbb{R}$
		- No caso de soluções infinitas
			- O vetor $b$ pertence à reta gerada por $A$
			- Chamamos o sistema de **compatível indeterminado**
		- No caso de não haver solução
			- O vetor $b$ não pertence à imagem de $A$
			- Chamamos o sistema de **incompatível**
- Um pouco mais sobre postos
	- Se o posto de $A$ é o mínimo entre $m,n$, então o sistema é **posto-completo**
	- Se o posto de $A$ for menor que o mínimo entre $m,n$, então o sistema é **posto-deficiente**  
- Tipos de métodos numéricos para resolver sistemas lineares
	- Método Direto: usa uma forma de resolução direta, sem rodeios
	- Método Iterativo: aplica um vetor repetidas vezes na matriz até que o resultado tenda ao $x$ desejado.