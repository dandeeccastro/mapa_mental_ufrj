# Expressões Regulares
Com [[AFD e Linguagens Regulares|Automatos Finitos Determinísticos]], podemos aceitar ou rejeitar palavras de um certo alfabeto $\Sigma$. No entanto, seria um trabalho árduo se tivessemos que testar cada palavra no autômato para poder ver se ela passa ou não.

Para facilitar esse processo, temos Expressões Regulares, que **descrevem** AFDs.

## Como funcionam?
ERs podem ser descritas como uma **palavra do alfabeto** $\tilde{\Sigma}$, que é descrito da seguinte forma:

$$\tilde{\Sigma} = \Sigma \cup \{\cup,\cdot,*,(,),\epsilon,\emptyset\}$$

Esses símbolos possuem as **seguintes regras**:
1. Se $\sigma \in \Sigma$, então $\sigma$ é uma expressão regular
2. $\emptyset$ e $\epsilon$ são expressões regulares
3. Se $r_1$ e $r_2$ são expressões regulares, então $(r_1 \cup r_2)$ e $(r_1 \cdot r_2)$ também são
4. Se $r$ é uma expressão regular, $(r)*$ também é
5. Nada mais é considerado uma expressão regular

Além disso, algumas regras parecidas com álgebra se aplicam, onde temos precedência dos operadores de uma ER. A maior precedência é de $*$, seguido de $\cdot$ e por fim $\cup$

Outra regra é que $\cdot$ pode ser omitido das operações, permitindo que expressões regulares de forma $0\cdot0\cdot1*$ possam ser escritas como $001*$

## ERs e Linguagens
Se temos uma expressão regular $r$, podemos criar uma linguagem $L(r)$, pois expressões regulares em cima de um alfabeto $\Sigma$ representam uma linguagem $L(r) \subseteq \Sigma*$

Linguagens geradas por expressões regulares seguem o seguinte formato:

1. Se $\sigma \in \Sigma$, então $L(\sigma) = \{\sigma\}$
2. $L(\emptyset) = \{\emptyset\}$
3. $L(\epsilon) = \{\epsilon\}$
4. $L(r_1 \cup r_2) = L(r_1) \cup L(r_2)$
5. $L(r_1 \cdot r_2) = L(r_1) \cdot L(r_2)$
6. $L(r*) = L(r)*$

**Observação**: Pode existir duas expressões regulares $r_1$ e $r_2$ tal que $r_1 \neq r_2$ mas $L(r_1) = L(r_2)$