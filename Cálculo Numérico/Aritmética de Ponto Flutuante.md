# Aritmética de Ponto Flutuante
## Como fica no PC
O padrão utilizado para armazenar números em um computador foi criado pela IEEE, com sua última revisão em 2008. Nessa representação, temos 3 componentes: 
- $s$ é o bit reservado para o sinal do número (positivo ou negativo)
- $c$ é chamado de **característica**, e representa o expoente da base
- $m$ é chamado de **mantissa**, e representa o número em versão fracionária

Se estamos lidando com um computador de 64 bits, por exemplo, segundo a IEEE, temos 1 bit de sinal, 11 bits na característica e 52 bits na mantissa. Convertendo para decimais, temos aproximadamente:
- $0 \leq c \leq 2^{11} - 1 => 0 \leq c \leq 2047$, caso $c$ não possua sinal.
- $-1023 \leq c \leq 1024$ para números com sinais

Normalizar o número faz mais sentido, para garantir representação única entre eles e otimizar armazenamento, então a fórmula final para a representação é

$$(-1)^s*2^{c-1023}*(1+m)$$

Para os propósitos desse estudo, vale considerarmos a **característica** e **mantissa** como independentes da base binária, e, consequentemente, da [[Conversão Decimal - Binária|conversão para decimal]]. E também, não é todo sistema que é alinhado com a IEEE.

Dessa forma, podemos interpretar números decimais da seguinte forma:
$$(-1)^s*10^c*(1+m)$$
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