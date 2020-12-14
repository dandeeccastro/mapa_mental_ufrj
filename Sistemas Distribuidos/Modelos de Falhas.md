# Modelos de Falhas

- Falhas são modelos que descrevem como um sistema pode dar xabu 
- Tolerância à falhas se resume à definir qual tipo de modelo de falha você aceita no seu sistema

- Tipos de falhas
	- Crash / Parada: Deu pau o sistema todo para 
		- Pode ser silencioso (nenhum outro nó sabe que você caiu) ou não
	- Temporal: Erros que dizem respeito ao tempo
		- A síncronização pode ter passado de um threshold importante 
		- A requisição demorou tempo demais para ser respondida
	- Omissão: Quando um processo não consegue responder às mensagens
	- De Resposta: A resposta do sistema é incorreta
		- Ou o valor é incorreto
		- Ou a resposta era para outra pergunta, então o formato não é compreendido
	- Bizantinas: Xabus diferentes dos aqui de cima, sem prejuízo claramente identificável
		- Aqui podem entrar o trabalho de hackers ou falhas deliberadamente causadas 
		- Nós que falharam continuam interagindo no sistema 
		- Outros nós não sabem encontrar a falha, ou se sabem que tem falha, não sabem dizer aonde

- Detectando falhas 
	- Idealmente, temos que considerar os resultados das falhas em sistemas síncronos e assíncronos
	- Sistemas assíncronos são complicados porque uma falha não necessariamente implica numa perda de performance ou comunicação
	- Sistemas síncronos são mais tranquilos 
		- Se um processo P envia mensagens para Q mas não recebe resposta, depois de um momento podemos dizer que Q foi de base
	- Na vida real, nenhum sistema é totalmente síncrono ou assíncrono
		- Sistemas parcialmente síncronos tem partes síncronas e assíncronas
		- Ex: sistemas com funcionamento síncrono mas que usam partes assíncronas para detectar problemas
		- Pode nos dar falsos positivos tho
			- Um processo demorou mas respondeu? Se demorar mais do que X é dado como problemático, independente de ter voltado

- Detectando falhas na parada de processos
	- Dois jeitos
		- Processos enviam mensagens para outros processos para saber se estão on, e esperam resposta
		- Processos aguardam mensagens dos outros ( só se aplica se temos garantia que a comunicação rola ) 
	- Processos que não respondem entram na lista de suspeitos (parcialmente síncronos)
	- Pode ser problema de comunicação entre os nós
		- Tipo, o nó está ok mas a comunicação dele não
		- Como distinguir isso? Testamos a comunicação do nó com os outros
			- Conseguiu conversar? Falha de processo
			- Não conseguiu conversar? Falha de comunicação 
