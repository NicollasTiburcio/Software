# Lógica de Programação
Lógica de programação é o emprego de raciocínio lógico para compreensão e resolução de problemas através do uso de algoritmos estruturados.

## Tipos de Linguagem

**Linguagem de Máquina** é a linguagem de mais baixo nível. Quase incompreensível para o ser humano, mas é a única que o computador compreende. Ela é formada por códigos binários, usando apenas 0 e 1.

**A Linguagem Simbólica** é a linguagem intermediária entre humano e máquina. Com ela é possível criar e estruturar instruções que a máquina entende, mas representando essas instruções com símbolos e números, como o Assembly, que usa comandos como MOV, ADD e SUB para representar ações que o processador deve executar.

**Linguagem de Alto Nível** é a linguagem mais próxima da linguagem humana, usada para criar programas e algoritmos sem a necessidade de criar instrução por instrução. Alguns exemplos são a linguagem C e o Python.

## Compiladores e Interpretadores

São programas responsáveis por traduzir linguagens de programação para linguagem de máquina.

Os compiladores trabalham em 3 etapas:

1. **Tradução:** O compilador analisa o código e busca a forma mais eficiente de realizar as operações, traduzindo o código (ex: de C para Assembly).
2. **Montagem:** O programa em Assembly é transformado em linguagem de máquina, através do Assembler.
3. **Resultado:** Gera um arquivo executável pronto para ser usado.

Nos interpretadores, o programa é lido e executado linha por linha, não gerando um arquivo final "montado".
Linguagens como Python costumam utilizar este método para facilitar o desenvolvimento.

## Conceito de Algoritmo

Um algoritmo é uma sequência de passos lógicos e ordenados com o objetivo de realizar uma determinada tarefa.

Todo software é um conjunto de algoritmos direcionados a uma finalidade, não existindo programa sem um objetivo prático.

## Análise e Síntese de Problemas

Para a resolução de problemas, passamos primeiro pelo processo de análise, onde identificamos as variáveis envolvidas (entidades e condições) e elaboramos um plano de ação para solucionar o problema.

Na fase de síntese do problema, transformamos nosso plano de ação em um algoritmo para resolver o caso. É na fase de síntese que identificamos falhas lógicas em nosso plano, o que nos leva a reavaliar o plano de ação.

## Fluxograma e seus Símbolos

Fluxogramas são ferramentas visuais utilizadas para representar uma sequência de passos tomados, descrevendo a lógica para resolver um determinado problema através de símbolos gráficos.

| Símbolo                     | Nome                     | Função                                                                                                    |
| --------------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------- |
| Oval                        | Início ou Fim (Terminal) | Representa o ponto de partida e o encerramento do fluxo.                                                  |
| Seta                        | Seta (Linha de Fluxo)    | Indica o caminho e a ordem de execução dos passos.                                                        |
| Retângulo                   | Retângulo (Processo)     | Representa uma ação ou instrução direta (ex: "Colocar a água no fogo").                                   |
| Paralelogramo               | Paralelogramo (I/O)      | Usado para qualquer entrada ou saída de dados genérica.                                                   |
| Losango                     | Losango (Decisão)        | Indica um ponto onde o algoritmo precisa testar uma condição (Geralmente uma pergunta de "Sim" ou "Não"). |
| Círculo                     | Círculo (Conector)       | Conecta caminhos diferentes em um ponto no fluxograma.                                                    |
| Retângulo com canto cortado | Entrada manual           | Representa a inserção manual de dados no programa.                                                        |
| Pentágono/seta              | Exibição                 | Representa o ponto onde há exibição de informação em um fluxo.                                            |

## Tipos de Dados

Para desenvolver softwares úteis, utilizamos diversos tipos de dados e estruturas para organizar e manipular esses dados.

### Tipos primitivos

Os tipos primitivos são os tipos de dados básicos que podem ser atribuídos às variáveis, cada qual com sua função.

| Tipo | Descrição |
|---|---|
| Inteiro (int) | São números inteiros, positivos, negativos ou zero |
| Ponto flutuante (float) | São os números reais, ou seja, os que possuem casas decimais, com sua casa decimal definida com o uso do ponto |
| Strings (str) | Representam textos. Podem ser uma letra, uma palavra ou até números que deverão ser lidos como texto e não como valores. São definidas utilizando aspas |
| Booleanos (bool) | Representam os valores lógicos verdadeiro (True) e falso (False) |
| None (NoneType) | Representa a ausência de um valor |

### Tipos construídos (estruturas de dados)

Estruturas de dados são objetos criados para armazenar e manipular dados de diversas formas, cada qual com suas características próprias. De forma conceitual, as principais estruturas construídas são:

- **Lista:** Estrutura que armazena vários valores organizados por posição (índice), podendo ser alterada depois de criada (tamanho e conteúdo mutáveis).
- **Vetor:** Estrutura que armazena uma sequência de valores do mesmo tipo, organizada por índices sequenciais — é o conceito geral do qual a Lista (em Python) é uma implementação.
- **Matriz:** Estrutura organizada em linhas e colunas (um "vetor de vetores"), usada para representar dados em duas dimensões, como tabelas.

Em Python, a implementação prática desses conceitos é feita com listas (`lista = [1, 2, 3]`) e listas de listas para representar matrizes (`matriz = [[1, 2], [3, 4]]`).

#### Manipulando Listas

Além de criar uma lista, é possível adicionar e remover itens dela depois de criada:

| Operação | Comando | Função |
|---|---|---|
| Adicionar no final | `lista.append(valor)` | Adiciona um novo item ao final da lista. |
| Adicionar em posição específica | `lista.insert(indice, valor)` | Insere um novo item na posição (índice) indicada. |
| Remover pelo valor | `lista.remove(valor)` | Remove a primeira ocorrência daquele valor na lista. |
| Remover por índice | `lista.pop(indice)` | Remove e retorna o item da posição indicada. Sem índice, remove o último item. |
| Remover por índice (sem retorno) | `del lista[indice]` | Remove o item da posição indicada, sem retornar o valor removido. |

Exemplo:

```python
lista = ["João", "Maria", "Pedro"]

lista.append("Julia")        # ["João", "Maria", "Pedro", "Julia"]
lista.insert(1, "Ana")       # ["João", "Ana", "Maria", "Pedro", "Julia"]
lista.remove("Maria")        # ["João", "Ana", "Pedro", "Julia"]
lista.pop(0)                 # ["Ana", "Pedro", "Julia"]
del lista[1]                 # ["Ana", "Julia"]

print(lista)
```

### Introdução às funções

Para exibir um valor na tela, usamos `print()`. Para checar o tipo de um dado, usamos `type()`, preenchendo-a com a variável ou valor que se quer consultar.

Código:

```python
idade = 22
print(idade)
print(type(idade))
```

Saída:

```
22
<class 'int'>
```

Para receber dados digitados pelo usuário, utilizamos `input()`. Essa função captura o valor informado na forma de uma string, que pode ser armazenada em uma variável e convertida em outros tipos de dados, quando compatível.

```python
nome = input("Digite seu nome: ")
idade = input("Digite sua idade: ")

print(nome)
print(type(idade))
```

Exemplo de execução:

```
Digite seu nome: João
Digite sua idade: 22
João
<class 'str'>
```

## Operadores Aritméticos e Ordem de Precedência

São operadores utilizados para a realização de cálculos matemáticos.

| Operador | Descrição |
|---|---|
| + (Adição) | Soma "a" e "b". Em strings, faz a concatenação. |
| - (Subtração) | Subtrai "b" de "a". |
| * (Multiplicação) | Multiplica "a" por "b". Em strings, repete a string um número x de vezes. |
| / (Divisão) | Divide "a" por "b", exibindo as casas decimais. |
| // (Divisão inteira) | Divide "a" por "b", arredondando para o valor mais baixo. |
| % (Módulo) | Exibe o resto da divisão de "a" por "b". |
| ** (Exponenciação) | Faz "a" elevado a "b". |

**Precedência Matemática:** Os cálculos são realizados seguindo uma ordem de prioridade: primeiro os parênteses, depois a exponenciação, em seguida multiplicação, divisão, divisão inteira e módulo e, por último, adição e subtração.

## Operadores Lógicos e Relacionais

### Operadores Relacionais (Condicionais)

Servem para comparar valores, sendo sempre verdadeiro ou falso (booleano).

| Operador | Descrição |
|---|---|
| == | Se "a" é igual a "b" |
| != | Se "a" é diferente de "b" |
| > | Se "a" é maior que "b" |
| < | Se "a" é menor que "b" |
| >= | Se "a" é maior ou igual a "b" |
| <= | Se "a" é menor ou igual a "b" |

### Operadores Lógicos

Servem para unir 2 ou mais comparações, atribuindo resultado de acordo com sua condição.

| Operador | Descrição |
|---|---|
| and | É verdadeiro se a condição "a" e a condição "b" forem verdadeiras. |
| or | É verdadeiro se a condição "a" ou a condição "b" forem verdadeiros. |
| not | Inverte a condição de "a" (verdadeiro ou falso). |

## Estruturas Condicionais (if/else)

Servem para controlar o fluxo de um programa de acordo com suas condições.

- **if** -> É o início de uma estrutura condicional. Se for verdadeiro, executa uma operação.
- **elif** -> Se `if` for falso, executa uma nova comparação.
- **else** -> Executa se nenhuma operação for verdadeira.

## Loops e Repetições (while/for)

Quando precisamos checar um valor várias vezes ou executar um bloco de código múltiplas vezes, podemos usar as estruturas `while` e `for`.

### While (Enquanto)

Utilizamos o `while` quando não sabemos exatamente quantas vezes o código precisa se repetir. Nesta estrutura, estamos dizendo: "Enquanto uma condição for verdadeira, faça...". É preciso garantir que, em algum momento, a condição de parada seja atingida para evitar um "loop infinito" (o programa rodando indefinidamente).

```python
while condição:
    bloco de código do loop
```

### Iterável e iterador

- Um iterável é um elemento ou estrutura de dados que permite que, internamente, seus elementos sejam percorridos individualmente.
- Um iterador é um objeto que move-se dentro de uma estrutura organizada e entrega elemento por elemento, avançando automaticamente para o próximo, até que não haja mais como avançar.

### For (Para)

O `for` é uma estrutura de repetição usada para percorrer os elementos de um iterável, sendo lido conceitualmente como: "Para cada item/elemento dentro desta coleção, faça...".
No `for`, Python obtém um iterador a partir do iterável. A variável temporária recebe, a cada repetição, o próximo valor produzido pelo iterador.

```python
for i in colecao:
    bloco de código a ser executado
```

O `for` também pode ser utilizado com a função `range(x)` para repetir uma execução um número x de vezes. A contagem do `range` começa em 0 e vai até 1 valor abaixo de x.

### Controle de Fluxo (continue e break)

- **continue:** Faz com que o loop ignore o resto do código daquela repetição específica e pule direto para a próxima execução do ciclo.
- **break:** Quebra e encerra o loop imediatamente, não importando se a condição original ainda é verdadeira.

## Funções

Funções são blocos de código criados para otimizar o desenvolvimento de sistemas, permitindo a reutilização de trechos de código e evitando repetições.

A sintaxe básica para criar uma função nomeada em Python é:

```python
def nome_funcao(parametros):
    bloco de código a ser executado
    return valor
```

- **def**: é a palavra-chave usada para criar uma função.
- **nome_funcao**: é o nome que damos para a função. Esse nome será usado depois para chamar a função.
- **parametros**: são variáveis que a função pode receber para executar sua operação. Nem toda função precisa ter parâmetros.
- **return**: é usado quando queremos que a função devolva algum valor após executar sua operação. Quando a função não possui *return*, ela retorna None por padrão.

**Parâmetro x Argumento:** o parâmetro é o nome definido na criação da função para receber um valor; o argumento é o valor real enviado quando a função é chamada. Exemplo:

```python
def saudacao(nome):       # "nome" é o parâmetro
    print(f"Olá {nome}")

pessoa = "Julia"
saudacao(pessoa)           # "pessoa" é o argumento
```

Exemplo de função com `return`:

```python
def somar(a, b):
    return a + b

resultado = somar(10, 20)
print(resultado)
```