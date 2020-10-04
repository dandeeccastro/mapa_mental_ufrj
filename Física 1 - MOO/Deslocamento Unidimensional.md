# Deslocamento Unidimensional
## Velocidade Média e Instantânea
Para descrever o movimento de uma partícula que se movimenta numa linha reta, podemos medir a distância que ela percorre com a **diferença de posição dela** e o **tempo do deslocamento**. 

Para isso medimos tanto $t_0, t_1$ como tempos iniciais e finais, assim como $x_0,x_1$ como posições finais e iniciais, podendo obter a _velocidade média_ do deslocamento entre eles.

$$v_{mx} = \frac{\Delta x}{\Delta t} = \frac{x_1 - x_0}{t_1 - t_0}$$

Se queremos obter a velocidade no exato momento $t$, temos que transformar o intervalo de tempo _infinitamente pequeno_, para que o tempo relevante seja somente $t_0$. Para isso fazemos a **derivada da velocidade média**:

$$v_x = \lim_{\Delta t \to 0}{ \frac{\Delta x}{\Delta t} } = \frac{dx}{dt}$$

## Aceleração Média e Instantânea

A aceleração mede a transformação da velocidade entre um espaço de tempo, e, analogamente à velocidade, pode ser descrita como a média da medição da velocidade em dois instantes de tempo diferentes:

$$a_{mx} = \frac{\Delta v}{\Delta t} = \frac{v_1 - v_0}{t_1 - t_0}$$

Do mesmo jeito, se queremos obter a aceleração num momento exato, podemos derivar a aceleração média num instante específico de tempo, para obter isso:

$$a = \lim_{\Delta t \to 0}{ \frac{\Delta v}{\Delta t} } = \frac{dv_x}{dt}$$

## Movimento Retilíneo com Aceleração Constante
Essas equações são válidas somente quando medimos um movimento de aceleração constante em $t_0 = 0$. No caso das variáveis com números embaixo das letras, elas representam velocidades ou acelerações instantâneas!

Essa fórmula se obtém se destrincharmos a de aceleração instantânea:
$$v_1 = v_0 +a_{x}*t$$

Trabalhando com a de velocidade média, obtemos uma igualdade interessante. Como a aceleração é constante, se temos as velocidades instantâneas $v_1$ e $v_0$, podemos dizer que a velocidade média é a média entre essas velocidades instantâneas. Em termos matemáticos, temos essas duas igualdades para $v_{mx}$:
$$v_{mx} = \frac{\Delta{x}}{\Delta{t}}$$
$$v_{mx} = \frac{v_1 - v_0}{2}$$

Manipulando elas matematicamente, temos que:
$$\frac{x_1 - x_0}{t_1 - t_0} = \frac{v_1 - v_0}{2}$$
$$\frac{x_1 - x_0}{t} = \frac{2v_0 + a_{x}t}{2}$$
$$x_1 = x_0 + v_0t + \frac{at^2}{2}$$

Quando a velocidade é constante, temos aceleração nula, logo:

$$x_1 = x_0 + v_{0}*t$$

Para esse aqui, primeiro botamos o tempo em evidência usando a fórmula de aceleração, para depois substituir ela na outra fórmula de posição:
$$t = \frac{v_1 - v_0}{a_x}$$
$$x_1 = x_0 + v_0(\frac{v_1 - v_0}{a_x}) + \frac{a(\frac{v_1 - v_0}{a_x})^2}{2}$$

Simplificando esse termo, temos como resultado final:

$$v_1^2 = v_0^2 + 2a\Delta x$$

Por fim, se multiplicarmos por $t$ a função igualada de $v_{mx}$ anterior, conseguimos a última fórmula:

$$t(\frac{x_1 - x_0}{t}) = t(\frac{2v_0 + a_{x}t}{2})t$$
$$x - x_0 = \frac{1}{2}*(v_0 + v)*t$$

## Movimento Retilíneo com Aceleração Variada
Podemos descobrir a velocidade e o tempo de uma função com aceleração variada integrando ela em termos do tempo

Isso na prática significa que a área do gráfico da função de aceleração por tempo é a variação da velocidade. Reutilizando esse conceito para o gráfico da velocidade, temos que a área dele é o deslocamento
$$x = x_0 + \int_0^tv_x$$
$$v = v_0 + \int_0^ta_x$$