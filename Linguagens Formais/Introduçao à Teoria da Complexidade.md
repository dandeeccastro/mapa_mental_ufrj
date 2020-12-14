# Introdução à Teoria da Complexidade

## Introdução 

- Classificar problemas em decidíveis ou não não nos fornece toda a informação necessária sobre esse problema
- Podem ter problemas decidíveis mas que são muito grandes para serem resolvidos
	- São os problemas chamados de *intratáveis*, os ineficientes na prática

## Complexidade de Tempo

- Máquinas de Turing Polinomialmente Limitadas
	- Temos uma função polinomial p(n) tal que toda entrada w que pertence ao alfabeto de MT
	- A MT é polinomialmente limitada se pra todo w de p(n), qualquer computação para em no máximo p(|w|) passos
	- Exemplo de função polinomial: x^3 + x^2 + 2

- Classe P é definida como a classe de todas as linguagens que podem ser decididas por uma MT determinística Polinomialmente Limitada
	- Problemas *tratáveis* são os problemas que pertencem à P

- Classe NP é definida como a classe de todas as linguagens que podem ser decididas por MT não determinística polinomialmente limitada
	- Problemas em NP são meio de adivinhar antes e verificar depois
	- Primeiro o lado não determinístico adivinha, dentro de um espaço de busca finito, se uma entrada pertence à linguagem, usando alguma "testemunha" ou "certificado"
	- Depois verificamos essa entrada deterministicamente em tempo polinomial
	- Se tem testemunha, tem uma computação que leva à aceitação, então foi
	- Se não tem testemunha, toda computação é rejeitada, então não foi

- Para que uma linguagem pertença á NP, é necessário que a verificação de testemunha possa ser feita em tempo polinomial
- Um problema em NP pode não ter um algoritmo eficiente para calcular a solução dele, mas pode ter um algoritmo eficiente para verificar se uma solução satisfaz o problema

- Exemplos
	- Linguagem formada pela codificação de todos os números compostos
		- A testemunha é um número maior que um e menor que X que seja um fator de X
		- Conferir se o número é uma testemunha == dividir X pelo número e ver se o resto é zero
	- Linguagem formada por grafos hamiltonianos
		- A evidência seria um caminho hamiltoniano pelo grafo
		- A verificação é andar pelo grafo	

- Teorema: P pertence à NP
	- Provando: Toda MT determinística é um caso particular de uma MT não determinístiva

- MT Exponencialmente Limitada
	- Mesma coisa para MT Polin. Lim., mas com mudanças pequenas
	- Temos uma constante inteira c > 1 e a função polinomial p(n)
	- O estado de parada é alcançado em no máximo c^p(|w|)	
 - Classe EXPTIME: classe de linguagens que podem ser decididas por uma MT determinística exponencialmente limitada
	- Outro nome comum é ETIME
- Classe NEXPTIME: EXPTIME pras não determinísticas
	- Problemas NEXPTIME também são de adivinhar, mas a verificação de que a testemunha é correta é feita em tempo exponencial

- Teorema: EXPTIME pertence à NEXPTIME
	- Mesma prova do P NP

- Teorema: NP pertence à EXPTIME
	- O que isso me diz? Que problemas com MT não determinísticas solúveis em tempo polinomial podem ser resolvidos por MT determinísticas em tempo exponencial
	- Provando: uma MT não determinística pode ser transformada numa MT determinística
	- O preço da transição pode precisar executar um número exponencial de operações
	- O aumento desse custo pode transformar o tempo polinomial em tempo exponencial 

- P pertence à NP pertence à EXPTIME pertence à NEXPTIME

## Complexidade de Espaço (Memória)

- Agora vamos pensar sobre coisas legais como memória e tamanho na fita
- Máquina de Turing Espacialmente Polinomialmente Limitada
	- Se dado uma função polinomial p(n) e uma palavra, a MT visita no máximo p(|w|) casas antes de parar

- Classes à partir desse tipo de coisa
	- PSPACE: classe das linguagens decididas por MT det. esp. pol. lim.
	- NPSPACE: classe das linguagens decididas por MT n. det. esp. pol. lim.
	- PSPACE contido em NPSPACE

- Tem como categorizar bem a relação de PSPACE e NPSPACE
- **Teorema de Savitch**: PSPACE = NPSPACE
	- Isso significa que o aumento exponencial de memória na transformação de PSPACE para NPSPACE não acontece, porque um é igual ao outro
	- A quantidade de memória que será utilizada vai ser só polinomialmente maior

- Teorema: P contido em PSPACE
	- A cada passo da computação, no máximo uma casa nova da fita é visitada
	- Se a máquina é pol. lim. e executa no max. f(|w|) passos, então ela visita no max. f(|w|) + 1 casas distintas da fita
	- f(|w|) + 1 é polinomial, então ela também é esp. pol. lim
- Também dá pra concluir que NP está contido em NPSPACE
- Mas NPSPACE = PSPACE, então NP tá contido em PSPACE

- Teorema: PSPACE contido em EXPTIME

- Finalizando: P contido em NP contido em PSPACE contido em EXPTIME contido em NEXPTIME
