## Intro-a-Logica-de-Programacao-e-Python
Um guia para iniciantes na programação pela lógica de programação e linguagem python

## Objetivo:
O material do assunto escolhido foi lógica de programação em linguagem python, como iniciei na área de programação recentemente estudando de casa com materiais gratuitos decide então criar esse guia com o auxilio do notebookLM.
O objetivo é dominar a lógica e o básico da linguagem nesse inicio de estudos e através desse guia acessar as informações relevantes de forma mais precisa e eficaz.

## Fontes:
Para adquirir fontes de conhecimentos ao notebooLM busquei alguns vídeos no youtube, arquivos adquiridos de um curso que realizei, e PDF obtido através de pesquisas, e através de alguns desses materiais pedi que algumas IAs verificasse se faltava mais alguma informação interessante onde pudesse está agregando conhecimento e que gerassem arquivos de apoio complementares referente ao assunto para um compreensão e aproveitamento melhor.
Links YouTube:

https://youtu.be/2uBrqwj70TQ

https://youtu.be/epf-WQdVis0

https://youtu.be/WexDtLkN77k

### Prompts Utilizados e suas Respostas:

No inicio tive um pouco de dificuldade para entender laços e saber como funcionam, e aqui vou mostrar a explicação obtida sobre o assunto através do notebook com alguns prompts e suas variações para detalhar sobre cada uma.

##1. Qual a diferença entre os laços de repetição For e While?

   #Resposta:
    A principal diferença entre os laços **`for`** e **`while`** em Python está no **controle do número de repetições** e no **cenário de uso recomendado**:


# 1. Laço `for`
* **Quando utilizar:** É mais adequado quando existe um **conjunto fixo ou pré-definido de repetições**, ou quando se deseja **percorrer (iterar sobre) uma coleção de dados** (como listas, tuplas, dicionários, strings ou sequências geradas pela função `range()`).
* **Como funciona:** O laço avança automaticamente por cada elemento da coleção ou sequência até que todos os itens tenham sido processados.
* **Sintaxe básica:**
  ```python
  for item in coleção:
      # código a ser executado
  ```
* **Exemplo curto:**
  ```python
  for i in range(3):
      print(i)  # Imprime 0, 1 e 2
  ```

---

# 2. Laço `while`
* **Quando utilizar:** É recomendado quando **não se sabe de antemão quantas vezes o laço precisará rodar**, pois a execução depende exclusivamente de uma **condição lógica para continuar**.
* **Como funciona:** O bloco de código se repete continuamente **enquanto** a condição testada for verdadeira (`True`). Exige que a variável de controle seja atualizada internamente para evitar laços infinitos.
* **Sintaxe básica:**
  ```python
  while condição:
      # código a ser executado
  ```
* **Exemplo curto:**
  ```python
  tentativas = 0
  while tentativas < 3:
      print("Tente novamente")
      tentativas += 1  # Incrementa o contador
  ```

---

# Resumo Comparativo

| Característica | Laço `for` | Laço `while` |
| :--- | :--- | :--- |
| **Condição de Parada** | Chegada ao fim da coleção/sequência ou limite do `range()`. | Falsidade da condição lógica avaliada (`False`). |
| **Conhecimento Prévio** | Usado quando o número de iterações é conhecido ou delimitado. | Usado quando o número de iterações é incerto (ex.: aguardar uma senha válida). |
| **Controle de Variável** | A avanço dos elementos ocorre de forma automática. | Exige atualização manual da condição/contador no corpo do laço. |

---

# Recursos Comuns
* **`break`**: Interrompe e encerra a execução do laço imediatamente.
* **`continue`**: Interrompe a iteração atual e avança para a próxima.
* **`else`**: Pode ser adicionado ao final do laço para executar um bloco quando a repetição é concluída normalmente (sem ter sido interrompida por um `break`).

## VARIAÇÕES PARA ESSA PERGUNTA:

#1.Pode me dar um exemplo de Loop Infinito no While?

  #Resposta:
  Um **loop infinito** no laço `while` ocorre quando a condição testada permanece continuamente verdadeira, fazendo com que o programa execute o bloco de código indefinidamente.

Abaixo estão os dois cenários mais comuns em que isso acontece em Python:

---

# 1. Condição fixa sempre verdadeira (`while True`)
Quando o valor `True` é informado diretamente como a condição do `while`, o laço é instruído a executar para sempre, pois a condição nunca se tornará falsa.

```python
while True:
    print("Este loop nunca vai parar!")
```

---

# 2. Esquecer de atualizar a variável de controle
Este é o caso involuntário mais comum. Ocorre quando a condição depende de uma variável (como um contador ou valor de comparação), mas o valor dessa variável **não é alterado** dentro do bloco do `while`.

```python
vendas = 100
meta = 200

# Como 'vendas' não muda dentro do laço, a condição '100 < 200' será sempre verdadeira
while vendas < meta:
    print("Não bateu a meta!")
```

---

# Como corrigir ou controlar esse comportamento?
* **Incrementar/Atualizar a variável:** É necessário garantir que a variável presente na condição seja modificada a cada volta (iteração) do laço até que a condição finalmente se torne falsa.
* **Uso do `break`:** Caso seja necessário usar uma estrutura `while True` de propósito (por exemplo, para continuar pedindo dados ao usuário até que ele digite uma informação válida), utiliza-se a instrução `break` para encerrar o laço manualmente.

---

#2. Somente o a palavra True pode ser utilizada após o while já vi em outros codígos outras palavras, como isso funciona?

   #Resposta:
   **Não, a palavra `True` não é a única que pode ser utilizada após o `while`.** 

O laço `while` aceita qualquer **condição lógica** ou **expressão**. Ele continua executando o bloco de código repetidamente enquanto essa condição for avaliada como verdadeira. 

Em programas reais, é muito comum utilizar variáveis, operadores de comparação ou operadores lógicos após o `while`:

---

# 1. Comparações Numéricas e Contadores
Você pode usar variáveis numéricas acompanhadas de operadores de comparação (como `<`, `>`, `<=`, `>=`, `==`, `!=`).
* **Contador de tentativas:** `while tentativas < 3:` faz o laço rodar enquanto a variável `tentativas` for menor que 3.
* **Controle de horário:** `while horario <= 17:` executa enquanto a variável `horario` for menor ou igual a 17.

---

# 2. Validação de Textos e Senhas
É possível verificar textos inseridos pelo usuário comparando variáveis do tipo *string*.
* **Verificação de senha:** `while senha != '123456':` repete a solicitação enquanto a variável `senha` for diferente do texto esperado.
* **Texto vazio:** `while nome == '':` repete o laço enquanto a variável `nome` estiver vazia.

---

# 3. Operações Matemáticas na Condição
É permitido realizar cálculos na própria expressão do laço.
* **Verificando número par:** `while numero % 2 == 0:` calcula se o resto da divisão da variável `numero` por 2 é igual a 0.

---

# 4. Múltiplas Condições com Operadores Lógicos (`and` / `or`)
Você pode conectar duas ou mais comparações na mesma linha utilizando operadores como `and` ou `or`.
* **Dupla validação:** `while usuario != 'Jonathan' and senha != '123456':` exige que tanto o usuário quanto a senha estejam incorretos para que o laço continue.

---

# 5. Variáveis Booleanas e Avaliação de "Valor de Verdade"
* **Variável lógica:** você pode usar a comparação direta com uma variável que guarda um booleano, como `while acertou == False:`.
* **Valor de verdade (*Truthy/Falsy*):** o Python não exige obrigatoriamente um objeto do tipo `bool` na condição. Valores como o número `0`, `None` e textos vazios (`""`) são avaliados como falsos, enquanto textos com conteúdo e números diferentes de zero são considerados verdadeiros.

---

### Resumo

A estrutura e intuito do notebook é trazer de forma mais assertiva, didática e explicativa conhecimento inicial sobre logica de programação e linguagem python para diversas aplicações, conseguindo assim acessar e tirar dúvidas durante toda aprendizagem, tendo a possibilidade de criar resumos, podcast, vídeos, relatórios e testes para a fixação dos assuntos. 

1. Glossário:

   *Lógica de programação e Algoritmo
   
   *Fundamentos python e controle de fluxo
   
   *Estrutura de dados e coleções
   
   *Modularização e Programação Orientada a Objetos (POO)
   
   
### Prompts reutilizáveis:

5 prompts reutilizáveis baseados nos tópicos do notebook (Lógica 5Qs, Estruturas de Dados, Controle de Fluxo, Funções e POO). Você pode copiá-los e preencher os campos entre colchetes (`[...]`) sempre que quiser revisar ou praticar algum conceito.

---

## 1. Prompt para Praticar Lógica e Decomposição (Método 5Qs)
> **Finalidade:** Treinar a análise de problemas antes de codificar.
> 
> *"Atue como um tutor de programação. Quero resolver o seguinte problema em Python: **[insira a descrição do problema ou exercício aqui]**. Aplique o Método 5Qs para decompor a solução em: 1) Análise do problema, 2) Entradas de dados, 3) Processamento e restrições, 4) Saídas esperadas e 5) Passo a passo do algoritmo em pseudocódigo. Somente após essa estrutura, apresente o código em Python."*

---

## 2. Prompt para Comparação e Escolha de Estruturas de Dados
> **Finalidade:** Revisar quando usar **Listas, Tuplas, Conjuntos (`set`) ou Dicionários (`dict`)**.
> 
> *"Preciso armazenar e manipular as seguintes informações em um programa: **[descreva os dados, ex: lista de compras, registros de usuários com ID único, coordenadas fixas, etc.]**. Compare como esse problema seria resolvido usando **Listas**, **Tuplas**, **Conjuntos** e **Dicionários**. Explique qual é a estrutura mais adequada considerando **mutabilidade**, **unicidade** e **desempenho de busca**, e mostre o código prático para criação, consulta e modificação."*

---

## 3. Prompt para Diagnóstico e Análise de Controle de Fluxo (`for` vs `while`)
> **Finalidade:** Identificar bugs, riscos de loop infinito ou escolher o laço correto.
> 
> *"Analise o seguinte trecho de código em Python: **[cole o código com laços ou condicionais aqui]**. Verifique se há erros de lógica, risco de **loop infinito** no `while`, ou problemas de escopo e indexação. Explique o que está errado, mostre a versão corrigida e proponha uma versão alternativa (ex: convertendo `while` para `for` com `range()` ou iteração direta, se aplicável)."*

---

## 4. Prompt para Modularização e Refatoração de Código (`def`)
> **Finalidade:** Praticar a criação de funções limpas, escopo de variáveis e boas práticas.
> 
> *"Aqui está um script em Python que realiza uma tarefa: **[cole o script continuo/extenso aqui]**. Refatore este código dividindo-o em **funções reutilizáveis** (`def`). Garanta o uso correto de parâmetros (posicionais ou padrão), valores de retorno (`return`), separação clara entre escopo local e global, e inclua *docstrings* explicativas para cada função criada."*

---

## 5. Prompt para Modelagem em Programação Orientada a Objetos (POO)
> **Finalidade:** Criar e revisar **Classes, Objetos, `__init__`, `self` e Exceções (`try/except`)**.
> 
> *"Crie uma estrutura Orientada a Objetos para um sistema de **[ex: Gerenciamento de Biblioteca, Controle de Estoque, Sistema Bancário]**. Modele a classe principal contendo: 1) O método construtor `__init__` e o uso de `self`, 2) Pelo menos 3 atributos relevantes, 3) Métodos para manipular esses dados e 4) Tratamento de erros com blocos `try/except` para prevenir falhas comuns durante a execução."*

---
