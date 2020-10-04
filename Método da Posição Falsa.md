# Método da Posição Falsa
## Ideia

O [[Método de Bisseção]] utiliza o ponto do meio para suas aproximações, mas nem sempre ele é o melhor para a ocasião. Esse método leva em consideração que, se temos um $f(a)$ e $f(b)$ para dois pontos $a$ e $b$, temos que fazer uma **média ponderada** entre os valores obtidos com os pontos, para priorizarmos o ponto cuja imagem tenha o **menor módulo**, ou seja, esteja mais próximo de zero.

Se temos dois pontos e suas imagens, podemos definir esse método como análogo ao de bisseção, com a diferença de que o novo ponto agora é calculado da seguinte forma.

$$ x = \frac{af(b) - bf(a)}{f(b)-f(a)}$$

## Execução
Calculamos as imagens dos pontos, depois calculamos o novo $x$ usando o novo cálculo. Se for menor que zero, atualizamos $b$. Se for maior, atualizamos $a$.