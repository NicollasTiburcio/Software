# Algoritmos

Durante a execução de um algoritmo, os dados são inseridos e processados, devendo permanecer armazenados na memória RAM de alguma forma ao longo desse ciclo.

Uma variável nada mais é do que um rótulo que dá nome a um local na memória. Quando manipulamos essa variável no código, estamos acessando ou alterando o valor guardado nesse endereço da RAM.

Em problemas reais de desenvolvimento de software, raramente vamos manipular valores isolados. Geralmente, precisamos manipular listas de clientes, tabelas ou conjuntos de informações. Tentar gerenciar isso com milhares de variáveis deixaria o código ilegível e inutilizável. É para solucionar isso que utilizamos estruturas de dados.

## Tipos de Dados
Para organizar as informações na memória RAM, as linguagens de programação utilizam diferentes categorias de tipos de dados. Esses tipos definem tanto a forma como os valores são representados em binário quanto a quantidade de memória necessária para armazená-los, dividindo-se entre formas simples (que guardam um único valor) e formas compostas (que agrupam múltiplos valores).

### Tipos primitivos

A memória RAM é organizada como uma grande sequência linear de endereços, onde cada posição tem 1 byte (8 bits). Quando uma variável é declarada, o sistema identifica o tipo de dado para saber quantos bytes o valor exige. Em seguida, esse valor é convertido em binário e gravado nos bytes reservados em um endereço que é identificado pela posição do primeiro byte ocupado.

Em Python, tudo é um objeto. Não existem tipos primitivos puros, com tamanho fixo no hardware. A variável armazena uma referência (um ponteiro de 8 bytes) que aponta para o endereço onde o objeto com o valor real e seus metadados estão alocados.

| Tipo  | Tamanho  | Comportamento    |
|-------|----------|------------------|
| `None`  | 16 bytes | Tamanho Fixo     |
| `Bool`  | 28 bytes | Tamanho Fixo     |
| `Float` | 24 bytes | Tamanho Fixo     |
| `Int`   | 28 bytes | Tamanho Dinâmico |
| `STR`   | 49 bytes | Tamanho Dinâmico |

*Valores aproximados para o interpretador padrão Python em sistemas de 64 bits.*

### Estruturas Compostas

Estruturas de Dados (também conhecidas como variáveis compostas) são estruturas que, em vez de representar apenas um valor individual, permitem organizar e armazenar múltiplos valores na memória. É como a diferença entre uma casa e um edifício.

Nas estruturas de dados básicas, como os vetores, o computador reserva uma parte da memória RAM, dividida em subespaços sequenciais. Esse modelo garante desempenho por meio da previsibilidade das posições, a partir da posição inicial e do índice desejado. Pense que o processador só precisa identificar o endereço inicial da estrutura e somá-lo ao índice, que, por sua vez, é multiplicado pelo tamanho do tipo de dado (Endereço + Índice × Tipo de Dado).

Em contrapartida, há estruturas em que os dados são armazenados de forma dispersa, o que traz vantagens quanto à maleabilidade da estrutura, mas ao custo de desempenho.

Essas estruturas podem ser classificadas em dois tipos:

- Estruturas Homogêneas: são estruturas que guardam apenas o mesmo tipo de dado. Ex.: arrays e matrizes.
- Estruturas Heterogêneas: são estruturas que permitem armazenar vários tipos de dados. Ex.: listas e tuplas.

### Consolidação
- *O que é a memória RAM:* A memória RAM é estruturada de forma linear e sequencial, contendo posições de memória identificadas por seu endereço.
    - *Capacidade das posições:* Cada endereço identifica uma posição de memória capaz de armazenar 1 byte (8 bits) de informação.
- *O que são variáveis:* Variáveis são identificadores para espaços de armazenamento na memória, nos quais valores podem ser armazenados e manipulados.
- *Como os tipos de dados ocupam espaço na memória:* Os tipos de dados determinam como os valores são representados em formato binário e a quantidade de bytes necessária para armazená-los. Quando armazenados diretamente, os valores de tipos primitivos ocupam posições contíguas na memória. O espaço ocupado pode ser fixo ou variável, dependendo do tipo de dado.


## Estruturas de dados

Nesta seção, vamos investigar três estruturas de dados fundamentais em Python: Tuplas, Dicionários e Conjuntos (Sets). Cada uma delas possui características próprias de mutabilidade, organização e desempenho, sendo aplicadas em cenários específicos, de acordo com a necessidade de uso.

### Tuplas

Tuplas são coleções ordenadas e imutáveis de elementos, utilizadas principalmente para agrupar dados relacionados de forma segura contra alterações acidentais.

**Características Gerais**
- **Imutabilidade:** Após a criação, os elementos não podem ser adicionados, removidos ou modificados.
- **Ordenação:** Seus elementos são organizados por índices, mantendo a ordem exata em que foram inseridos.
- **Duplicidade de dados:** Permitem valores repetidos dentro de si.
- **Heterogêneas:** Suportam múltiplos tipos de dados simultaneamente.
- **Sintaxe:** São declaradas utilizando parênteses, com os elementos separados por vírgulas. Ex.: `tupla = (elemento1, elemento2)`

**Vantagens:** Maior proteção da integridade dos dados (devido à sua imutabilidade), menor consumo de memória e processamento em relação às listas.

**Desvantagens:** Não atendem a situações em que é necessário modificar dados com frequência.

**Cenários de Uso**
- Mapeamento de dados fixos (ex.: coordenadas geográficas `(latitude, longitude)`, datas).
- Retorno de múltiplos valores em funções.
- Resultados de consultas em bancos de dados (ex.: `(nome, cpf, data_nascimento)`).

**Exemplo de tupla**
```Python
# Criando uma tupla
tupla = ("João", 18)

# Acessando por índice
nome = tupla[0]
idade = tupla[1]

print(nome)    # Saída: "João"
print(idade)   # Saída: 18

# Contando elementos de uma tupla
print(len(tupla))    # Saída: 2
```

**Métodos de tuplas**

| Método | Descrição | Exemplo | Resultado |
|---|---|---|---|
| `count(x)` | Conta quantas vezes um valor aparece | `(1, 2, 2).count(2)` | `2` |
| `index(x)` | Retorna o índice da primeira ocorrência | `(10, 20, 30).index(20)` | `1` |

**Funções aplicáveis a tuplas**

| Função | Descrição | Exemplo | Resultado |
|---|---|---|---|
| `len()` | Retorna a quantidade de elementos | `len((1, 2, 3))` | `3` |
| `max()` | Retorna o maior elemento | `max((4, 8, 2))` | `8` |
| `min()` | Retorna o menor elemento | `min((4, 8, 2))` | `2` |
| `sum()` | Soma os elementos numéricos | `sum((1, 2, 3))` | `6` |
| `tuple()` | Converte um iterável em tupla | `tuple([1, 2, 3])` | `(1, 2, 3)` |
| `zip()` | Combina elementos de iteráveis pelos índices, produzindo tuplas. | `tuple(zip([1, 2], ["A", "B"]))` | `((1, "A"), (2, "B"))` |


### Dicionários

Dicionários são estruturas de dados que armazenam informações em pares `Chave: Valor`.

**Características Gerais**

- **Estrutura `Chave: Valor`:** Os dados são armazenados em pares, nos quais cada valor é acessado por uma chave única.
- **Chaves únicas e imutáveis:** As chaves devem ser de um tipo imutável (str, int, tuple...) e não podem ser duplicadas. Se uma chave for declarada novamente, ela irá sobrescrever o valor anterior.
- **Valores:** Os valores associados às chaves podem ser de qualquer tipo e alterados a qualquer momento.
- **Sintaxe:** São criados utilizando chaves (`{}`), com cada par separado por vírgula. Ex.: `dicionario = {"João": 18, "Julia": 20}`.

**Vantagens:** Buscas de dados extremamente rápidas, sem necessidade de percorrer os elementos da estrutura. Úteis para representar entidades e objetos por meio da combinação de chave (identificador) e valor (atributo).

**Desvantagens:** Consomem mais memória RAM do que listas e tuplas.

**Cenários de Uso**
- Mapeamento de entidades com atributos (ex.: criar a representação de um usuário e seus respectivos atributos).
- Tabelas de consulta (ex.: associar o código de um produto ao seu preço).

**Exemplo de Dicionário**

```Python
# Criando um dicionário
alunos = {"João": 18, "Julia": 20, "Igor": 17}

# Acessando valores pela chave
print(alunos["João"])    # Saída: 18

# Adicionando valores
alunos["Thiago"] = 33
print(alunos["Thiago"])   # Saída: 33

# Alterando valores
alunos["Igor"] = 19
print(alunos["Igor"])     # Saída: 19

# Removendo um par
del alunos["Igor"]
print(alunos)             # Saída: {'João': 18, 'Julia': 20, 'Thiago': 33}
```

**Métodos de dicionários**

| Método | Descrição | Exemplo | Retorno |
|---|---|---|---|
| `keys()` | Retorna uma visualização das chaves do dicionário, que pode ser percorrida ou convertida em lista | `{"A": 10, "B": 20}.keys()` | `dict_keys(['A', 'B'])` |
| `values()` | Retorna uma visualização dos valores do dicionário, que pode ser percorrida ou convertida em lista | `{"A": 10, "B": 20}.values()` | `dict_values([10, 20])` |
| `items()` | Retorna uma visualização dos pares chave-valor, representados por tuplas, que pode ser percorrida ou convertida em lista | `{"A": 10, "B": 20}.items()` | `dict_items([('A', 10), ('B', 20)])` |
| `update()` | Adiciona ou atualiza pares chave-valor | `dicionario = {"A": 10, "B": 20}; dicionario.update({"B": 30})` | `None` (modifica `dicionario`) |
| `pop(chave)` | Remove uma chave e retorna seu valor | `dicionario = {"A": 10, "B": 20}; dicionario.pop("A")` | `10` |
| `clear()` | Remove todos os elementos do dicionário | `dicionario = {"A": 10, "B": 20}; dicionario.clear()` | `dicionario = {}` |

**Funções aplicadas a dicionários**

| Função | Descrição | Exemplo | Retorno |
|---|---|---|---|
| `len()` | Retorna a quantidade de pares chave-valor | `len({"A": 10, "B": 20})` | `2` |
| `dict()` | Cria um dicionário a partir de pares chave-valor | `dict([("A", 10), ("B", 20)])` | `{'A': 10, 'B': 20}` |

### Conjuntos (Sets)

Conjuntos são coleções não ordenadas de elementos únicos, utilizadas para armazenar dados sem duplicidade e realizar operações matemáticas entre conjuntos.

**Características Gerais**

- **Elementos únicos:** Não permitem valores duplicados. Ao inserir um elemento que já existe, o conjunto permanece inalterado.
- **Não ordenados:** Os elementos não possuem posições definidas por índices, impossibilitando seu acesso por posição.
- **Mutabilidade:** Permitem adicionar e remover elementos após sua criação.
- **Elementos imutáveis:** Em Python, os conjuntos armazenam elementos de tipos imutáveis, como inteiros, strings e tuplas compostas por elementos imutáveis.
- **Heterogêneos:** Suportam diferentes tipos de dados simultaneamente, desde que sejam válidos como elementos de um conjunto.
- **Sintaxe:** São declarados utilizando chaves (`{}`), com elementos separados por vírgulas. Ex.: `conjunto = {1, 2, 3}`. Para criar um conjunto vazio, utiliza-se `set()`.

**Vantagens:** Impedem automaticamente a duplicação de dados e permitem realizar operações matemáticas entre conjuntos.

**Desvantagens:** Não permitem acesso por índices nem garantem uma ordem de apresentação dos elementos. Também podem exigir mais memória RAM do que estruturas sequenciais.

**Cenários de Uso**
- Remoção de valores duplicados em coleções.
- Verificação da existência de elementos em grandes conjuntos de dados.
- Identificação de elementos comuns ou exclusivos entre diferentes coleções.

**Exemplo de Conjunto**

```Python
# Criando um conjunto
numeros = {1, 2, 2, 3}

# Contando elementos (duplicatas são ignoradas)
print(len(numeros))    # Saída: 3

# Adicionando um elemento
numeros.add(4)
print(len(numeros))    # Saída: 4

# Removendo um elemento
numeros.remove(2)
print(len(numeros))    # Saída: 3, pois o número 2 só aparecia uma vez.

# Verificando a existência de um elemento
print(3 in numeros)    # Saída: True

# Criando conjuntos para operações matemáticas
conjunto_a = {1, 2, 3}
conjunto_b = {3, 4, 5}

# Interseção (elementos comuns)
print(conjunto_a.intersection(conjunto_b))    # Saída: {3}
```

**Métodos de conjuntos**

| Método | Descrição | Exemplo | Resultado |
|---|---|---|---|
| `add(x)` | Adiciona um elemento ao conjunto | `{1, 2}.add(3)` | Adiciona `3` ao conjunto |
| `remove(x)` | Remove um elemento; gera erro se não existir | `{1, 2}.remove(2)` | Remove `2` |
| `discard(x)` | Remove um elemento sem gerar erro caso não exista | `{1, 2}.discard(3)` | Conjunto inalterado |
| `union()` | Retorna a união de dois conjuntos | `{1, 2}.union({2, 3})` | `{1, 2, 3}` |
| `intersection()` | Retorna os elementos comuns | `{1, 2}.intersection({2, 3})` | `{2}` |
| `difference()` | Retorna os elementos exclusivos do primeiro conjunto | `{1, 2}.difference({2, 3})` | `{1}` |
| `clear()` | Remove todos os elementos | `{1, 2}.clear()` | Conjunto vazio |

**Funções aplicáveis a conjuntos**

| Função | Descrição | Exemplo | Resultado |
|---|---|---|---|
| `len()` | Retorna a quantidade de elementos | `len({1, 2, 3})` | `3` |
| `max()` | Retorna o maior elemento | `max({4, 8, 2})` | `8` |
| `min()` | Retorna o menor elemento | `min({4, 8, 2})` | `2` |
| `sum()` | Soma os elementos numéricos | `sum({1, 2, 3})` | `6` |
| `set()` | Cria um conjunto a partir de um iterável | `set([1, 2, 2, 3])` | `{1, 2, 3}` |

## Desempenho de Algoritmos

Ao desenvolver um algoritmo, precisamos avaliar o quão eficiente ele é ao processar volumes crescentes de dados. Essa eficiência pode ser avaliada sob duas perspectivas:

1. **Complexidade temporal:** Quanto tempo (ou quantas operações) o algoritmo leva para ser executado.
2. **Complexidade espacial:** Quanta memória RAM o algoritmo exige durante sua execução.

### Notação Big O

A notação Big-O (ou notação de ordem de crescimento) é utilizada para representar o desempenho e a escalabilidade de um algoritmo através do consumo de recursos em função do tamanho da entrada de dados, permitindo avaliar o tempo de execução e o consumo de memória à medida que esse volume de dados cresce.

**Tamanho da entrada (`n`) e função `f(n)`**

O tamanho da entrada é representado pela variável `n`, enquanto `f(n)` representa a quantidade de recursos necessários para executar o algoritmo, como operações de processamento ou espaço de memória.

A notação Big O estabelece um limite para o crescimento dessa função, considerando seu desempenho à medida que `n` aumenta.

**Principais classes de complexidade**

| Classe | Comportamento | Exemplo |
|---|---|---|
| `O(1)` - Constante | O consumo de recursos não cresce com `n`. | Acessar um elemento diretamente pelo índice. |
| `O(n)` - Linear | O consumo cresce proporcionalmente a `n`. | Percorrer todos os elementos de uma lista. |
| `O(n²)` - Quadrática | O consumo cresce proporcionalmente ao quadrado de `n`. | Dois laços aninhados percorrendo `n` elementos. |

Essas classes permitem comparar o crescimento dos recursos exigidos por diferentes algoritmos, tanto em relação ao processamento quanto à memória.

### Complexidade temporal

Por mais que possa parecer natural medir a eficiência pelo tempo gasto, como 0,5 segundo de execução, essa medição não é precisa, pois envolve vários fatores externos ao algoritmo, como:

- **Linguagem de programação:** Uma linguagem compilada executa as instruções mais rapidamente do que uma linguagem interpretada.
- **Carga do sistema:** Programas executados em segundo plano no momento do teste interferem diretamente no tempo de execução do algoritmo.
- **Hardware:** Processadores mais rápidos executam o mesmo código em menos tempo.
- **Tamanho da entrada:** Um algoritmo pode apresentar excelente desempenho com um baixo volume de dados, mas tornar-se muito lento com um alto volume de dados.

Devido a esses fatores, devemos desvincular a medição da eficiência do hardware e passar a medir o número de operações que o algoritmo realiza conforme o tamanho da entrada cresce.

**Tempo constante e tempo linear**

Há basicamente duas formas distintas de realizar operações em uma estrutura com `n` elementos:

- **Tempo constante (`O(1)`):** Os elementos são acessados diretamente por meio de uma única operação matemática, permitindo acessar qualquer dado independentemente do tamanho da estrutura, mantendo um tempo constante.
    - **Exemplo:** Acessar um vetor com 3 ou 30 elementos não afeta o desempenho, pois todos os elementos são acessados por meio de seus índices, mantendo o mesmo tempo de execução. `vetor[indice]`

- **Tempo linear (`O(n)`):** Para saber se um valor está na estrutura, os itens são percorridos individualmente, do primeiro até encontrar o valor desejado ou chegar ao último. À medida que `n` cresce, podem ser necessárias mais operações.
    - **Exemplo:** Para verificar se o elemento `x` está na lista `y`, precisamos verificar cada item individualmente até encontrá-lo ou chegar ao final da lista. `for i in lista`

**Melhor cenário x pior cenário**

Ao elaborar algoritmos, devemos considerar os cenários em que serão aplicados. Os principais são:

- **Melhor cenário:** A análise desse cenário descreve o desempenho do algoritmo sob as condições mais favoráveis de entrada, considerando a quantidade mínima de operações necessárias para concluir uma tarefa. Não é uma boa métrica isoladamente, pois dificilmente representa todas as situações de uso.
- **Pior cenário:** A análise de desempenho foca principalmente nas condições menos favoráveis de entrada, buscando maior garantia de desempenho por meio da definição de um limite matemático para o número de operações necessárias.

**Experimento prático**

Utilize o código abaixo para medir o tempo de execução de diferentes algoritmos. Repita os testes aumentando gradualmente o tamanho da entrada (`n`) e observe como o tempo varia.

Para facilitar os experimentos, utilize a função `range(n)`, que gera uma sequência de números inteiros de `0` até `n - 1`. Essa sequência pode ser convertida em diferentes estruturas de dados utilizando as funções já estudadas.

Ex: `list(range(n))` e  `tuple(range(n))`

*Atenção:* Essa medição não determina a complexidade temporal de um algoritmo. Ela apenas registra o tempo real de execução, que também sofre influência do hardware, da carga do sistema e de outros fatores externos.

```Python
import time

# Tamanho da entrada
n = 100

# Preparação dos dados
lista = list(range(n))
tupla = tuple(range(n))

# Início da medição
inicio = time.perf_counter()

############

# Escreva seu código aqui

############

# Fim da medição
fim = time.perf_counter()

# Calculando o tempo de execução
tempo_execucao = fim - inicio

print(f"Tempo de execução: {tempo_execucao:.6f} segundos")
```

Experimente diferentes valores para `n`, como 100, 1_000 e 10_000, comparando os resultados obtidos.

### Complexidade Espacial

A eficiência de um algoritmo vai além da quantidade de operações, envolvendo também a quantidade de memória necessária para executá-las. A complexidade espacial é a métrica usada para avaliar o consumo de memória que um algoritmo exige em função do tamanho da entrada `n`.

Para analisar esse impacto, é preciso avaliar o consumo em duas frentes:

- **Espaço de entrada:** A memória necessária para armazenar os dados brutos recebidos pelo programa.
- **Espaço auxiliar:** A memória extra alocada pelo algoritmo durante sua execução para criar variáveis, estruturas intermediárias ou gerenciar o fluxo de controle.

**Espaço constante e espaço linear**

Para compreender a aplicação dessas classes na complexidade espacial, podemos observar dois comportamentos comuns:

- **Espaço constante (`O(1)`):** O algoritmo utiliza apenas um número fixo de variáveis locais para realizar um processamento, tendo consumo de memória adicional fixo, não dependente da entrada `n`.
    - **Exemplo:** Calcular a soma de todos os números de uma lista usando uma variável acumuladora (`total += numero`).

- **Espaço linear (`O(n)`):** A quantidade de memória auxiliar necessária cresce em proporção direta ao tamanho da entrada `n`.
    - **Exemplo:** Criar uma nova lista para armazenar uma cópia ou versão transformada dos `n` elementos da lista original: `lista_dobrada = [x * 2 for x in lista]`.

Quando analisamos o espaço auxiliar, classificamos apenas a memória adicional utilizada pelo algoritmo, desconsiderando a memória necessária para armazenar os dados de entrada. Por isso, é importante distinguir essa análise da complexidade espacial total.

**Experimento prático**

Utilize o código abaixo para observar a quantidade de memória alocada durante a execução de diferentes algoritmos. Repita os testes aumentando gradualmente o tamanho da entrada (`n`) e observe como o consumo de memória varia.

Para isso, utilizaremos a biblioteca `tracemalloc`, que permite monitorar as alocações de memória realizadas pelo Python.

*Atenção:* Essa medição não determina a complexidade espacial de um algoritmo. Ela registra o pico de memória rastreada durante a execução, sem necessariamente representar toda a memória RAM utilizada pelo programa.

```python
import tracemalloc

# Tamanho da entrada
n = 100

# Preparação dos dados
lista = list(range(n))

# Início da medição
tracemalloc.start()

############
# Escreva seu código aqui
############

# Fim da medição
memoria_atual, memoria_pico = tracemalloc.get_traced_memory()

# Parada da medição
tracemalloc.stop()

#Exibição
print(f"Memória atual: {memoria_atual / 1024 ** 2: .6f} MiB")
print(f"Pico de memória: {memoria_pico / 1024 ** 2: .6f} MiB")
```

Experimente diferentes valores para `n`, como `100`, `1_000` e `10_000`, comparando os resultados obtidos.

### Tempo x espaço (trade-off)

É comum precisar escolher entre otimizar o tempo ou o espaço. Estruturas como dicionários podem consumir grandes volumes de memória para garantir buscas em tempo constante (`O(1)`), sacrificando espaço em troca de velocidade.

Por outro lado, quando a memória é um recurso crítico, em vez de manter estruturas auxiliares armazenadas, os dados são calculados no momento em que são gerados, custando mais CPU para processar, mas reduzindo o custo em memória.

### Testes de Desempenho (Benchmark)

Além da análise teórica, podemos realizar testes práticos para observar o comportamento dos algoritmos, medindo o tempo de execução e o consumo de memória em diferentes condições.

Algumas boas práticas para elaborar testes de algoritmos são:

1. **Isolar a Preparação dos Dados (Setup):** Os dados a serem processados devem ser gerados antes do início das medições, ignorando assim o tempo gasto para ler ou criar valores aleatórios.
    - **Exemplo:** Crias as listas `list(range(1000))` antes de iniciar a medição.

2. **Rodada de Aquecimento (Warm-up):** Executar o algoritmo antes de iniciar as medições, descartando os resultados iniciais para reduzir interferências relacionadas à inicialização.
    - **Exemplo:** Executar a função uma vez antes de começar a registrar os tempos com `time.perf_counter()`.

3. **Variação de Entrada e Curva de `n`:** O algoritmo deve ser testado utilizando entradas crescentes de dados, confirmando empiricamente o comportamento do algoritmo em relação a curva Big-O.
    - **Exemplo:** `n = 100` -> `n = 1000`.

4. **Medição por múltiplas repetições (Tempo):** Testar o algoritmo múltiplas vezes para avaliar o menor tempo e o tempo médio, reduzindo a influência causada por outros processos do sistema operacional.

5. **Medição de Memória (Espaço):** Avaliar as estruturas e os objetos utilizados pelo algoritmo, observando a memória alocada durante sua execução e seu pico de consumo.
