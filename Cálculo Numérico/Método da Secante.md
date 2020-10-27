# Método da Secante
## Introdução
Esse método surge como um auxiliar para os casos em que o [[Método de Newton|de Newton]] não ajuda muito. Esses casos são os que a derivada de primeiro grau $f'(x)$ é próxima ou igual a zero no ponto de aproximação.

Para resolver isso, esse método muda a fórmula usada em cada iteração, da reta **tangente** para a reta **secante**, eliminando a derivada do problema.

$$f'(x_k) \approx \frac{f(x_k) - f(x_{k-1})}{x_k - x_{k-1}}$$
$$x_{k+1} = \frac{x_{k-1}f(x_k) - x_{k}f(x_{k-1})}{f(x_k) - f(x_{k-1})}$$

## Algoritmo
- Entramos com o erro e dois valores para $x$, $x_0$ e $x_1$
	- Fazemos $k = 0$
	- Calculamos $f(x_0)$
- Incrementamos $k$ e calculamos $f(x_k)$
- Calculamos $x_{k+1}$ usando a fórmula anterior.
- Calculamos $f(x_{k+1})$
- Se for menor que o erro, paramos. 
	- Senão, voltamos a iterar do ponto 2

Único ponto a se tomar cuidado é quando $f(x_k)$ e $f(x_{k-1})$ forem próximos, pois isso pode dar valores perto de zero para a diferença deles e, como esse é o denominador da fração, estourar o valor para a próxima iteração.