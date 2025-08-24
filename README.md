# As Tuplas
Diferentes linguagens e campos do conhecimento podem ter definições diferentes de tuplas, mas, no fim, uma tupla pode ser resumida grossamente a um aglomerado de dados que foi aglutinado em um único conjunto. Em bancos de dados, por exemplo, uma tupla é uma linha em uma tabela de banco de dados que corresponde a um registro ou entidade, enquanto, em Python, ela é um objeto usado para armazenar informações imutáveis. No entanto, faz pouco sentido para nós entender todas essas definições, então basta que entendamos toda a amplitude de definições com diferenças sutis entre si que existem por aí.

**Então?**
Para nós, tuplas são estruturas de dados que guardam informações. Simples, não é?

## Listas X Tuplas
Tanto em Haskell quanto em Python — serão nossos dois principais materiais de estudo —, tuplas e listas possuem muitas semelhanças. No entanto, uma única diferença as torna muito diferentes na prática. 
Dentro de uma lista, em Python, por exemplo, podemos ler elementos, inserir ou excluir novos e até modificá-los. Por exemplo:
```
umaLista.insert(indice, elemento) -> insere um elemento à lista "umaLista" no indice escolhido.

umaLista.remove(elemento) -> remove um elemento da lista, retornando erro caso o elemento não exista.
```
Apesar de existirem muitas outras funções relacionadas às listas, elas não são nosso foco aqui. Por enquanto, desejamos apenas entender que toda a versatilidade das listas que já conhecemos não fazem sentido para as tuplas. O detalhe que altera a função de uma estrutura para outra é a **mutabilidade**. Ou melhor, a falta dela.

### Imutabilidade
A única forma de inserir elementos dentro de uma tupla é no momento de sua declaração. Uma tupla existe para ser lida, não para ter seus dados manipulados, e isso altera completamente a mecânica de seu uso. Além disso, por ser uma estrutura estática, não dinâmica, a tupla é recomendada pra uso heterogêneo de dados, ou seja, inserir tipos diferentes dentro da mesma estrutura.
Seguem abaixo alguns exemplos de tuplas:
```
(True, 123, "123")
('1', '2', '3', 321)
(Falso, Falso, "Falso")
Obs: Repare na diferença de dados sendo inseridos dentro do mesmo conjunto. Em Haskell, isso é crucial.
```
## Uso de Tuplas
