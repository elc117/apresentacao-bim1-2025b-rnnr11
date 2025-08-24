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
Apesar de existirem muitas outras funções relacionadas às listas, elas não são nosso foco aqui. Por enquanto, desejamos 
