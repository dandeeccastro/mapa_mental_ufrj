# Introdução
## O que?
Sistemas Distribuídos pode ser definido como uma coleção de _elementos de computação autômatos_ que se comunicam e cooperam para realizar uma **tarefa final**.   

** Exemplos **
- **Aplicativos Web** => Dividem processamentos pesados e lógica de negócio para o servidor, deixando o cliente só como meio de acesso
- **Sistema de controle de aeronave** => Cada elemento de computação faz uma coisa na aeronave, a cooperação entre esses nodes faz com que ela vôe e opere de forma coesa
- **Processamento de dados meteorológicos** => Pode ser feito com uma máquina, mas por ser um cálculo complexo, é melhor realizado quando dividido.
- **Compartilhamento de Arquivos** => Melhor do que ter um arquivo em um lugar é um arquivo em um lugar que pode ser acessado de outros lugares

 ## Por que?
 Alguns exemplos de ganhos diferentes que podemos ter com sistemas distribuídos são: 
 - Podemos **compartilhar recursos**, como dispositivos (impressoras), páginas Web, bancos de dados, assim como processamento, armazenamento e memória.
 - Nos permite **gerenciar** esses mesmos recursos via clientes remotos, como gerenciamento de servidor via SSH
 - Nos permite **integrar agentes e fontes de informação** diferentes para criar soluções de problemas complexos, como sensores de fumaça para detecção de incêndios. 

## Como?
### Algoritmos Distribuídos
Nesses sistemas usamos algorítmos distribuídos, que devem ser feitos pensando não só nos problemas de algorítmos normais (falhas de hardware, erros padrão e etc), mas também com todas as dinâmicas de distribuição de tarefas:
- Quando processadores e meios de comunicação estão _operando em diferentes condições_
- Quando um dos nodes _sofre uma falha, mas o sistema tem que continuar_

### Processo de Planejamento
Envolve **projetar**, **implementar** e depois **avaliar** os algorítmos que rodam conectados por meio desses canais de comunicação. Se fosse para botar em termos gerais, podemos fazer da seguinte forma:
- **Dividimos tarefas** que podem ser colocadas em execução concorrente e em máquinas diferentes.
- Definimos como será o tipo de **agrupamento e cooperação** entre as máquinas, e como controlaremos sua evolução.
- Gerenciamos **heterogeneidade** de hardware e software, assom como **possibilidade de falhas** tanto em processos quanto em comunicação.

## Desafios de Sist. Dist.
- Heterogeneidade
- Segurança
- Escalabilidade
- Tratamento de Falhas
- Concorrência
- Transparência
- Forma de acesso aos serviços