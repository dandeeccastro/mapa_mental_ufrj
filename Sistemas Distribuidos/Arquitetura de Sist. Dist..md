# Arquitetura de Sistemas Distribuídos
Assim como sistemas locais, sistemas distribuídos possuem diferentes tipos de arquiteturas e itens específicos do qual eles são feitos. 
## O que faz parte da arquitetura?
Num modelo de sist. dist. temos dois itens principais: **componentes**, que são as partes do software que lidam com o problema que precisa ser resolvido, e **conectores**, que são responsáveis pelas conexões entre componentes.

## Quais os tipos de arquitetura?
- **Em camadas**
	- Forma mais hierárquica, onde camadas superiores se comunicam às inferiores, que reportam resultados para as superiores e assim vai.
- **Orientado a Objetos**
	- Cada componente é interpredado no programa como sendo um Objeto, seguindo os padrões de OOD
- **Orientado a Recursos**
	- A comunicação é feita primariamente para gerência de recursos na aplicação, como movimentação no banco de dados e em arquivos
- **Orientado a Eventos**
	- Certos objetos emitem eventos, e outros objetos reagem à esses eventos em outros lados da aplicação