# Relógios Lógicos
- Pra muitas aplicações, a ordem relativa dos eventos é mais importante que o tempo global
	- O make não quer saber a hora geral mas sim se um passo aconteceu antes ou depois do outro
- Bora considerar um evento como a ocorrência de uma ação de comunicação ou transição de estado
- Como a gente ordena esses eventos dentro de um processo individual?
	- Ele pode ser feito de forma única. Um estado vai pra outro porque um evento aconteceu
	- Podemos manter um histórico dos eventos facilmente
	- Uma linha do tempo dos eventos do processo
- Como ordenar os eventos num sistema distribuído?
	- Agora temos várias linhas de tempo para cada processo no sistema
	- Podem rolar ao mesmo tempo ou não
	- Eventos de comunicação podem demorar para serem recebidos por outros processos
	- Qual o critério? Encontrar o tempo sincronizado é complicado e seguir por ordem de eventos em cada máquina pode não refletir isso
		- Exemplo: Processos executam 4 eventos, então penso em ordenar em "lotes" do primeiro, segundo, terceiro e quarto evento
		- No entanto, e se a máquina no processo 2 tava renderizando algo e só conseguiu rodar o evento 1 quando o resto tava no evento 3?
		- Ou pior: evento 2 do processo 1 envia mensagem para o processo 3 gerar o evento 4, mas minha ordem nesse critério não reflete isso
	- Se um evento A causa um evento B, podemos gerar uma ordem baseado na causalidade
		- Isso independe do processo, porque um evento pode ser de comunicação 
	- Tem notação fofinha para isso
		- $a \to b$: evento $a$ rola antes do evento $b$
			- Eles são consecutivos na mesma máquina
			- O envio da mensagem em $a$ é recebida em $b$ 
			- Eles são relacionados por transitividade (evento $c$ só rolou por causa do $b$, e $b$ só existe porque $a$, logo...)
		- $a || b$: Os eventos são concorrentes
- Relógios de Lamport
	- Ele propôs o conceito de relógios lógicos
	- Algoritmo
		- Cada processo tem um contador, e a cada evento ele incrementa esse contador (menos em receive)
		- Quando o processo envia uma mensagem ao processo, ele envia o contador anexado
		- Quando o processo recebe uma mensagem, ele atualiza seu contador 
			- Contador local = máximo(Contador local, contador recebido) + 1
	- Dessa forma podemos construir a ordem deles e dizer quem precedeu e quem é paralelo!
	- Relógio de Lamport garante que se há causalidade entre eles, então o contador de um vai ser menor que o do outro