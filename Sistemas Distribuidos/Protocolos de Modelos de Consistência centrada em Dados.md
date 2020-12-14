# Protocolos de Modelos de Consistência centrada em Dados

- Protocolos de Consistência
	- Descrevem implementações específicas de cada modelo de consistência
	- Na prática, implementamos modelos de consistência que são simples de se entender
		- Incluem os que delimitam desvios de desatualização
		- Incluem menos os que lidam com desvios numéricos
		- Geralmente, o utilizado é a consistência sequencial, com agrupamento de operações via bloqueio 

- Protocolos basedos em cópias primárias
	- Cada item X tem uma cópia primária associada que coordena as operações de escrita ou atualização
	- Duas formas:
		- Escrita remota: cópia primária fixa (um servidor com ela)
			- Escrita bloqueante até que todas as cópias sejam atualizadas
			- Implementação direta da consistência sequencial
			- Também chamado de protocolo de backup primário
		- Escrita local
			- Cópia primária possa migrar entre os processos ao invés de ficar presa em um
			- Processo quer atualizar X? Achamos ele primeiro e puxa para si
			- Várias escritas sucessivas podem ser feitas localmente, enquanto os outros processos mantém acesso à leitura local
			- Atualizações propagadas depois que todas as escritas são concluídas
			- Alternativa: Servidor primário que nem na escrita remota, mas que concede por um tempo o direito de escrita para alguma réplica
				- No final, recebe as atualizações e publica
				- Usado em sistemas de arquivos distribuídos

- Protocolos de escrita replicada
	- Replicação ativa
		- Um processo associado a cada réplica que cuida das atualizações 
		- Desafio: operações tem que ser propagadas em ordem total (multicast atômico)
		- Alternativa: temos um coordenador central para lidar com essas coisas
			- Ele recebe as solicitações de operações, atribui números sequenciais distintos e encaminha para as outras
		- Alternativa para escalabilidade: Vários sequenciadores fazendo multicast entre si usando relógios de Lamport
	- Votação
		- Cada processo tem que pedir permissão de vários servidores para ler e escrever na sua réplica
		- Leitura e escrita tem que ter consentimento de metade mais uma réplicas
		- Item X passa a ter uma versão nova armazenada nas réplicas que consentiram
		- Para ler X, o cliente pede as réplicas que mandem seu número de versão mais recente
			- Se a maioria lança o mesmo número, ela é a mais recente

