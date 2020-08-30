# Arredondamento e Truncamento
## Introdução
Números possuem  o que chamamos de **algarismos significativos**, que são os dígitos que importam para definir seu valor. Por exemplo, se temos $0.0001231$, $1231$ seriam os dígitos significativos do número.

Os erros surgem quando nós nos vemos forçados a sacrificar esses algarismos por limitações no [[Aritmética de Ponto Flutuante| jeito como armazenamos os números]]. Para que possamos reduzir os erros nessa eliminação, temos dois jeitos de reduzir esses algarismos: **arredondamento** ou **truncamento**.
## Arredondamento
Fazemos uma avaliação numérica dos algarismos que não podem ser representados e, dependendo do resultado, mudamos o valor _para cima ou para baixo_.

- Exemplo

$$0.0001322131 \to 0.2131 \leq 0.5 \to 0.000132$$
$$0.053678 \to 0.678 \geq 0.5 \to 0.054$$

## Truncamento
Nesse método nós simplesmente _ignoramos_ os dígitos que não podem ser representados, independente de serem maiores ou menores que $0.5$.
- Exemplo

$$0.0001322131 \to 0.000132$$
$$0.053678 \to 0.053$$