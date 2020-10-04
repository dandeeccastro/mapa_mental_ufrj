# Autômatos Finitos Não Determinísticos
Esses autômatos não tem a característica determinística que os [[AFD e Linguagens Regulares]] possuem. Eles compartilham grande partes dos componentes da 5-upla, mas sua **função de transição** possui uma entrada e saída diferentes

Nesse caso temos $\delta ,\sum ,Q, q_0,F$,  que representam os seguintes conceitos:
- $\sum$ é o alfabeto utilizado
- $Q$ é um conjunto finito não-vazio de **estados**
- $q_0$ é o estado inicial do AFD
- $F$ é o conjunto de estados finais do AFD
- $\Delta$ é a função de transição de estados, que pode ser representada da forma abaixo

$$\delta : Q \times \sum \to Q$$