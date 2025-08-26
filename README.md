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
A única forma de inserir elementos dentro de uma tupla é no momento de sua declaração. Uma tupla existe para ser lida, não para ter seus dados manipulados, e isso altera completamente a mecânica de seu uso. Além disso, por ser uma estrutura estática, não dinâmica, a tupla é recomendada pra uso heterogêneo de dados, ou seja, inserir tipos diferentes dentro da mesma estrutura. Essa imutabilidade é diferente para o Haskell, mas abordaremos mais a frente. Além disso, também devemos lembrar que, para termos uma tupla, não podemos ter menos de dois dados no conjunto, diferente das listas que até vazias podem existir.
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

### Sintaxe da Tupla
As tuplas são declaradas em Haskell entre parenteses, sendo que todos os seus elementos são separados internamente por vírgulas.
```
ghci> umaTupla = (10, 20, "30", '4', '0') -- isso é uma tupla sendo declarada
```
Apesar de tudo, acessar tuplas não é nada prático, exceto quando falamos de seus primeiros e segundos elementos. Haskell já tem as funções fst e snd que utilizamos para acessar o primeiro e o segundo elemento. Por exemplo:
```
ghci> pair = (1, 2)
ghci> pair
(1, 2)
ghci> fst pair
1
ghci> snd pair
2
```
No entanto, caso desejemos acessar elementos do terceiro em diante, é necessário que criemos nossas próprias funções para fazer a leitura. Além disso, também é válido lembrar que tuplas podem ser inseridas uma dentro da outra, assim como dentro de listas.
```
ghci> tup = (("aqui", "dentro",), "aqui fora")
ghci> lst = [(1, 2), (3, 4), (5, 6)]
```
Por fim, temos a função curry e uncurry. Essa função transforma uma função em uma que seja "curried", ou seja, muda uma função que receba como parâmetro uma tupla para uma que recebe dois elementos. Por exemplo:
```
ghci> curry fst "aqui" "dentro" -- fst recebe uma tupla como parâmetro, então essa construção com seus elementos separados não deveria ser possível
"aqui"
ghci> funcao x y = x+y
ghci> funcao 1 2
3
ghci> uncurry funcao (1, 2) -- funcao é uma função "curried", então não deveria funcionar com uma tupla.
3
```

### Estrutura Heterogênea
Diferente do Python, em que é **recomendável** que listas tenham o mesmo tipo de dados, no Haskell, isso é uma exigência. Como listas são homogeneas na linguagem, a principal utilidade de uma tupla é a estruturação heterogênea de dados, ou seja, unir dados com tipos diferentes sem a necessidade de criar novas estruturas (structs).
```
fuzzObjectR :: ValueExt -> Gen ValueExt
fuzzObjectR trm = do
  key <- arbitrary
  pairs <- arbitrary @[(T.Text, ValueExt)]
  pure $ RequiredFieldAccess P.emptySpan (Object P.emptySpan $ Compat.fromList $ pairs <> [(key, trm)]) (Left key)
```
No exemplo acima, temos uma função que gera objetos JSON aleatórios para o teste de alguma função que irá os processar. Na quarta linha, a função utiliza outra função, a "arbitrary" para gerar valores aleatórios para uma lista de pares. A forma que o desenvolver encontrou para listar esses pares foi uma lista de tupla. Ao invés de criar uma estrutura para poder conter esses pares, foi necessário apenas o uso de uma tupla.
# Testando Tuplas
![Primeiro Exemplo](https://github.com/elc117/apresentacao-bim1-2025b-rnnr11/blob/main/primeiro%20exemplo.gif)
teste
![Segundo Exemplo](https://github.com/elc117/apresentacao-bim1-2025b-rnnr11/blob/main/segundo%20exemplo.gif)
teste
![Terceiro Exemplo](http://github.com/elc117/apresentacao-bim1-2025b-rnnr11/blob/main/terceiro%20exemplo.gif)
