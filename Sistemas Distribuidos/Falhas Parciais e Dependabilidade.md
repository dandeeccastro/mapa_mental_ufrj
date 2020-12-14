# Falhas Parciais e Dependabilidade

- Falhas parciais: quando parte do sistema falha enquanto o resto continua operando
- Desafio é construir um sistema que seja capaz de se recuperar de uma falha parcial

- Tolerância à falhas: termo acadêmico para o estudo do comportamento de sistemas distribuídos quanto à ocorrência de falhas
- Na indústria: "sistemas de alta performance" ou "sistemas redundantes"

- Dependabilidade: termo que engloba alguns requisitos
	- Disponibilidade: ele tá pronto para uso no momento
	- Confiabilidade: executar contínuamente sem falhas
	- Operação segura: se o sistema falha, nenhuma catástrofe rola
	- Mantenabilidade: Facilidade de reparar as falhas que rolarem
	- Segurança: Capacidade de lidar com ataques maliciosos

- Classificando os problemas 
	- Sistemas falham quando algo acontece que impede que eles façam o esperado
	- Erro é quando ele tem uma falha, um evento temporal
	- Erros são causados por defeitos

- Tipos de defeitos
	- Transiente: uma vez para nunca mais
	- Intermitente: apareçe de vez em quando mas some
	- Permanente: Continuam a acontecer até que o componente com problema seja substituido

- Lidando com defeitos 
	- Podemos prevenir eles, construindo sistemas que idealmente nunca encontrarão defeitos na vida (Prevenção)
	- Podemos verificar e remover eles conforme necessário (validação) 
	- Podemos estimar a presença e consequência dos defeitos (previsão)
	- Podemos prover o sistema funcionando mesmo com a existência de defeitos (tolerância)

