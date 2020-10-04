# Erros
Acontecem quando temos um número que não pode ser representado no sistema que estamos trabalhando. Nesse caso possuímos um erro na representação do número.

Analisar esses casos envolve descobrir a relação entre o número absoluto $x$ e sua representação numérica imprecisa $\bar{x}$.

## Erro Absoluto
O **Erro Absoluto** é a _diferença_ entre o valor real do número e sua representação imprecisa. Logo, podemos descrevê-lo da seguinte forma:
$$EA_x = x - \bar{x}$$
Como descrito anteriormente, não é sempre que temos ciência do valor de $x$, o que nos impede de obter o valor real do erro absoluto. Por isso, resolvemos esses tipos de problemas com estimativas e limites superiores e inferiores.

No caso de $\pi$, sabemos que ele está entre $3.14$ e $3.15$ ($\pi \in (3.14,3.15)$), logo sabemos que $|EA_x| = |\pi - \bar{\pi}| < 0.01$.

## Erro Relativo
É definido pelo erro absoluto _dividido_ pelo valor aproximado. É utilizado para casos em que o erro absoluto não representa bem a precisão dos valores, devido à diferenças na _ordem de grandeza_ do número sendo analizado.

$$|ER_x| = \frac{|x - \bar{x}|}{|\bar{x}|} = \frac{|EA_x|}{|\bar{x}|}$$

## Desvio Relativo
A perda de precisão nos cálculos usando ponto flutuante acontece por causa dos erros, e eles surgem por dois motivos que podem ser encontrados na fórmula abaixo:

$$x + y \approx x \oplus y = fl(\tilde{x} + \tilde{y})$$

Nesse caso:
- $\tilde{x} + \tilde{y} = (x + y)(1 - \delta^{dados}_{x+y})$, onde temos uma **soma com dados errados**!
- $fl(\tilde{x} + \tilde{y}) = (\tilde{x} + \tilde{y})(1 - \delta^{arred}_{\tilde{x} + \tilde{y}})$ onde temos um **arredondamento da soma**.

Juntando as duas expressões e _generalizando para qualquer operação_ podemos definir o **desvio relativo** acumulado:

$$\delta^{acum}_{op} = \delta_{op}^{dados} + \delta_{op}^{arred} - \delta_{op}^{dados}\delta_{op}^{arred}$$

**Desenvolvendo** essa equação, encontramos um dado interessante:

$$|e_{op}^{dados} - e_{op}^{arred}| \leq e_{op}^{acum} \leq e_{op}^{dados} + e_{op}^{arred}$$

Isso nos diz que o erro de precisão com **dados** é o que define se o erro acumulado será grande ou não. Sendo assim, **quanto mais operações com dados errados, maior o limite do erro acumulado**!

Assim podemos ter casos de **cancelamento catastrófico**, onde o erro se propaga de uma forma exponencial. Esses casos geralmente podem ser mitigados.