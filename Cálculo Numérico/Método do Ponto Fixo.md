# Método do Ponto Fixo
## Ideia
Certas funções podem ser manipuladas para que, tentando obter $f(x) = 0$, obtenhamos uma expressão na qual $x$ esteja em termos de uma outra função, como no exemplo abaixo.

$$f(x) = x^3 +4x^2 - 2$$
$$0 = x^3 +4x^2 - 2 \to x(x^2 + 4x) = 2 \to x = \frac{2}{x^2 + 4x}$$

Chamaremos a função que descreve $x$ de $g(x)$, ou a **função de iteração**. Se conseguirmos encontrar um valor de $x$ tal que $x = g(x)$, encontramos um $x$ tal que $f(x) = 0$.

Para fazer isso, fazemos uma estimativa e aplicamos ela repetidamente na função, até que ela faça convergência para um ponto.
## Execução
Usamos uma função $g(x)$ e uma estimativa $p_0$. Fazemos $p = g(p_0)$ e $p_0 = p$ até que o módulo da diferença entre $p$ e $p_0$ seja menor que a tolerância estabelecida.