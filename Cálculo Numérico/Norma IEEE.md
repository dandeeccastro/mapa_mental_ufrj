# Norma IEEE
## Introdução
Números binários, assim como decimais, podem ser representados com um polinômio em termos de sua base, como demonstrado abaixo:
$$d_1*2^n + d_2*2^{n-1}\dots d_n *2^0$$
Mas também devemos levar em conta os números de ponto flutuante, ou os números que pertencem ao domínio dos reais. Nesses casos, a representação fica dessa forma:
$$x = (-1)^s*(d_0d_{-1}d_{-2}\dots d_n)*2^e$$
Nesses casos, um bit é reservado para o sinal do número ($s$) e temos uma divisão do resto dos bits em dois itens, a **mantissa** e o **expoente**, para que possamos fazer com que eles sejam frações muito pequenas assim como números grandes.
### Nota: Normalização
- Quando o primeiro dígito $d_0$ é igual a zero, a representação do número **não está normalizada!**
- Não existe representação normalizada de $x=0$
## Norma IEEE 754
Introduzida em 1985 e atualizada pela última vez em 2008, essa norma visa padronizar as seguintes coisas:
- Representação de números reais no computador
- Formas de aproximação de números reais no computador
- Formato de representação de números de ponto flutuante que devem ser usados
- Operações aritméticas de números de ponto flutuante
- Tratamento de exceções de números de ponto flutuante

### Representações
Se temos os números $p$, $E_{min}$ e $E_{max}$ tais que $p \geq 1$, $E_{min} < E_{max}$, podemos definir um sistema de ponto flutuante com precisão $p$ e limites $E_{min}$ e $E_{max}$ como sendo um subconjunto $F$ de números reais da seguinte forma

$$F = \{\pm(d_0,d_1\dots d_{p-1})_2 \times 2^e | d_0 = 1, e \in [E_{min},E_{max}]\} \cup \{ 0 \} $$

Sobre esse sistema de representação, podem ser feitas algumas observações:
- Dois números de $F$ só podem ser iguais se suas representações são iguais
- $F$ possui $2^p(E_{max} - E_{min} + 1) +1$ números
- Números de menor módulo: $x_{min} = 2^{E_{min}}$
- Números de maior módulo: $x_{max} = (2^p-1)2^{E_{max} +1 - p}$

### Aproximação de Números Reais
Temos uma função $fl$ que aproxima os números reais para $F$, de forma que se $x \in F$ então $fl(x) = x$. O computador entende $x$ como $fl(x)$.

### Aritmética de Ponto Flutuante
Quando introduzimos no conjunto $F$ as operações aritméticas, construimos um sistema de aritmética elementar dentro dele, da seguinte forma:
- $x \oplus y = fl(x + y)$
- $x \ominus y = fl(x - y)$
- $x \odot y = fl(x \cdot y)$
- $x \oslash y = fl(x/y)$

**Importante**: Pode ser que o resultado da operação em $F$ seja diferente do resultado da operação nos números reais devido à aproximação. Isso acontece porque, por mais que $x \in F, y \in F$, não podemos garantir que $x \otimes y$ para a operação $\times \in \{+.-,\cdot,/\}.$

### 32 vs 64 bits
Temos dois formatos básicos de números de ponto flutuante segundo a norma IEEE:

| |Precisão Simples|Precisão Dupla|
|---|---|---|
|$p$|24|53|
|$E_{min}$|-126|-1022|
|$E_{max}$|127|1023|
|Bits|32|64|

Existem [[Arredondamento e Truncamento|dois jeitos principais]] de determinar aproximações de $fl(x)$. As aproximações na norma IEEE são feitas via [[Arredondamento e Truncamento#Arredondamento|arredondamento]].

### Erros na Aprox. de ponto flutuante
A norma prefere o arredondamento ao truncamento porque o resultado do erro é menor.

Seja $E$ o erro absoluto e $e$ o erro relativo, podemos definir o erro obtido com arredondamento e truncamento da seguinte forma:

#### Truncamento
$$E_x = |x - x_{trunc}| \leq 2^{e-p}$$
$$e_x = |\frac{x - x_{trunc}}{x}| \leq e_{maq} = 2^{-p+1}$$
#### Arredondamento
$$E_x = |x - x{arred}| \leq 2^{e-p-1}$$
$$e_x = |\frac{x - x_{arred}}{x}| \leq \frac{e_{maq}}{2} = 2^{-p}$$

Os valores obtidos nessas duas análises demonstram que o arredondamento possui limites menores e, por consequência, **mais precisos** que o truncamento.

Os valores para $e_{maq}$ segundo a norma são 
- $2^{-23} \approx 1.19 \cdot 10^{-7}$ (simples)
- $2^{-52} \approx 2.22 \cdot 10^{-16}$ (dupla)