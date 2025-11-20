# 📚 Fundamentos de Programação e Algoritmos

## Introdução

Este documento apresenta os **fundamentos essenciais de programação** e **lógica algorítmica** necessários para desenvolver soluções computacionais. O conteúdo é baseado em exemplos práticos utilizando a linguagem **Portugol/VisualG**.

---

## 1. O que é um Algoritmo?

Um **algoritmo** é uma sequência finita de instruções bem definidas que resolve um problema ou realiza uma tarefa específica. Suas características principais são:

- **Finito**: possui um início e um fim
- **Determinístico**: sempre produz o mesmo resultado para as mesmas entradas
- **Eficaz**: resolve o problema proposto

### Estrutura Básica de um Algoritmo em VisualG

```
Algoritmo "nome_do_algoritmo"

Var
   declaração_de_variáveis

Inicio
   instruções_do_programa

Fimalgoritmo
```

---

## 2. Variáveis e Tipos de Dados

### Conceito de Variável

Uma **variável** é um espaço na memória do computador que armazena um valor. Ela possui:
- **Nome**: identificador único
- **Tipo**: qual tipo de dado armazena
- **Valor**: o dado armazenado

### Tipos de Dados Primitivos

| Tipo | Descrição | Exemplo |
|------|-----------|---------|
| **inteiro** | Números sem casas decimais | 42, -10, 0 |
| **real** | Números com casas decimais | 3.14, -2.5, 0.0 |
| **caractere** | Texto/string | "Olá", "A" |
| **logico** | Verdadeiro ou Falso | verdadeiro, falso |

### Declaração de Variáveis

```
Var
   idade : inteiro
   altura : real
   nome : caractere
   ativo : logico
```

### Atribuição de Valores

O operador `<-` atribui um valor a uma variável:

```
idade <- 25
altura <- 1.75
nome <- "João"
ativo <- verdadeiro
```

---

## 3. Entrada e Saída de Dados

### Saída de Dados

**`escreva()`** - Exibe um valor sem quebra de linha:
```
escreva("Valor: ", 42)  // Resultado: Valor: 42
```

**`escreval()`** - Exibe um valor e pula para a próxima linha:
```
escreval("Nome: ", "Maria")  // Resultado: Nome: Maria
                               //            (cursor na próxima linha)
```

### Entrada de Dados

**`leia()`** - Lê um valor digitado pelo usuário:
```
escreval("Digite sua idade: ")
leia(idade)
```

---

## 4. Operadores

### Operadores Aritméticos

| Operador | Operação | Exemplo |
|----------|----------|---------|
| `+` | Adição | 5 + 3 = 8 |
| `-` | Subtração | 7 - 2 = 5 |
| `*` | Multiplicação | 4 * 3 = 12 |
| `/` | Divisão | 10 / 2 = 5 |
| `%` | Resto da divisão | 10 % 3 = 1 |
| `^` | Potência | 2 ^ 3 = 8 |

### Operadores Relacionais

| Operador | Significado | Exemplo |
|----------|-------------|---------|
| `=` | Igual | 5 = 5 (verdadeiro) |
| `<>` ou `!=` | Diferente | 5 <> 3 (verdadeiro) |
| `<` | Menor que | 3 < 5 (verdadeiro) |
| `>` | Maior que | 7 > 2 (verdadeiro) |
| `<=` | Menor ou igual | 5 <= 5 (verdadeiro) |
| `>=` | Maior ou igual | 6 >= 4 (verdadeiro) |

### Operadores Lógicos

| Operador | Descrição | Exemplo |
|----------|-----------|---------|
| `e` | AND lógico (ambas verdadeiras) | (5 > 3) e (2 < 4) = verdadeiro |
| `ou` | OR lógico (pelo menos uma verdadeira) | (5 > 3) ou (2 > 4) = verdadeiro |
| `nao` | NOT lógico (inverte) | nao (5 > 3) = falso |

---

## 5. Estruturas de Controle

### 5.1 Condicionais (Se-Então-Senão)

Uma **estrutura condicional** executa diferentes blocos de código dependendo de uma condição.

#### Se Simples
```
se condicao entao
   bloco_de_comandos
fimse
```

#### Se-Senão
```
se condicao entao
   bloco_se_verdadeiro
senao
   bloco_se_falso
fimse
```

#### Se Aninhado
```
se condicao1 entao
   se condicao2 entao
      comando_1
   fimse
senao
   comando_2
fimse
```

### 5.2 Estrutura de Seleção (Escolha)

Para múltiplas opções, use a estrutura `escolha`:

```
escolha variavel
caso valor1:
   comando_1
caso valor2:
   comando_2
outrocaso:
   comando_padrão
fimescolha
```

### 5.3 Laços de Repetição

#### Para (For)
Repete um bloco um número específico de vezes:

```
para variavel de inicio ate fim [passo passovalue] faca
   bloco_de_comandos
fimpara
```

**Exemplo:**
```
para i de 1 ate 5 faca
   escreval(i)
fimpara
// Exibe: 1, 2, 3, 4, 5
```

#### Enquanto (While)
Repete enquanto uma condição for verdadeira:

```
enquanto condicao faca
   bloco_de_comandos
fimenquanto
```

#### Repita Até (Do-Until)
Executa pelo menos uma vez e repete até a condição ser verdadeira:

```
repita
   bloco_de_comandos
ate condicao
```

---

## 6. Vetores (Arrays)

Um **vetor** é uma estrutura de dados que armazena múltiplos valores do **mesmo tipo** em posições sequenciais.

### Declaração de Vetor

```
Var
   numeros : vetor[0..9] de inteiro
   nomes : vetor[1..100] de caractere
```

### Acesso a Elementos

Usa-se **índice** (posição) para acessar elementos:

```
numeros[0] <- 10
numeros[1] <- 20
escreval(numeros[0])  // Exibe: 10
```

### Exemplo Prático

```
Var
   vet : vetor[0..9] de real
   i : inteiro

Inicio
   para i de 0 ate 9 faca
      escreval("Digite um número: ")
      leia(vet[i])
   fimpara
Fimalgoritmo
```

---

## 7. Matrizes (Arrays Multidimensionais)

Uma **matriz** é um vetor bidimensional com linhas e colunas.

### Declaração

```
Var
   matriz : vetor[0..2, 0..2] de inteiro
```

### Acesso

```
matriz[0][0] <- 5
matriz[1][2] <- 10
escreval(matriz[0][0])
```

---

## 8. Funções e Procedimentos

### Funções

Uma **função** é um bloco de código reutilizável que **retorna um valor**.

#### Sintaxe

```
funcao nome_da_funcao(param1 : tipo1, param2 : tipo2) : tipo_retorno

inicio
   // comandos
   retorne valor
fimfuncao
```

#### Exemplo

```
funcao soma(a : inteiro, b : inteiro) : inteiro
inicio
   retorne a + b
fimfuncao

Algoritmo "teste"
Var
   resultado : inteiro
Inicio
   resultado <- soma(5, 3)
   escreval(resultado)  // Exibe: 8
Fimalgoritmo
```

### Procedimentos

Um **procedimento** é similar a uma função, mas **não retorna valor**.

#### Sintaxe

```
procedimento nome_do_procedimento(param1 : tipo1, param2 : tipo2)

inicio
   // comandos
fimprocedimento
```

---

## 9. Escopo de Variáveis

O **escopo** determina onde uma variável pode ser usada:

- **Variável Local**: declarada dentro de uma função/procedimento, só existe nesse bloco
- **Variável Global**: declarada na seção `Var` principal, acessível em todo o programa

### Exemplo

```
Var
   globais : inteiro  // escopo global

procedimento exemplo()
Var
   local : inteiro  // escopo local
inicio
   local <- 10
fimprocedimento
```

---

## 10. Conceitos Importantes de Programação

### Lógica Sequencial
A execução ocorre **linha por linha**, na ordem em que aparecem:

```
escreval("Primeira linha")
escreval("Segunda linha")
escreval("Terceira linha")
```

### Expressões Compostas
Combinam múltiplos operadores:

```
resultado <- (5 + 3) * 2 - 1  // = 15
condicao <- (idade >= 18) e (possui_cnH = verdadeiro)
```

### Indentação
Use indentação para melhor legibilidade:

```
se condicao entao
   se subcondicao entao
      escreval("Duas indentações")
   fimse
fimse
```

---

## 11. Boas Práticas

1. **Nomes Significativos**: `idade` em vez de `id`, `altura` em vez de `h`
2. **Comentários Claros**: explique a lógica complexa
3. **Indentação**: mantenha o código legível
4. **Validação de Entrada**: verifique se o usuário digitou dados válidos
5. **Funções Pequenas**: cada função deve fazer uma coisa bem
6. **Reutilização**: crie funções para código repetido

---

## 12. Resumo Hierárquico

```
Algoritmo
├── Variáveis (Dados)
├── Entrada (Leia)
├── Processamento
│   ├── Operações Aritméticas
│   ├── Operações Lógicas
│   └── Estruturas de Controle
│       ├── Condicionais (se/senão)
│       ├── Seleção (escolha)
│       └── Repetição (para/enquanto/repita)
├── Estruturas de Dados
│   ├── Vetores
│   └── Matrizes
├── Funções/Procedimentos
└── Saída (Escreva)
```

---

## Conclusão

Estes fundamentos são a base para criar algoritmos eficientes e programas bem estruturados. Pratique com os exemplos fornecidos no repositório para solidificar seu aprendizado!

**Próximos passos:**
- Consulte o documento `CONCEITOS_SINTAXES.md` para sintaxes específicas
- Estude os exemplos práticos em `DevSuperior/VisualG/`
- Resolva os problemas em `DevSuperior/VisualG/Problemas/`
