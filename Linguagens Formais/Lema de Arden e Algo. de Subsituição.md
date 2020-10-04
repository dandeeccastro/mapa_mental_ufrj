# Lema de Arden e Algo. de Subsituição
Temos [[AFD e Linguagens Regulares|AFDs e Linguagens Regulares]], e temos [[Expressões Regulares]]. Sabemos que ERs representam linguagens de um certo alfabeto $\Sigma$. Sendo assim, como podemos usar ERs para descrever AFDs?

## Destrinchando o funcionamento da LR
Podemos analisar o funcionamento de uma linguagem regular olhando para ela quando ela se encontra em um estado diferente, ou seja, quando temos algum símbolo em $Q$ que esteja sendo processado.

Para fazer isso, ajuda termos a visualização de tabelas ou grafo da linguagem a ser analisada, então segue abaixo um exemplo:

| $\delta$ | $0$ | $1$ | 
|---|---|---|
|$q_1$|$q_2$|$q_2$|
|$q_2$|$q_1$|$q_1$|

Dessa forma podemos montar uma pequena expressão regular para cada estado diferente da máquina:

- $L_1 = 0L_2 \cup 1L_2 = (0 \cup 1)L_2$
- $L_2 = 0L_1 \cup 1L_1 \cup \{\epsilon\} = (0 \cup 1)L_1 \cup \{\epsilon\}$

## Algoritmo de Substituição
O plano a partir daqui é simples: substituímos as linguagens da lista até que tenhamos uma expressão só. Podemos obter expressões únicas de cada item, mas vale lembrar que a **linguagem baseada no símbolo inicial é a que representa a linguagem regular da expressão**

$L_1 = (0 \cup 1)L_2$
$L_1 = (0 \cup 1)((0 \cup 1)L_1 \cup \{\epsilon\})$
$L_1 = (0 \cup 1)^2L_1 \cup (0 \cup 1)$

Aqui você encontra o maior problema desse algoritmo: recursividade. 

## Lema de Arden
Esses tipos de modelos recursivos foram estudados e uma generalização do problema foi encontrada: a resolução da equação abaixo.

$$X = AX \cup B$$

Nesses casos podemos reparar um padrão quando tentamos substituir $X$ em $X$ algumas vezes

$$ X = A(AX \cup B) \cup B = A^2X \cup (A \cup \epsilon)B$$
$$A^2(AX \cup B) \cup (AB \cup B)$$