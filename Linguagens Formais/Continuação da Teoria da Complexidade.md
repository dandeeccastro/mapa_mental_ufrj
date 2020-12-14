# Continuação da Teoria da Complexidade

## Co-Classes

- Se C é uma classe de complexidade, a classe co-C é um complemento da classe C
	- É a classe de todas as linguagens cujos complementos pertencem a C
	- L pertence à co-C se e somente se o complemento de L pertence à C
- Se L é decidida por uma MT det., então invertendo o Sim e Não dela nos gera uma máquina que decide o complemento de L 
- Pra todas as classes definidas a partir de MT det., temos que co-C = C
	- P = co-P
	- PSPACE = co-PSPACE
	- EXPTIME = co-EXPTIME

- Pelo Teorema de Savitch, temos que PSPACE = NPSPACE
- Logo co-PSPACE = co-NPSPACE, e assim co-NPSPACE = PSPACE
- Questões ainda em aberto sobre esses rolês
	- co-NP é igual ou diferente de NP?
	- co-NEXPTIME é igual ou diferente de co-NEXPTIME?
- Como inserir co-NP e co-NEXPTIME no sisteminha?

- Lema: se C1 e C2 são classes de complexidade e C1 é contido em C2, então co-C1 está contido em co-C2
	- Se L pertence à co-C1, então o complemento dela pertence à C1
	- Como C1 está contido em C2, o complemento pertence à C2, logo L pertence à co-C2
- Com raciocínios análogos, podemos dizer que 
	- co-P tá contido em co-NP 
	- co-EXPTIME tá contido em co-NEXPTIME
	- co-NP tá contiod em co-PSPACE

## Redução Polinomial entre Linguagens

- 
