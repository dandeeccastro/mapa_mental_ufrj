#Consistência e replicação

- Replicação: Técnica para aumentar a confiabilidade ou o desempenho do sistema
- O que é? Réplicas tanto dos dados quanto do sistema de acesso deles
- Tem a ver com tolerância à falhas
	- Se uma réplica falha, temos outra rodando então está safe
	- Podemos proteger contra corrupção de dados, fazendo comparações com outras réplicas
- Replicação pra melhorar desempenho
	- Queremos compensar a perda de desempenho com o crescimento do sistema
	- Tanto quando tem muita gente acessando (réplica divide a carga de trabalho)
	- Quanto quando temos uma área muito ampla (réplica permite redução de atraso ao acesso dos recursos)
- Mantendo as réplicas confiáveis
	- Quando uma réplica é alterada, ela agora é a outcast do sistema
	- Todas as outras réplicas precisam se atualizar com a outcast antes da próxima operação, para garantir a consistência
	- Quando e como replicar define o custo dessa replicação 
		- Imagina que o processo de replicar atrasa mais ainda ele
		- Podemos ter mais atualizações de réplicas do que operações no sistema
		- Alternativa: Relaxar as restrições de consistência para que a performance não morra no processo
