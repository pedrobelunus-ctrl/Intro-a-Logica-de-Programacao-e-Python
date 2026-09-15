# Intro-a-Logica-de-Programacao-e-Python
Um guia para iniciantes na programação pela lógica de programação e linguagem python

# Objetivo:
O material do assunto escolhido foi lógica de programação em linguagem python, como iniciei na área de programação recentemente estudando de casa com materiais gratuitos decide então criar esse guia com o auxilio do notebookLM.
O objetivo é dominar a lógica e o básico da linguagem nesse inicio de estudos e através desse guia acessar as informações relevantes de forma mais precisa e eficaz.

# Fontes:
Para adquirir fontes de conhecimentos ao notebooLM busquei alguns vídeos no youtube, arquivos adquiridos de um curso que realizei, e PDF obtido através de pesquisas, e através de alguns desses materiais pedi que algumas IAs verificasse se faltava mais alguma informação interessante onde pudesse está agregando conhecimento e que gerassem arquivos de apoio complementares referente ao assunto para um compreensão e aproveitamento melhor.
Links YouTube:
https://youtu.be/2uBrqwj70TQ

https://youtu.be/epf-WQdVis0

https://youtu.be/WexDtLkN77k

# Prompts Utilizados e suas Respostas:

No inicio tive um pouco de dificuldade para entender laços e saber como funcionam, e aqui vou mostrar a explicação obtida sobre o assunto através do notebook com alguns prompts e suas variações para detalhar sobre cada uma.

1. Qual a diferença entre os laços de repetição For e While?

    A principal diferença entre os laços **`for`** e **`while`** em Python está no **controle do número de repetições** e no **cenário de uso recomendado**:

---

### 1. Laço `for`
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

### 2. Laço `while`
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

### Resumo Comparativo

| Característica | Laço `for` | Laço `while` |
| :--- | :--- | :--- |
| **Condição de Parada** | Chegada ao fim da coleção/sequência ou limite do `range()`. | Falsidade da condição lógica avaliada (`False`). |
| **Conhecimento Prévio** | Usado quando o número de iterações é conhecido ou delimitado. | Usado quando o número de iterações é incerto (ex.: aguardar uma senha válida). |
| **Controle de Variável** | A avanço dos elementos ocorre de forma automática. | Exige atualização manual da condição/contador no corpo do laço. |

---

### Recursos Comuns
* **`break`**: Interrompe e encerra a execução do laço imediatamente.
* **`continue`**: Interrompe a iteração atual e avança para a próxima.
* **`else`**: Pode ser adicionado ao final do laço para executar um bloco quando a repetição é concluída normalmente (sem ter sido interrompida por um `break`).

# VARIAÇÕES PARA ESSA PERGUNTA:

2.Pode me dar um exemplo de Loop Infinito no While?

  Um **loop infinito** no laço `while` ocorre quando a condição testada permanece continuamente verdadeira, fazendo com que o programa execute o bloco de código indefinidamente.

Abaixo estão os dois cenários mais comuns em que isso acontece em Python:

---

### 1. Condição fixa sempre verdadeira (`while True`)
Quando o valor `True` é informado diretamente como a condição do `while`, o laço é instruído a executar para sempre, pois a condição nunca se tornará falsa.

```python
while True:
    print("Este loop nunca vai parar!")
```

---

### 2. Esquecer de atualizar a variável de controle
Este é o caso involuntário mais comum. Ocorre quando a condição depende de uma variável (como um contador ou valor de comparação), mas o valor dessa variável **não é alterado** dentro do bloco do `while`.

```python
vendas = 100
meta = 200

# Como 'vendas' não muda dentro do laço, a condição '100 < 200' será sempre verdadeira
while vendas < meta:
    print("Não bateu a meta!")
```

---

### Como corrigir ou controlar esse comportamento?
* **Incrementar/Atualizar a variável:** É necessário garantir que a variável presente na condição seja modificada a cada volta (iteração) do laço até que a condição finalmente se torne falsa.
* **Uso do `break`:** Caso seja necessário usar uma estrutura `while True` de propósito (por exemplo, para continuar pedindo dados ao usuário até que ele digite uma informação válida), utiliza-se a instrução `break` para encerrar o laço manualmente.

3. Somente o a palavra True pode ser utilizada após o while já vi em outros codígos outras palavras, como isso funciona?

   **Não, a palavra `True` não é a única que pode ser utilizada após o `while`.** 

O laço `while` aceita qualquer **condição lógica** ou **expressão**. Ele continua executando o bloco de código repetidamente enquanto essa condição for avaliada como verdadeira. 

Em programas reais, é muito comum utilizar variáveis, operadores de comparação ou operadores lógicos após o `while`:

---

### 1. Comparações Numéricas e Contadores
Você pode usar variáveis numéricas acompanhadas de operadores de comparação (como `<`, `>`, `<=`, `>=`, `==`, `!=`).
* **Contador de tentativas:** `while tentativas < 3:` faz o laço rodar enquanto a variável `tentativas` for menor que 3.
* **Controle de horário:** `while horario <= 17:` executa enquanto a variável `horario` for menor ou igual a 17.

---

### 2. Validação de Textos e Senhas
É possível verificar textos inseridos pelo usuário comparando variáveis do tipo *string*.
* **Verificação de senha:** `while senha != '123456':` repete a solicitação enquanto a variável `senha` for diferente do texto esperado.
* **Texto vazio:** `while nome == '':` repete o laço enquanto a variável `nome` estiver vazia.

---

### 3. Operações Matemáticas na Condição
É permitido realizar cálculos na própria expressão do laço.
* **Verificando número par:** `while numero % 2 == 0:` calcula se o resto da divisão da variável `numero` por 2 é igual a 0.

---

### 4. Múltiplas Condições com Operadores Lógicos (`and` / `or`)
Você pode conectar duas ou mais comparações na mesma linha utilizando operadores como `and` ou `or`.
* **Dupla validação:** `while usuario != 'Jonathan' and senha != '123456':` exige que tanto o usuário quanto a senha estejam incorretos para que o laço continue.

---

### 5. Variáveis Booleanas e Avaliação de "Valor de Verdade"
* **Variável lógica:** você pode usar a comparação direta com uma variável que guarda um booleano, como `while acertou == False:`.
* **Valor de verdade (*Truthy/Falsy*):** o Python não exige obrigatoriamente um objeto do tipo `bool` na condição. Valores como o número `0`, `None` e textos vazios (`""`) são avaliados como falsos, enquanto textos com conteúdo e números diferentes de zero são considerados verdadeiros.

---

# 
