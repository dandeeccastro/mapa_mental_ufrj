# Limitações da Máquina de Turing

## Problema da Parada

- Resumindo a ideia do Problema da Parada
	- Temos linguagens recursivamente enumeráveis, que são *aceitas* por Máquinas de Turing
	- Temos linguagens recursivas, que são *decididas* por Máquinas de Turing (decisores somente)
	- A ideia do problema da parada é codificar uma MT e decidir se uma palavra w é aceita ou não por ela
	- Resolver esse problema significa simplesmente falar que toda linguagem recursivamente enumerável é recursiva
	- Isso é impossível considerando os anéis de Chomsky, que determinam que Linguagens Regulares são um subconjunto próprio de Linguagens Recursivamente Enumeráveis

- Vamos usar um mesmo raciocínio para provar três verdades distintas
	1. Existem problemas que são algoritmicamente insolúveis (não podem ser decididos por uma MT)
	2. A classe de linguagens recursivas é um subconjunto próprio da de recursivamente enumeráveis
		- Podem haver linguagens recursivamente enumeráveis que não são linguagens recursivas
	3. As linguagens recursivamente enumeráveis não são fechadas por complemento 

- Vamos supor um algoritmo P
	- Ele recebe um código A e a entrada desse código
	- Objetivo dele é saber se o código vai parar ou nunca para com a entrada especificada
- Ia ser um algoritmo muito interessante de se existir para testar softwares com loops infinitos
- Esse algoritmo resolveria o **Problema da Parada**, mas esse algoritmo também é **impossível de existir**
- Vamos (infelizmente) provar que isso é verdade

- Vamo considerar uma linguagem H que é formada pelos símbolos de MTU
	- Essa linguagem aceita palavras no formato c(M)Zw
		- c(M) é a codificação da MT que está sendo testada
		- Z divide a codificação
		- w é uma palavra com símbolos de MTU que, quando usada como input do MT, faz com que ela pare, termine de processar
- Só as MT que sejam capazes de processar w ajudam a compor a linguagem H
- A linguagem H é uma linguagem recursivamente enumerável (por que mano???)
- Já que w é feito com símbolos de MTU, é fácil montar uma MT que transforma c(M)Zw em c(M)Zc(w)
- Se temos a MT que faz essa transformação, o próximo passo é montar uma máquina que transforme essa outra na MTU
	- Se tivermos um MTU que computa esse tipo de coisa, podemos dizer quando ela para e quando ela não para
	- Uma vez que temos uma máquina que aceita H, podemos dizer que H é recursivamente enumerável

## Outros problemas que não podem ser resolvidos por MT's

1. Dadas duas LLC, a interseção delas é LLC?
2. Dada uma Linguagem Livre de Contexto, ela é Regular?
3. Dada uma Linguagem Livre de Contexto, ela é inerentemente ambígua?

- Sabendo que o Problema de Parada não tem solução, podemos usar *redução* para mostrar que outros também não podem ser resolvidos
- Redução: dada duas linguagens L1 e L2, existe uma redução se pudermos encontrar uma função computável f tal que 
	- Se w pertence à L1, então f(w) pertença à L2
	- Se w não pertence à L1, então f(w) não pertença à L2
	
