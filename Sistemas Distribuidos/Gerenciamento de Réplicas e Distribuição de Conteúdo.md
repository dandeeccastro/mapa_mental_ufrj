# Gerenciamento de Réplicas e Distribuição de Conteúdo

- Onde, quando e por quem as réplicas devem ser colocadas: a grande questão 
- Quais mecanismos usamos para manter elas consistêntes?

- Posicionamento de Réplicas
	- Melhor localização pode ser definida usando parâmetros relacionados à gerência e custo de operação
- Posicionamento de Conteúdo
	- Como escolher a melhor réplica para se colocar um conteúdo

- Três tipos de réplicas com relação à posicionamento de conteúdos
	- Réplicas permanentes
		- Conjunto inicial de réplicas de uma base de dados 
		- Pequeno e configurado estaticamente
		- Exemplos
			- Arquivos de site replicados em uma mesma localização: requisições são encaminhadas para um deles baseado num sisteminha de balanceamento de carga
			- Uso de espelhamento: O site é replicado para alguns servers geograficamente espalhados
	- Réplicas iniciadas pelos servidores
		- Cópia do BD para melhorar desempenho, criada pelo gerente da base de dados
		- Geralmente usado para atender uma demanda espontânea de acesso
		- Para leitura, geralmente
	- Réplicas iniciadas pelos clientes
		- Facilidade de armazenamento local usado por um cliente para temporariamente armazenar uma cópia do dado requisitado com ele (conhecido como caches)
		- Gerência do cache é do cliente
		- Pode contar com a base de dados para notificar atualizações 
		- Mantém por tempo limitado para prevenir desatualização ou dar espaço para outros dados
		- Podemos compartilhar cache entre vários clientes
			- Caches em máquinas compartilhadas em uma rede local
			- Servidores de cache

- Algumas tretas que se tem que tratar às vezes
	- Estado X Operação (define o que propagar): notificações de atualizações, dados ou operações
		- Propagação de Notificações: as réplicas são informadas que teve atualização (bom quando as atualizações são mais frequentes que as leituras)
		- Transferência de dados: pode agregar várias atualizações (bom quando leituras são mais frequentes que atualizações)
		- Propagação de operações: assume que tem um processo associado à réplica, para que ela performe a operação no dado (envia somente as operações e os parâmetros dela)
	- Protocolos pull X push: quem dispara essas atualizações
		- Push: as atualizações são propagadas sem que a réplica tenha pedido 
		- Pull: só quando eu peço a atualização que eu mudo a réplica

