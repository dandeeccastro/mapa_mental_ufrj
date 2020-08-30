# Aritmética de Ponto Flutuante
## Como fica no PC
Quando lidamos com números de ponto flutuante, o computador armazena eles de uma forma bem específica no computador:

$$(.d_1d_2d_3...d_t)*\beta^\epsilon$$

Nesse caso, armazenamos _t_ dígitos na mantissa, definimos qual a base com _beta_ e o _epsilon_ sendo o expoente

Se quiséssemos armazenar o número 301.34, teríamos

$$(.30134)*10^3$$

## Limites
Esse método de armazenamento tem números máximos e mínimos, dado que o tamanho da mantissa depende do sistema que você está usando. 

Por exemplo, se sua máquina trabalha com _t = 7_, _beta = 10_ e _e = 5_ podemos calcular m e M, que são, respectivamente, o mínimo e máximo do sistema

$$M = 0.9999999 *10^5 = 99999.99  $$
$$m = 0.10000000 * 10^{-5} = 10^{-6}$$

Se algum número _x_ quiser ser representado nesse sistema, 3 coisas podem acontecer

- Ele se encontra entre m e M, e é representado de forma correta
	-  No caso de ter mais dígitos que a mantissa permite, pode ser usado truncamento ou arredondamento
- Ele é _menor que m_, o que resulta num _underflow_
- Ele é _maior que M_, o que resulta num _overflow_

## Caveats
O que pode ser feito para resolver esse problema é usar um bom e velho conceito de programação, _double_. Na maioria das linguagens, ele essencialmente determina que **os digitos da mantissa sejam duplicados**!

O único problema dessa abordagem é que ele passa a utilizar dois registradores para armazenar o número (por isso que duplica), logo o processamento demora um pouco mais para acomodar essas mudanças de baixo nível

## Zeros
Zeros nessa representação geralmente são representados com o _menor expoente possível_. Isso se dá para que não percamos precisão em cálculos que envolvam zero.