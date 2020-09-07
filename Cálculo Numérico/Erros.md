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

