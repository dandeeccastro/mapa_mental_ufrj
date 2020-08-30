# Vetores e Operações
## Vetor
É um _segmento de reta orientado_ geralmente representado por letras como _u,v_ que possui três características descritivas
- **Norma**, o _valor numérico_ que representa a magnitude dele: $||u||$
- **Direção**, ou _onde que a reta está_
- **Sentido**, ou _onde a seta aponta_

Retas não podem simplesmente existir no vazio, então também temos um _ponto_ de onde todos os vetores se originam: a **origem**. Ela é geralmente denotada pela letra O.

Existe um **vetor nulo**, que não tem direção nem sentido, pois a norma dele é zero. Geralmente denotamos ele como 0 (zero)

Existe também um vetor simétrico, que é essencialmente um vetor idêntico ao que temos, mas com sentido oposto. Considerando o vetor $v$, pode ser denotado o simétrico de $v$ como $\bar{v}$ ou $-v$
## Operações
### Adição
Como vetores existem num plano e originam do mesmo ponto, podemos somá-los montando um _paralelogramo_ no plano. Isto é, dado um vetor _v_ e outro vetor _u_, podemos descobrir _v+u_ se:
1. Colocarmos a ponta de _u_ no final de _v_
2. Colocarmos a ponta de _v_ no final de _u_
	- Nessa altura montamos um paralelogramo
3. Conectamos à origem o ponto apontado pelas duas novas retas
4. Esse é o vetor _v + u_ 

#### Propriedades
- **Comutativa**
	- Podemos chegar no ponto final do vetor _u + v_ tanto botando _u_ no final de _v_ como botando _v_ no final de _u_
	- Logo a ordem não importa: $u + v = v + u$
- **Associativa**
	- Não importa como a soma seja feita, o resultado será o mesmo
	- Logo $(u + v) + w = u + (v + w)$
- **Elemento Neutro**
	- $u + 0 = u$
- **Vetor Simétrico**
	- $u + \bar{u} = 0$

### Multiplicação por Escalar
É quando multiplicamos um vetor $v$ por algum número $\lambda$. Isso essencialmente significa que estamos adicionando $v$ em $v$ $\lambda$ vezes.

$$\lambda v = v + v + v + \dots + v$$

Visualmente falando, o vetor resultante tem a mesma direção que o original, mas a norma altera e o sentido _pode alterar se multiplicarmos por um $\lambda$ negativo_.
#### Propriedades
Tendo como exemplo o vetor $v$ e os escalares $\lambda$ e $\omega$, a multiplicação por escalares tem as seguintes propriedades:
- $0 * v = 0$
	- Aqui vale lembrar que o zero multiplicado é o **número** e o zero resultado é o **vetor nulo**
- $1*v = v$
- $-1*v = \bar{v}$
	- Tanto que $v + \bar{v} = 0$
- $(\lambda + \omega)*v = \lambda*v + \omega*v$
- $\lambda*(u + v) = \lambda*u + \lambda*v$
- $\omega*(\lambda*v) = \lambda*(\omega*v)$

Muitas dessas propriedades são matemática básica: a multiplicação da soma de dois números é a soma da multiplicação desses números e coisa do tipo.