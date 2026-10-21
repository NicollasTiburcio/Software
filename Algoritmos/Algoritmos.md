# Estruturas de Dados

Durante a execução de um algoritmo, os dados são inseridos e processados, devendo permanecer armazenados na memória RAM de alguma forma ao longo desse ciclo.

Uma variável nada mais é que um rótulo que aponta para um endereço na memória. Quando manipulamos uma variável, estamos manipulando um valor específico que está em um local da nossa RAM.

Em problemas reais de desenvolvimento de software, raramente vamos manipular valores isolados. Geralmente, precisamos manipular listas de clientes, tabelas ou conjuntos de informações. Tentar gerenciar isso com milhares de variáveis deixaria o código ilegível e inutilizável. É para solucionar isso que utilizamos estruturas de dados.

## Tipos primitivos

A memória RAM é organizada como uma grande sequência linear de endereços, onde cada posição tem 1 byte (8 bits). Quando uma variável é iniciada, o compilador (ou interpretador) identifica o tipo de dado para saber quantos bytes ela exige. Em seguida, o valor da variável é convertido em binário e gravado nos bytes reservados em um endereço que é identificado pela posição do primeiro byte que ele ocupa.

Em Python, tudo é um objeto. Não existem tipos primitivos puros, com tamanho fixo no hardware. A variável armazena apenas um ponteiro de 8 bytes, que aponta para uma estrutura contendo o dado junto a um cabeçalho de metadados do interpretador.

| Tipo  | Tamanho  | Comportamento    |
|-------|----------|------------------|
| `None`  | 16 bytes | Tamanho Fixo     |
| `Bool`  | 28 bytes | Tamanho Fixo     |
| `Float` | 24 bytes | Tamanho Fixo     |
| `Int`   | 28 bytes | Tamanho Dinâmico |
| `STR`   | 49 bytes | Tamanho Dinâmico |

*Valores aproximados para o interpretador padrão Python em sistemas de 64 bits.

## Estruturas Compostas

Estruturas de Dados (também conhecidas como variáveis compostas) são variáveis que, em vez de armazenar apenas 1 valor em 1 endereço, armazenam múltiplos valores em uma sequência de endereços. É como a diferença entre uma casa e um edifício.

Nas estruturas de dados básicas, como os vetores, o computador reserva uma parte da memória RAM, dividida em subespaços sequenciais. Esse modelo garante desempenho por meio da previsibilidade das posições, a partir da posição inicial e do índice desejado. Pense que o processador só precisa identificar o indice procurado, multiplicar pelo tamanho do dado e somar com a posiçao atual.

Em contrapartida, há estruturas em que os dados são armazenados de forma dispersa, o que traz vantagens quanto à maleabilidade da estrutura, mas ao custo de desempenho.

Essas estruturas podem ser classificadas em dois tipos:

- Estruturas Homogêneas: são estruturas que guardam apenas o mesmo tipo de dado. Ex.: arrays e matrizes.
- Estruturas Heterogêneas: são estruturas que permitem armazenar vários tipos de dados. Ex.: listas e tuplas.