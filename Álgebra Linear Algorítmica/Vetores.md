# Vetores

## Introdução 

- Primeiro veremos tudo para duas dimensões, depois generalizamos
- O que é um vetor?
	- Um segmento de reta orientado composto por
		- Um comprimento chamado *módulo*
		- Uma *direção*, definida pela reta que a gente pode desenhar ele
		- Um *sentido*, ou seja, pra onde essa reta vai
	- Vetores ficam presos a um ponto chamado origem, denotado como O
		- Desenhamos um vetor juntando a origem ao ponto cujas coordenadas dele vão
		- Ponta da seta onde tá a coordenada
	- Notação de módulo de v:  $||v||$

## Operações com vetores

- Soma pode ser feita com o princípio do paralelogramo
	- Você soma as coordenadas respesctivas e BUM nova posição
- Subtração = Soma do vetor negativo 
	- Vetor negativo é o vetor com sentido invertido
- Multiplicação de vetor com número é o vetor somado N vezes a si mesmo
	- Por negativo é o vetor negativo somado N vezes a si mesmo
	- Por zero: origem
- Vetores podem ser retas ou pontos, depende da interpretação
- Sobre vetores e retas
	- Se temos uma reta que passa pelo espaço que a gente tá trabalhando
	- Se temos um vetor que encosta nessa reta, e outro que tem a mesma direção que ela
	- Podemos descrever qualquer vetor que encoste nessa reta 
		- $x = u + \lambda * v$, onde $u$ é o que encosta na reta e $v$ é o na mesma direção
		- Existe sempre um $\lambda$ que satisfaz essa propriedade
		- $v$ é o chamado _vetor diretor_ dessa reta e $u+\lambda v$ é a _equação vetorial_ dela

## Projeção 

- Temos dois vetores u, v e projetamos v em cima de u 
- Criamos outro vetor!
	- Direção: mesma se o ângulo for agudo, oposta se obtuso
	- Norma: $||v|| * \cos{\lambda}$ , onde lambda é o ângulo entre os dois
- Se u for unitário, então o vetor gerado pode ser descrito como $u*(||v|| * \cos{\lambda})$
- Se u não for unitário, transformamos ele em unitário dividindo pela norma de u 
	- Isso ficaria $Proj_u(v) = \frac{u(||v|| * \cos{\lambda})}{||u||}$

## Coordenadas

- Projeções nos permitem pensar em sistemas de coordenadas para vetores
- Fixamos dois vetores _não colineares_ $e1,e2$ para descrevermos os outros vetores
	- Esses vetores $\{e1,e2\}$ são chamados de _base do plano_.
	- Nossa vida é mais simples quando esses vetores são perpendiculares
- Descrevendo vetores nos termos das bases
	- $v = (||v||*\cos{\lambda})*e1 + (||v||*\sin{\lambda})*e2$
	- Se as bases estiverem fixadas, podemos denotar isso de forma mais reduzida: $v = (||v||*\cos{\lambda},||v||*\sin{\lambda})$
	- Chamamos esses dois valores de **coordenadas** do vetor para as bases dele
- Operações dos vetores e coordenadas
	- Vetores que usaremos: $v=(a_1,b_1)$ e $u=(a_2,b_2)$
	- Soma: $v+u=(a_1+a_2,b_1+b_2)$
	- Multiplicação por escalar $\lambda$: $\lambda v=(\lambda a_1,\lambda b_1)$
- Relação entre a equação cartesiana e equação vetorial da reta
	- Equação cartesiana: $y = ax + b$
	- Adaptando isso para um vetor de posição, temos $(x,y)=(x,ax+b)$
	- Manipulando essa equação, temos $(x,y)=x(1,a)+(0,b)$
	- Sendo assim, temos que $x$ é nosso _escalar_ e o vetor diretor é $(1,a)$
- Tem como descobrir a equação cartesiana a partir da equação vetorial, mas achei complicado demais para colocar no resumo

## Produto Interno
- __Produto interno__ ou __Produto escalar__ dos vetores $u,v$ é definido como o número $\langle u|v\rangle =||u||*||v||*\cos{\theta}$
	- $\theta$ é o menor ângulo entre $u$ e $v$ (isso faz com que o produto interno sempre seja nulo ou positivo)
	- Mas como podemos representar esse produto interno em termos de _bases perpendiculares $e_1,e_2$__?
- Definindo algumas coisas
	- Além do ângulo $\theta$, temos também que considerar os ângulos que $u$ e $v$ fazem com a base $e_1$
	- Chamaremos de $\alpha$ e $\beta$ os ângulos que $u$ e $v$ fazem com $e_1$, respectivamente
	- Sendo assim, temos que $\theta=\beta-\alpha$
		- Ou seja: $\cos{\theta}=\cos{\beta-\alpha}=\cos{\beta}\cos{\alpha}+\sin{\beta}\sin{\alpha}$
	- E o produto interno fica $||u||\cdot\cos{\beta}\cdot||v||\cdot\cos{\alpha} + ||u||\cdot\sin{\beta}\cdot||v||\cdot\sin{\alpha}$
	- Se tivermos as coordenadas de $u$ e $v$ sendo $(u_1,u_2)$ e $(v_1,v_2)$, então temos que o produto interno é $\langle u|v \rangle =u_1v_1 + u_2v_2$
- Propriedades do produto interno
	- $\langle u|v_1+v_2 \rangle = \langle u|v_1 \rangle + \langle u|v_2\rangle$
	- $\langle v_1|\lambda v_2\rangle = \lambda\langle v_1| v_2\rangle$
	- $\langle v_1| v_2\rangle = \langle v_2| v_1\rangle$
	- $\langle u|u \rangle \geq 0$
		- Ele só vai ser igual a zero se $u=0$
- Intepretando a equação geral da reta
	- $\alpha x + \beta y + \gamma = 0$, onde $\alpha,\beta,\gamma$ são constantes
	- Considerando $\gamma=0$
		- Vamos considerar que os vetores $n,v$ tem valores respectivos de $(\alpha,\beta)$ e $(x,y)$
		- Sendo assim, o produto interno deles é a equação da reta
		- $v$ pertence à reta com a equação $\alpha x + \beta y$ somente se $\langle n|v \rangle = 0$
		- Ou seja, $v$ só pertence à reta se $v$ for perpendicular à $n$
	- Considerando $\gamma \neq 0$
		- Sabemos que $|\gamma|$ representa o valor do produto interno
			- $\alpha x + \beta y = -\gamma \to \langle v|n \rangle = -\gamma$ 