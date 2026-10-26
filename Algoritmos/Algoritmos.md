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

## Desempenho de Algoritmos

Ao desenvolver um algoritmo, precisamos avaliar o quão eficiente ele é ao processar volumes crescentes de dados. Essa eficiência pode ser avaliada sob duas perspectivas:

1. **Complexidade temporal:** Quanto tempo (ou quantas operações) o algoritmo leva para ser executado.
2. **Complexidade espacial:** Quanta memória RAM o algoritmo exige durante sua execução.

### Complexidade temporal

Por mais que possa parecer natural medir a eficiência pelo tempo gasto, como 0,5 segundo de execução, essa medição não é precisa, pois envolve vários fatores externos ao algoritmo, como:

- **Linguagem de programação:** Uma linguagem compilada executa as instruções mais rapidamente do que uma linguagem interpretada.
- **Carga do sistema:** Programas executados em segundo plano no momento do teste interferem diretamente no tempo de execução do algoritmo.
- **Hardware:** Processadores mais rápidos executam o mesmo código em menos tempo.
- **Tamanho da entrada:** Um algoritmo pode apresentar excelente desempenho com um baixo volume de dados, mas tornar-se muito lento com um alto volume de dados.

Devido a esses fatores, devemos desvincular a medição da eficiência do hardware e passar a medir o número de operações que o algoritmo realiza conforme o tamanho da entrada cresce.

**Tamanho da entrada (`n`) e função `f(n)`**

O tamanho da entrada é representado pela variável `n`. O desempenho do algoritmo é avaliado pelo crescimento do número de operações, representado por `f(n)`, em função do aumento de `n`.

**Busca sequencial e acesso direto**

Há basicamente duas formas distintas de realizar operações em uma estrutura com `n` elementos:

- **Acesso direto:** Os elementos são acessados diretamente por meio de uma única operação matemática, permitindo acessar qualquer dado independentemente do tamanho da estrutura, mantendo um tempo constante.
    - **Exemplo:** Acessar um vetor com 3 ou 30 elementos não afeta o desempenho, pois todos os elementos são acessados por meio de seus índices, mantendo o mesmo tempo de execução. `vetor[indice]`

- **Busca sequencial:** Para saber se um valor está na estrutura, os itens são percorridos individualmente, do primeiro até encontrar o valor desejado ou chegar ao último. À medida que `n` cresce, podem ser necessárias mais operações.
    - **Exemplo:** Para verificar se o elemento `x` está na lista `y`, precisamos verificar cada item individualmente até encontrá-lo ou chegar ao final da lista. `for i in lista`

**Melhor cenário x pior cenário**

Ao elaborar algoritmos, devemos considerar os cenários em que serão aplicados. Os principais são:

- **Melhor cenário:** A análise desse cenário descreve o desempenho do algoritmo sob as condições mais favoráveis de entrada, considerando a quantidade mínima de operações necessárias para concluir uma tarefa. Não é uma boa métrica isoladamente, pois dificilmente representa todas as situações de uso.
- **Pior cenário:** A análise de desempenho foca principalmente nas condições menos favoráveis de entrada, buscando maior garantia de desempenho por meio da definição de um limite matemático para o número de operações necessárias.

### Complexidade Espacial