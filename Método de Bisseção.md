# Método de Bisseção
## Ideia
Sabemos que para ter um zero na função, temos que ter dois pontos $a$ e $b$ tal que os sinais de $f(a)$ e de $f(b)$ sejam diferentes. Isso nos mostra que, para ele ir de cima para baixo no gráfico, ele tem que ter passado no zero.

## Execução
Pegamos $a$ e $b$, e com eles encontramos o ponto do meio $p$. Encontramos $f(p)$, e analisamos o sinal dele. Se for maior que zero, fazemos $a = p$, se não, $b = p$. Repetimos até que o resultado seja zero ou menor que a tolerância estabelecida no problema.