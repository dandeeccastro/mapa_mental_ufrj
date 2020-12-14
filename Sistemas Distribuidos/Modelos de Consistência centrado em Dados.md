# Modelos de Consistência centrados em Dados

- Consistência no contexto de operações que escrevem e lêem dados num BD compartilhado
- Cada processo mantém uma réplica perfeita das informações 
- Operações de escrita são propagadas para toda a rede de réplicas
- A ideia é que a operação de leitura sempre devolva o dado correto, atualizado 
	- Sem um relógio global, dizer qual foi a última escrita é complicado 
	- Modelos de consistência definem alternativas sobre a última atualização
		- Relaxamos o conceito de atualização pra poder garantir que o sistema não seja super restrito quanto ao uso e acesso dele 

- Não tem uma solução geral de modelo de consistência
	- Inconsistência tolerável depende de cada aplicação 
- Podemos dividir quais inconsistências uma aplicação deve tolerar
	- Desvio de valores numéricos
		- Diferença absoluta ou relativa máxima entre réplicas 
		- Número de atualizações pendentes realizadas em uma réplica e não percebida pelas outras
	- Desvio de inatividade
		- Atraso na atualização de uma réplica
		- Pode ser uma atualização todo dia numa hora X
	- Desvio na ordem de execução 
		- Atualizações locais aguardando um acordo global

- Unidades de consistência: Um tipo de dado que tem que estar igual em todos
	- Podemos usar ele como um basteão para atualizar todas as réplicas, ou só uma delas
	- Atualizações nos dois lados? Usamos ferramentas de sincronização 

- Se queremos consistência contínua, a réplica tem que saber o quanto ela tá diferente das outras
	- Comunicação extra e separada para manter as réplicas informadas sobre os desvios
	- Essa comunicação não é barata (menos é mais quando se trata de troca de mensagens)

- Modelos com ordenação consistente de operações entre os dados 
	- Lidam ocom a questão de recursos compartilhados replicados 
	- Computação paralela distribuída geralmente precisa disso
	- Alguns tipos de técnicas pra isso
		- Consistência sequencial
			- Qualquer sequência de operações é aceitável, desde que todos os processos vejam a mesma sequência
		- Consistência causal
			- Só as operações com relações de causa-efeito tem que ser vistas na mesma ordem
		- Consistência pra operações agrupadas
			- Sequências de operações em dados agrupados são protegidos contra o acesso concorrente
			- Se o lock/unlock é usado, o sistema sabe que tem que sincronizar as cópias 
		- Consistência eventual
			- Eventualmente as réplicas se resolvem
			- Aplicações Web, onde um escreve nele e os outros lêem
			- Clientes geralmente acessam a mesma réplica
			- Único requerimento: que as atualizações sejam propagadas para todas as réplicas (eventualmente)
