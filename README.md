# As Tuplas
Diferentes linguagens e campos do conhecimento podem ter definições diferentes de tuplas, mas, no fim, uma tupla pode ser resumida grossamente a um aglomerado de dados que foi aglutinado em um único conjunto. Em bancos de dados, por exemplo, uma tupla é uma linha em uma tabela de banco de dados que corresponde a um registro ou entidade, enquanto, em Python, ela é um objeto usado para armazenar informações imutáveis. No entanto, faz pouco sentido para nós entender todas essas definições, então basta que entendamos toda a amplitude de definições com diferenças sutis entre si que existem por aí.

**Então?**
Para nós, tuplas são estruturas de dados que guardam grupos de informações. Simples, não é?

## Listas X Tuplas
Tanto em Haskell quanto em Python — serão nossos dois principais materiais de estudo —, tuplas e listas possuem muitas semelhanças. No entanto, uma característica da tupla as torna muito diferentes na prática. 
Dentro de uma lista, em Python, por exemplo, podemos ler elementos, inserir ou excluir novos e até modificá-los. Por exemplo:
```
umaLista.insert(indice, elemento) -> insere um elemento à lista "umaLista" no indice escolhido.

umaLista.remove(elemento) -> remove um elemento da lista, retornando erro caso o elemento não exista.
```
Apesar de existirem muitas outras funções relacionadas às listas, elas não são nosso foco aqui. Por enquanto, desejamos apenas entender que toda a versatilidade das listas que já conhecemos não fazem sentido para as tuplas. Dentro do Python, o detalhe que altera a função de uma estrutura para outra é a **mutabilidade**. Ou melhor, a falta dela.

### Imutabilidade
A única forma de inserir elementos dentro de uma tupla é no momento de sua declaração. Uma tupla existe para ser lida, não para ter seus dados manipulados, e isso altera completamente a mecânica de seu uso. Além disso, por ser uma estrutura estática, não dinâmica, a tupla é recomendada pra uso heterogêneo de dados, ou seja, inserir tipos diferentes dentro da mesma estrutura. Essa imutabilidade é diferente para o Haskell, mas abordaremos mais a frente.
Seguem abaixo alguns exemplos de tuplas:
```
(True, 123, "123")
('1', '2', '3', 321)
(Falso, Falso, "Falso")
Obs: Repare na diferença de dados sendo inseridos dentro do mesmo conjunto. Em Haskell, isso é crucial.
```
## Uso de Tuplas em Python
Em Python, a declaração de tuplas pode ser feita através da inserção dos elementos livremente ou entre parenteses. Segue o exemplo abaixo:
```
>>> t = 12345, 54321, 'hello!' # também funciona -> t = (12345, 54321, 'hello!')
>>> t[0]
12345
>>> t
(12345, 54321, 'hello!')
```
Como dito antes, tuplas são imutáveis, então tentar alterá-la retornará um erro.
```
>>> t[0] = 88888
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```
## Uso de Tuplas em Haskell
No entanto, a mecânica das tuplas em Haskell é diferente do Python. Aqui, as listas também são imutáveis, e a alteração de seus dados exige a criação de uma nova lista. Nesse caso, a função das tuplas muda um pouco.

### Estrutura Heterogênea
Diferente do Python, em que é **recomendável** que listas tenham o mesmo tipo de dados, no Haskell, isso é uma exigência. Como listas são homogeneas na linguagem, a principal utilidade de uma tupla é a estruturação heterogênea de dados, ou seja, unir dados com tipos diferentes sem a necessidade de criar novas estruturas (structs).
