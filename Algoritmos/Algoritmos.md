# Estruturas de Dados

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

Estruturas de Dados (também conhecidas como variáveis compostas) são variáveis que, em vez de armazenar apenas 1 valor em 1 endereço, armazenam múltiplos valores em uma sequência de endereços. É como a diferença entre uma casa e um edifício.

Nas estruturas de dados básicas, como os vetores, o computador reserva uma parte da memória RAM, dividida em subespaços sequenciais. Esse modelo garante desempenho por meio da previsibilidade das posições, a partir da posição inicial e do índice desejado. Pense que o processador só precisa identificar o endereço inicial da estrutura e somá-lo ao índice, que, por sua vez, é multiplicado pelo tamanho do tipo de dado (Endereço + Índice × Tipo de Dado).

Em contrapartida, há estruturas em que os dados são armazenados de forma dispersa, o que traz vantagens quanto à maleabilidade da estrutura, mas ao custo de desempenho.

Essas estruturas podem ser classificadas em dois tipos:

- Estruturas Homogêneas: são estruturas que guardam apenas o mesmo tipo de dado. Ex.: arrays e matrizes.
- Estruturas Heterogêneas: são estruturas que permitem armazenar vários tipos de dados. Ex.: listas e tuplas.