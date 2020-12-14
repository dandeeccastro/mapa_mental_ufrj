# Marcamento de falhas usando Replicação 

- Um jeito de lidar com falhas é esconder ela de outros processos
- Podemos fazer isso com redundância
	- Redundância de Informações
		- Adicionar informações extras nos dados para que eles possam ser recuperados em casos de falha
	- Redundância de Tempo
		- Ações não dependerem do tempo, podem ser feitas N vezes durante a vida 
		- Útil para recuperar falhar transitórias e intermitentes, porque eventualmente o nó volta a se estabilizar com elas
	- Redundância Física
		- Replicamos recursos ou componentes físicos
		- Se um lado dá xabu, temos o outro pra compensar

- Redundância Física
	- Proteger falhas em processos pode ser feito replicando eles em grupos
	- De forma que se um cai, outros estão ali para substituir
	- Eles precisam ser gerenciados com algo tipo um Load Balancer
	- Mensagens vão para todos os processos
		-	Assim eles estão sempre iguais um ao outro
		- Podemos usar mecanismos de sincronização para garantir que uma delas não está atrás

- Grupos de Processos Replicados 
	- Eles podem ser organizados de duas formas
		- Ou todos são iguais e as decisões do sistema são tomadas coletivamente (implica uso de multicast entre eles)
		- Ou tem uma hierarquia de processos, onde um é lider e toma as decisões, por exemplo
			- Essas decisões podem ser sobre ordem de execução e de gerenciamento do grupo
	- Tolerância à Falhas? Podemos usar protocolos de cópia primária e de escrita replicada!
		- A cópia primária pode coordenar todas as escritas, e quando ela falha, outra cópia primária é eleita
		- Podemos eliminar o ponto de falha único com coordenação distribuída, mas é mais avançado

- Tamanho dos grupos de processos 
	- K-fault tolerant: Grupo de processos tolerante à falhas em K nós
	- Se a falha for silenciosa, k+1 processos são suficientes (por que???)
	- Se a falha não for silenciosa, 2k + 1 (k processos falhando, temos k+1 processos gerando respostas corretas e iguais) (ainda boiando)
	- Se mais de k processos falham, o grupo não tem como imitar o comportamento de um único processo robusto

- Esses modelos de falhas também se aplicam à camada de comunicação
- TCP pode mascarar falhas de omissão na forma de mensagens perdidas
- TCP usa confirmação de recebimento (ACK) e retransmissões como mecanismo de resolução de problemas
- Falhas de parada não são tratadas pelo TCP, ele só morre e não transmite mais mensagens
