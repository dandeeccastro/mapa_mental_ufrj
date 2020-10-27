# Método de Newton
A ideia por trás é resolver um problema mais simples do que o polinômio $f(x)$. O caminho mais simples para se fazer isso é com uma reta, e encontrar o zero dela.
## Obtendo a reta
- Escolhemos um $x_0$, um chute educado. 
- Calculamos $f(x_0)$ e $f'(x_0)$
- Com isso geramos a reta tangente a $f(x)$ no ponto $x_0$:
	- $r_0(x) = f(x_0) + f'(x_0)(x - x_0)$
- Por fim podemos calcular o zero de $r_0$

## Iteração e Algoritmo
Não é possível derivar em um computador, então temos que manipular a equação da reta em zero ($r_0 = 0$) para poder obter algo iterável. Fazendo isso obtemos a equação abaixo
$$x_1 = x_0 - \frac{f(x_0)}{f'(x_0)}$$
Podemos iterar em cima disso, fazendo uma série de chutes ou estimativas $x_k$
$$x_k = x_{k-1} - \frac{f(x_{k-1})}{f'(x_{k-1})}$$
 Repetimos o processo até que o resultado encontrado seja menor que o erro que propomos
 
 ## Por que funciona?
 
Se pararmos para analisar, o modelo da função de Newton é um [[Método do Ponto Fixo|método de posição fixa]], já que podemos definir a função $g(x)$ como sendo 
$$g(x) = x - \frac{f(x)}{f'(x)}$$
Sendo assim, cada iterando do método de Newton é gerado como o próximo $x$ de uma iteração de ponto fixo da função descrita acima.