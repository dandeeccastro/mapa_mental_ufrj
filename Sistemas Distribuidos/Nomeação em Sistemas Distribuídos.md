# Nomeação em Sistemas Distribuídos
- Nomes são comuns em programação, mas quando elevamos o nível para sistemas distribuídos, nomear implica poder **identificar uma entidade** para, com isso, poder me comunicar com ela. 
	- Podem ser usernames, hashes gerados pelo sistema, etc.
- **Sistema de Nomeação** permite processos e entidades acessarem informações de comunicação de outros processos e entidades
	- Em sist. dist., eles existem _para cada processo_, então tem mais um problema para ser resolvido aí
	- **Tipos**
		- Nomeação Simples: Stringzona da massa
		- Nomeação Estruturada: Usando identificadores como descritores de arquivo para nomear
		- Nomeação baseada em Atributos: Como o nome diz, usando atributos da entidade para nomea-la
- Entidades ofereçem **operações** 
	- Impressora imprimindo arquivos, servidores oferecendo comandos...
- Processos precisam achar entidades pra fazer as operações
	- Solução: uma entidade especial que chamamos de **pontos de acesso**
		- Nome do ponto de acesso é referenciado como **endereço**
		- Endereço do ponto de acesso é o endereço da entidade associada a ele
		- Exemplo: 
			- Entidade Danilo tem uma entidade de ponto de acesso que é meu número de telefone
			- O nome do meu telefone (número dele) é considerado como meu "endereço"
	- **Não devemos botar como nome da entidade o endereço do ponto de acesso dela!**
		- Entidade pode mudar de ponto de acesso, ou esse ponto de acesso pode ser usado por uma entidade diferente
		- Assim a referência pra entidade via endereço fica inválida
			- Ex: Bad File Descriptors no PYChat
- Entidades podem ter **mais do que um** ponto de acesso
- Maior flexibilidade se usarmos **nomes independentes de localização**
- Questionamentos filosóficos da vida
	- Considerando DHCP, será mesmo que IP's são identificadores únicos, ou são somente apelidos?