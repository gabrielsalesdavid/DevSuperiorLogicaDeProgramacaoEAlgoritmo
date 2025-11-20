# 🔧 Conceitos de Sintaxes - Portugol/VisualG

## Introdução

Este documento detalha a **sintaxe específica do Portugol/VisualG**, a linguagem de programação utilizada neste repositório. Inclui estruturas, comandos e exemplos práticos.

---

## 1. Estrutura Geral de um Programa

### Componentes Principais

```
Algoritmo "nome_do_algoritmo"

Var
   // Declaração de variáveis globais

Inicio

   // Código principal do algoritmo

Fimalgoritmo
```

### Explicação dos Componentes

| Componente | Função |
|-----------|--------|
| `Algoritmo "nome"` | Define o início do algoritmo com um nome |
| `Var` | Seção onde declaram-se as variáveis |
| `Inicio` | Marca o início das instruções executáveis |
| `Fimalgoritmo` | Marca o fim do algoritmo |

---

## 2. Declaração de Variáveis

### Sintaxe Básica

```
Var
   nome_variavel : tipo_de_dado
   outra_variavel : tipo_de_dado
```

### Tipos de Dados Disponíveis

```
Var
   idade : inteiro           // números inteiros
   preco : real              // números decimais
   mensagem : caractere      // texto
   ativo : logico            // true/false (verdadeiro/falso)
   datas : vetor[0..10] de caractere   // array
```

### Múltiplas Variáveis do Mesmo Tipo

```
Var
   a, b, c : inteiro
   nome, sobrenome : caractere
```

---

## 3. Atribuição de Valores

### Operador de Atribuição: `<-`

```
variavel <- valor
idade <- 25
nome <- "João Silva"
salario <- 3500.50
ativo <- verdadeiro
```

### Atribuição com Operações

```
resultado <- 10 + 5
area <- 3.14 * raio * raio
nome_completo <- nome + " " + sobrenome
```

---

## 4. Entrada e Saída de Dados

### Comando `leia()` - Entrada de Dados

Lê um valor do teclado e armazena em uma variável:

```
Var
   idade : inteiro

Inicio
   leia(idade)  // Aguarda o usuário digitar um valor
Fimalgoritmo
```

#### Leitura Múltipla

```
Var
   nome : caractere
   idade : inteiro
   altura : real

Inicio
   leia(nome)
   leia(idade)
   leia(altura)
Fimalgoritmo
```

### Comando `escreva()` - Saída sem Quebra de Linha

```
escreva("Seu nome é: ")  // Exibe sem pular linha
```

### Comando `escreval()` - Saída com Quebra de Linha

```
escreval("Bem-vindo!")  // Exibe e pula para próxima linha
escreval("Digite seu nome: ")
```

#### Exibir Variáveis

```
escreval("Nome: ", nome)
escreval("Idade: ", idade)
```

#### Formatação de Números

```
escreval("Valor: R$", preco:5:2)  // preco com 5 dígitos e 2 decimais
escreval("Percentual: ", porcentagem:6:1)  // 6 dígitos, 1 decimal
```

#### Quebra de Linha Vazia

```
escreval()  // Pula uma linha
```

---

## 5. Operadores Aritméticos

### Operações Básicas

```
resultado <- 10 + 5      // Adição: 15
resultado <- 10 - 3      // Subtração: 7
resultado <- 4 * 5       // Multiplicação: 20
resultado <- 20 / 4      // Divisão: 5
resultado <- 20 % 3      // Módulo (resto): 2
resultado <- 2 ^ 8       // Potência: 256
```

### Expressões Compostas

```
resultado <- (5 + 3) * 2     // Respeita precedência de operadores
resultado <- 10 / 2 + 3 * 4  // = 5 + 12 = 17
resultado <- ((10 + 5) * 2) / 3  // Parênteses para clareza
```

---

## 6. Operadores Relacionais

Comparações que resultam em `verdadeiro` ou `falso`:

```
5 = 5        // Igual (verdadeiro)
5 <> 3       // Diferente (verdadeiro)
3 < 5        // Menor que (verdadeiro)
7 > 2        // Maior que (verdadeiro)
5 <= 5       // Menor ou igual (verdadeiro)
6 >= 4       // Maior ou igual (verdadeiro)
```

---

## 7. Operadores Lógicos

### `e` - AND (E lógico)

Verdadeiro apenas se **ambas** as condições forem verdadeiras:

```
se (idade >= 18) e (carteira_motorista = verdadeiro) entao
   escreval("Pode dirigir")
fimse
```

### `ou` - OR (OU lógico)

Verdadeiro se **pelo menos uma** condição for verdadeira:

```
se (dia = "sabado") ou (dia = "domingo") entao
   escreval("É fim de semana!")
fimse
```

### `nao` - NOT (NÃO lógico)

Inverte o valor lógico:

```
se nao (lluva = verdadeiro) entao
   escreval("Dia ensolarado!")
fimse
```

### Combinações

```
se ((idade >= 18) e (renda > 1000)) ou (renda > 5000) entao
   // lógica complexa
fimse
```

---

## 8. Estrutura Condicional: `se` / `senao` / `fimse`

### Se Simples

```
se condicao entao
   bloco_de_comandos
fimse
```

**Exemplo:**

```
Var
   idade : inteiro

Inicio
   leia(idade)
   se idade >= 18 entao
      escreval("Você é maior de idade")
   fimse
Fimalgoritmo
```

### Se-Senão (If-Else)

```
se condicao entao
   bloco_se_verdadeiro
senao
   bloco_se_falso
fimse
```

**Exemplo:**

```
Var
   nota : real

Inicio
   leia(nota)
   se nota >= 6 entao
      escreval("Aprovado!")
   senao
      escreval("Reprovado!")
   fimse
Fimalgoritmo
```

### Se Aninhado (Nested If)

```
se condicao1 entao
   se condicao2 entao
      escreval("Ambas as condições são verdadeiras")
   fimse
senao
   se condicao3 entao
      escreval("Condição 1 falsa, mas 3 verdadeira")
   fimse
fimse
```

**Exemplo Prático:**

```
Var
   hora : inteiro

Inicio
   escreval("Digite a hora: ")
   leia(hora)
   
   se hora < 12 entao
      escreval("Bom dia!")
   senao
      se (hora >= 12) e (hora < 18) entao
         escreval("Boa tarde!")
      senao
         escreval("Boa noite!")
      fimse
   fimse
Fimalgoritmo
```

---

## 9. Estrutura de Seleção: `escolha` / `caso` / `fimescolha`

Para múltiplas opções baseadas no valor de uma variável:

### Sintaxe

```
escolha variavel
caso valor1:
   comando_1
caso valor2:
   comando_2
caso valor3:
   comando_3
outrocaso:
   comando_padrao
fimescolha
```

### Exemplo

```
Var
   opcao : inteiro

Inicio
   escreval("Menu:")
   escreval("1 - Somar")
   escreval("2 - Subtrair")
   escreval("3 - Sair")
   escreval("Digite sua opção: ")
   leia(opcao)
   
   escolha opcao
   caso 1:
      escreval("Opção de soma selecionada")
   caso 2:
      escreval("Opção de subtração selecionada")
   caso 3:
      escreval("Saindo do programa")
   outrocaso:
      escreval("Opção inválida!")
   fimescolha
Fimalgoritmo
```

---

## 10. Laços de Repetição

### 10.1 `para` / `fimpara` - For Loop

Repete um bloco de código um número **específico** de vezes:

#### Sintaxe

```
para variavel de inicio ate fim [passo valor] faca
   bloco_de_comandos
fimpara
```

#### Exemplo Básico

```
Var
   i : inteiro

Inicio
   para i de 1 ate 5 faca
      escreval(i)
   fimpara
Fimalgoritmo
```

**Saída:**
```
1
2
3
4
5
```

#### Com Passo (Incremento Customizado)

```
para i de 0 ate 10 passo 2 faca
   escreval(i)
fimpara
```

**Saída:**
```
0
2
4
6
8
10
```

#### Decrementando

```
para i de 10 ate 1 passo -1 faca
   escreval(i)
fimpara
```

**Saída:**
```
10
9
8
...
2
1
```

### 10.2 `enquanto` / `fimenquanto` - While Loop

Repete enquanto uma **condição** for verdadeira:

#### Sintaxe

```
enquanto condicao faca
   bloco_de_comandos
fimenquanto
```

#### Exemplo

```
Var
   contador : inteiro

Inicio
   contador <- 1
   enquanto contador <= 5 faca
      escreval(contador)
      contador <- contador + 1
   fimenquanto
Fimalgoritmo
```

#### Leitura com Validação

```
Var
   idade : inteiro

Inicio
   idade <- 0
   enquanto idade <= 0 faca
      escreval("Digite uma idade válida (> 0): ")
      leia(idade)
   fimenquanto
   escreval("Sua idade é: ", idade)
Fimalgoritmo
```

### 10.3 `repita` / `ate` - Do-Until Loop

Executa **pelo menos uma vez** e repete **até** a condição ser verdadeira:

#### Sintaxe

```
repita
   bloco_de_comandos
ate condicao
```

#### Exemplo

```
Var
   numero : inteiro

Inicio
   repita
      escreval("Digite um número entre 1 e 10: ")
      leia(numero)
   ate (numero >= 1) e (numero <= 10)
   
   escreval("Número válido: ", numero)
Fimalgoritmo
```

---

## 11. Vetores (Arrays Unidimensionais)

### Declaração

```
Var
   numeros : vetor[0..9] de inteiro
   nomes : vetor[1..100] de caractere
   valores : vetor[0..99] de real
```

### Acesso e Modificação

```
Var
   vet : vetor[0..4] de inteiro

Inicio
   vet[0] <- 10
   vet[1] <- 20
   vet[2] <- 30
   escreval(vet[0])  // Exibe: 10
Fimalgoritmo
```

### Iteração em Vetor

```
Var
   vet : vetor[0..9] de inteiro
   i : inteiro

Inicio
   // Preenchendo o vetor
   para i de 0 ate 9 faca
      escreval("Digite um número: ")
      leia(vet[i])
   fimpara
   
   // Exibindo o vetor
   para i de 0 ate 9 faca
      escreval(vet[i])
   fimpara
Fimalgoritmo
```

---

## 12. Matrizes (Arrays Bidimensionais)

### Declaração

```
Var
   matriz : vetor[0..2, 0..2] de inteiro
   tabela : vetor[1..10, 1..5] de real
```

### Acesso

```
Var
   mat : vetor[0..1, 0..1] de inteiro

Inicio
   mat[0][0] <- 1
   mat[0][1] <- 2
   mat[1][0] <- 3
   mat[1][1] <- 4
   escreval(mat[0][1])  // Exibe: 2
Fimalgoritmo
```

### Iteração em Matriz

```
Var
   mat : vetor[0..2, 0..2] de inteiro
   i, j : inteiro

Inicio
   // Preenchendo
   para i de 0 ate 2 faca
      para j de 0 ate 2 faca
         leia(mat[i][j])
      fimpara
   fimpara
Fimalgoritmo
```

---

## 13. Funções

### Definição de Função

```
funcao nome_funcao(param1 : tipo1, param2 : tipo2) : tipo_retorno

inicio
   // instruções
   retorne valor
fimfuncao
```

### Exemplos

#### Função Simples

```
funcao soma(a : inteiro, b : inteiro) : inteiro

inicio
   retorne a + b
fimfuncao
```

#### Função com Múltiplos Parâmetros

```
funcao media(nota1 : real, nota2 : real, nota3 : real) : real

inicio
   retorne (nota1 + nota2 + nota3) / 3
fimfuncao
```

#### Uso em Programa

```
Algoritmo "teste_funcao"

funcao dobro(x : inteiro) : inteiro
inicio
   retorne x * 2
fimfuncao

Var
   resultado : inteiro

Inicio
   resultado <- dobro(5)
   escreval("Resultado: ", resultado)  // Exibe: 10
Fimalgoritmo
```

---

## 14. Procedimentos

### Definição

```
procedimento nome_procedimento(param1 : tipo1, param2 : tipo2)

Var
   variaveis_locais

inicio
   // instruções (sem retorno)
fimprocedimento
```

### Exemplo

```
Algoritmo "teste_procedimento"

procedimento saudacao(nome : caractere)

inicio
   escreval("Olá, ", nome, "!")
fimprocedimento

Inicio
   saudacao("Maria")
   saudacao("João")
Fimalgoritmo
```

---

## 15. Passagem de Parâmetros

### Por Valor

O valor é copiado; modificações não afetam a variável original:

```
procedimento incrementar(valor : inteiro)

inicio
   valor <- valor + 1
fimprocedimento

Var
   numero : inteiro

Inicio
   numero <- 5
   incrementar(numero)
   escreval(numero)  // Exibe: 5 (não foi modificado)
Fimalgoritmo
```

### Por Referência

A variável é passada diretamente; modificações a afetam:

```
procedimento incrementar(var valor : inteiro)

inicio
   valor <- valor + 1
fimprocedimento

Var
   numero : inteiro

Inicio
   numero <- 5
   incrementar(numero)
   escreval(numero)  // Exibe: 6 (foi modificado!)
Fimalgoritmo
```

---

## 16. Funções Matemáticas Integradas

```
abs(x)          // Valor absoluto: abs(-5) = 5
raizq(x)        // Raiz quadrada: raizq(9) = 3
int(x)          // Parte inteira: int(3.7) = 3
rnd()           // Número aleatório entre 0 e 1
sen(x)          // Seno (em radianos)
cos(x)          // Cosseno (em radianos)
tan(x)          // Tangente (em radianos)
exp(x)          // e^x
log(x)          // Logaritmo natural
```

**Exemplo:**

```
Var
   resultado : real

Inicio
   resultado <- raizq(16)      // 4
   resultado <- abs(-10)       // 10
   resultado <- int(7.89)      // 7
   escreval(resultado)
Fimalgoritmo
```

---

## 17. Escopo e Variáveis Locais

### Variáveis Globais

Declaradas na seção `Var` principal, acessíveis em todo o programa:

```
Algoritmo "escopo"

Var
   global : inteiro  // Acessível em toda parte

funcao exemplo() : inteiro
inicio
   global <- global + 1
   retorne global
fimfuncao

Inicio
   global <- 10
   escreval(exemplo())  // Modifica e usa global
Fimalgoritmo
```

### Variáveis Locais

Declaradas dentro de funções/procedimentos, existem apenas naquele escopo:

```
funcao calcular() : inteiro

Var
   local : inteiro  // Só existe aqui

inicio
   local <- 5
   retorne local
fimfuncao
```

---

## 18. Exemplos Integrados

### Exemplo 1: Encontrar Maior Número em Vetor

```
Algoritmo "maior_vetor"

Var
   vet : vetor[0..9] de inteiro
   i, maior : inteiro

Inicio
   maior <- -2147483648  // valor muito pequeno
   
   para i de 0 ate 9 faca
      escreval("Digite um número: ")
      leia(vet[i])
   fimpara
   
   para i de 0 ate 9 faca
      se vet[i] > maior entao
         maior <- vet[i]
      fimse
   fimpara
   
   escreval("Maior número: ", maior)
Fimalgoritmo
```

### Exemplo 2: Validação de Entrada

```
Algoritmo "validacao"

Var
   idade : inteiro

Inicio
   idade <- 0
   
   repita
      escreval("Digite sua idade (0-150): ")
      leia(idade)
      
      se (idade < 0) ou (idade > 150) entao
         escreval("Idade inválida! Tente novamente.")
      fimse
   ate (idade >= 0) e (idade <= 150)
   
   escreval("Idade registrada: ", idade)
Fimalgoritmo
```

### Exemplo 3: Tabela de Multiplicação

```
Algoritmo "tabuada"

Var
   numero, i, resultado : inteiro

Inicio
   escreval("Digite um número: ")
   leia(numero)
   
   para i de 1 ate 10 faca
      resultado <- numero * i
      escreval(numero, " x ", i, " = ", resultado)
   fimpara
Fimalgoritmo
```

---

## 19. Dicas de Sintaxe

| Aspecto | Regra |
|---------|-------|
| **Case Sensitivity** | Não diferencia maiúsculas/minúsculas |
| **Indentação** | Não obrigatória, mas recomendada |
| **Comentários** | Não existem em VisualG puro (use `//` em alguns editores) |
| **Pontuação** | Não usa ponto-e-vírgula no final das linhas |
| **Palavras-chave** | `Algoritmo`, `Var`, `Inicio`, `Fimalgoritmo` |
| **Operador atribuição** | Sempre `<-` (nunca `=`) |

---

## 20. Resumo de Comandos Principais

```
leia(variavel)                    // Entrada
escreva() / escreval()            // Saída
variavel <- valor                 // Atribuição
se ... entao ... fimse           // Condicional
escolha ... caso ... fimescolha  // Seleção múltipla
para ... fimpara                 // Repetição determinada
enquanto ... fimenquanto         // Repetição condicional
repita ... ate                   // Repetição pós-condicional
funcao ... retorne               // Função
procedimento ... fimprocedimento // Procedimento
```

---

## Conclusão

A sintaxe do Portugol/VisualG é intuitiva e pedagógica, perfeita para aprender conceitos de programação. Pratique com os exemplos fornecidos nos arquivos `.ALG` deste repositório!
