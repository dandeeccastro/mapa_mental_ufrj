# Velocidade 
### Deslocamento e Tempo
Medindo isso, a diferença entre a **posição** da partícula se chama _deslocamento_, enquanto o **tempo** que demorou para ele chegar lá é o _intervalo de tempo_

$$\Delta x=x_2 - x_1$$
$$\Delta t=t_2 - t_1$$

Vale lembrar que a pessoa pode ter se mexido mas ter tido _zero deslocamento_, quando o ponto final que ela chegou também é o inicial, logo $\Delta x = x_1-x_1=0$

### Velocidade Média
É a razão entre o deslocamento e o tempo que a partícula tomou para realizar algum (ou nenhum) movimento num espaço de tempo.

$$v_m = \frac{\Delta x}{\Delta y} = \frac{x_2 - x_1}{t_2 - t_1}$$

### Velocidade Instantânea
Quando o intervalo de tempo é pequeno o suficiente para gente não ser capaz de medir as mudanças na velocidade da partícula.

Podemos montar a fórmula dessa velocidade instantânea a partir da fórmula da média:

$$v_m = \frac{\Delta x}{\Delta y} = \frac{x_2 - x_1}{t_2 - t_1}$$

Para isso, mudaremos alguns nomes para que certas igualdades possam ser percebidas. Primeiro transformamos em $t_0$ o **tempo inicial** e descrevemos $t_2$ usando ele e o tempo que demorou para completar o movimento, ou seja, $\Delta t$
$$t_1=t_0$$
$$t_2 = \Delta t + t_0$$
Depois disso, tratamos o _deslocamento_ em [[Funções Horárias|função desse tempo]], transformando $x$ em uma função dependente de $t_0$ e $\Delta t$

$$x_1=x(t_0)$$
$$x_2=x(\Delta t + t_0)$$

Assim a fórmula original fica:

$$v(t_0) = \frac{x(t_0 + \Delta t) - x(t_0)}{\Delta t}$$

Se estamos medindo de forma que o tempo seja infinitamente pequeno, devemos fazer um **limite com $\Delta t$ tentendo a zero**! E conferindo as definições, esse procedimento não é nada mais nada menos do que a **derivada da função horária de movimento**

$$\lim_{\Delta t \to 0}{\frac{x(t_0 + \Delta t) - x(t_0)}{\Delta t}} = lim_{\Delta t \to 0}{\frac{\Delta x}{\Delta t}} = \frac{dx}{dt}$$
