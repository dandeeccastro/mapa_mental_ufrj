# Nomeação Estruturada e Baseada em Atributos

## Estruturada

- Nomeação com maior legibilidade para os usuários finais dos sistemas
	- Nomes de arquivos, domínios da Web, URLs
	- Aqui onde entra o DNS e o NFS, não na [[Nomeação Simples]]
- Nomes estruturados são gerados em espaços de nomes (namespaces)
	- Estrutura de árvore: cada no pai indo pro filho até chegar na folha montam o nome da entidade
	- É um grafo direcionado acíclico e com uma única raiz (diretório central)
		- Endereço da entidade é o caminho dela até chegarmos no nó que representa ela
	- Nó com várias arestas: coleção de entidade (nó de contexto ou diretório)
		- Nó folha representa uma entiadde só e tem informações sobre ela
		- Nó diretório tem uma tabela onde cada entrada é uma aresta que a pessoa pode ir naquele caminho (identificador do nó, rótulo da aresta)
		- Nós diretório podem estar em máquinas diferentes se o grafo for distribuído
		
## Baseada em Atributos

- Não preciso saber o nome dessa entidade, podemos procurar ela via os atributos que ela tem
- Entidades são descritas como uma coleção de pares de atributo e valor	
	- Busca por atributo pode nos dar mais de uma entidade
- Sistemas de nomeação baseado em atributos são conhecidos como serviços de diretórios
	- Exemplo de protocolo assim é o LDAP (Lightweight Directory Access Protocol)
