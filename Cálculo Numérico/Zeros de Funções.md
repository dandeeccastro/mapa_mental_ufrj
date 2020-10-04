# Zeros de Funções
Em Cálculo Numérico, um dos ganhos que temos fazendo aproximação é quando queremos descobrir zeros de polinômios grandes. Quando eles são de segundo grau, podemos resolver facil e manualmente por meio de fórmulas mais conhecidas, mas conforme vamos avançando isso se torna mais inviável.

Sendo assim, temos que usar de análises e aproximações para poder chegarmos ao nosso resultado. Os passos a se tomar são os seguintes:
1. Isolamento dos Zeros
2. Refinamento dos Resultados

## Isolamento dos Zeros
### A Regra dos Sinais
Uma função polinomial tem zeros, mas são difíceis de achar. Podemos usar uma regra para dizer quando tem ou não um zero em um intervalo entre dois pontos.

Sejam $a$ e $b$ dois valores de $x$ e $f$ a função polinomial que queremos analisar. Uma regra básica nos diz que se **o sinal de $f(a)$ e de $f(b)$ forem diferentes, é porque tem pelo menos um zero entre eles**! Isso se dá porque, lógicamente, você tem que cruzar o eixo $x$ para mudar o sinal de $f(x)$.

Se os sinais forem iguais, pode ou não significar zeros entre eles, é inconclusivo.

### Igualando funções
Se temos uma função $f(x) = 0$, pode ser bom dividirmos ela em duas outras $g(x)$  e $h(x)$ de forma que obtenhamos $g(x) = h(x)$. 

Se traçarmos o gráfico das duas funções, vamos encontrar pontos onde esses dois gráficos se cruzam. Achando eles, podemos possivelmente encontrar nossos zeros, já que se temos $\sigma$ tal que $f(\sigma) = 0$, também temos $g(\sigma) = h(\sigma)$