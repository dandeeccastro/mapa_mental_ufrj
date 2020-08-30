# Conversão Decimal - Binária
## Da base 2 para a base 10
Quando temos um número como 214 na base 10 ou 101011 na base 2, eles podem ser traduzidos para um formato polinomial

`214 = 2 x 10 ^ 2 + 1 x 10 ^ 1 + 4 x 10 ^ 0`
`101011 = 1 x 2 ^ 5 + 0 x 2 ^ 4 + 1 x 2 ^ 3 + 0 x 2 ^ 2 + 1 x 2 ^ 1 + 1 x 2 ^ 0`

Essa interpretação por si só nos trás o jeito de converter números binários para a base decimal:

1. Monte o polinômio
	- Valor decimal = Dígito x Base ^ Posição - 1
2. Resolva o polinômio

### Exemplo
`101011 = 1 x 2 ^ 5 + 0 x 2 ^ 4 + 1 x 2 ^ 3 + 0 x 2 ^ 2 + 1 x 2 ^ 1 + 1 x 2 ^ 0`
`101011 = 32 + 8 + 2 + 1`
`101011 = 43`

## Da base 10 para a base 2
Quando temos um número decimal que queremos transformar em outra base, temos que procurar _descrever o número baseado nessa base_. 

Para fazermos isso, temos que voltar a analisar a interpretação polinomial. Se temos que multiplicar um número de base diferente para chegar na base dez, a recíproca é verdadeira: _temos que dividir pela nova base para conseguir nosso número_

O algoritmo é simples:

1. Dividimos o número pela base e conseguimos o dividendo e o resto
2. O resto é o dígito do novo número
3. O dividendo é o número que será dividido na próxima iteração
4. Terminamos isso até que não sobre nada do número além do resto

No final temos uma série de dígitos que representam o _número invertido_. Ele está ao contrário porque estamos desconstruindo ele, começando da potência mais alta até a mais baixa.

### Exemplo

`341 = 2 x dividendo + resto`
`341 = 2 x 170 + 1`
`170 = 2 x 85 + 0`
`85 = 2 x 42 + 1`
`42 = 2 x 21 + 0`
`21 = 2 x 10 + 1`
`10 = 2 x 5 + 0`
`5 = 2 x 2 + 1`
`2 = 2 x 1 + 0`
`1 = 2 x 0 + 1`
`Resultado: 341 = 101010101`

Podemos provar que é o caso fazendo o processo reverso
`101010101 = 256 + 64 + 16 + 4 + 1 = 341`

## Mas e quando é um número fracionário?
Antes de mais nada, note que a interpretação polinomial continua sendo válida para números fracionários, só que agora **as potências da base são negativas**! Mesmo assim, a máxima de manipular o número usando somente a base que queremos chegar continua sendo verdadeira.

### De decimal para binário
Quando temos um número como 0.354, nada adianta dividir ele por 2, pois estamos lidando com bases negativas. O número já está sendo representado com divisões de 10, se quisermos mudar isso, temos que convertê-lo **multiplicando por 2**

O algoritmo é o seguinte:
1. Multiplico o número atual por dois
2. A parte inteira dele é o dígito daquela potência
3. O resto vira o novo número
4. Repetir até que o resto fique zero ou se econtre uma dízima

#### Exemplo
`0.354 => 0.708 => 1.416 => 0.832 => 1.664 => 1.328 => 0.656 => 1.312 => 0.624...`

Isso vai continuar por muito tempo. Fazendo um script rápido em python, consegui encontrar um valor final para esse número

`0.010101110100101111000110101001111110111110011101101101`

Importante notar que esse número possui _56 dígitos_, o que significa que se estivéssemos numa máquina de 32 bits, não conseguiríamos representá-lo de forma completa. Até mesmo numa máquina de 64 bits você pode acabar tendo menos de 56 dígitos na [[Aritmética de Ponto Flutuante | mantissa]]. **Por isso que erros de aproximação existem**.

### De binário para decimal
Assim como o anterior, multiplicaremos nosso número desejado por dez, retiraremos a parte inteira e ela será nosso dígito. O pequeno porém dessa operação é que ela tem que ser feita com dez em binário, ou seja, 1010.

O algoritmo é o seguinte:
1. Multiplicamos o número por 1010
2. A parte inteira é convertida para decimal e é o valor no dígito
3. A parte que sobrar se torna o novo número
4. Repetir até que tenhamos zero no resto ou dízima

#### Exemplo
 
 `0.000111 => 1.00011 -> 1 => 0.1111 -> 0 => 1001.011 -> 9 => 11.11 -> 3 => 111.1 -> 7 => 101 -> 5`
 `0.109375`