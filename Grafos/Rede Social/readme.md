# 📊 Projeto ConectaUDF — Redes Sociais com Grafos

## 📌 Sobre o projeto

Este projeto foi desenvolvido como atividade prática da disciplina de **Estrutura de Dados**, com o objetivo de estudar e aplicar os conceitos de Teoria dos Grafos utilizando Python.

A atividade consiste em representar uma rede social fictícia chamada **ConectaUDF**, na qual os usuários são representados por vértices e suas amizades por arestas.

A partir dessa representação, foram realizados cálculos e análises para compreender a estrutura da rede social, identificar usuários com maior número de conexões e explorar possibilidades de recomendação de novas amizades.

O trabalho foi desenvolvido em grupo, em parceria entre **[Amanda Nogueira](https://github.com/Nogueira-Amanda/Estrutura_Dados_II/blob/main/Grafos/Atividade%20Rede%20Social/readme.md)** e **Silviane Souza**.

# Caderno do Estudante
## Projeto ConectaUDF: redes sociais com grafos

**Disciplina:** Algoritmos / Matemática Discreta / Ciência de Dados

---

## 1. O desafio

Você faz parte da equipe que analisa a rede social fictícia ConectaUDF. Sua missão é representar as amizades em um grafo, realizar cálculos e usar Python para interpretar a estrutura da rede.

## 2. Conceitos essenciais

- **Vértice (ou nó):** representa um usuário.
- **Aresta:** representa uma amizade entre dois usuários.
- **Grau:** quantidade de conexões diretas de um usuário.
- **Caminho:** sequência de usuários em que cada par consecutivo está conectado.
- **Densidade:** proporção entre as amizades existentes e todas as amizades possíveis.

Neste projeto, a amizade é recíproca. Portanto, usamos um **grafo não direcionado**.

## 3. Conheça os usuários

| Código | Usuário |
|:---:|---|
| A | Ana |
| B | Bruno |
| C | Carla |
| D | Diego |
| E | Elisa |
| F | Felipe |

### Amizades iniciais

- Ana — Bruno
- Ana — Carla
- Bruno — Carla
- Bruno — Diego
- Carla — Elisa
- Diego — Elisa
- Diego — Felipe
- Elisa — Felipe

## 4. Passo a passo: desenhe o grafo

1. Desenhe seis círculos, um para cada usuário.
2. Escreva o nome de cada pessoa dentro do círculo.
3. Para cada amizade da lista, desenhe uma linha entre os dois usuários.
4. Não desenhe duas linhas para a mesma amizade.
5. Confira se todas as oito amizades aparecem.

<img width="296" height="304" alt="Captura de tela 2026-11-06 130103" src="https://github.com/user-attachments/assets/cf398733-898f-49a7-b0e5-36ae9cf3e3e0" />

## 5. Passo a passo: calcule o grau

Conte quantas linhas chegam a cada círculo. Registre o resultado.

| Usuário | Amigos diretos | Grau |
|---|---|:---:|
| Ana | Bruno e Carla | 2 |
| Bruno | Ana, Carla e Diego | 3 |
| Carla | Ana, Bruno e Elisa | 3 |
| Diego | Bruno, Felipe e Elisa | 3 |
| Elisa | Carla, Felipe e Diego | 3 |
| Felipe | Elisa e Diego | 2 |

**Pergunta 1: quem tem mais conexões diretas?**

**Resposta:** Bruno, Carla, Diego e Elisa possuem mais conexões diretas, pois possuem 3 amigos cada.

## 6. Passo a passo: calcule o número de amizades

Some todos os graus. Como cada amizade conecta dois usuários, cada aresta é contada duas vezes.

**Fórmula:**

```text
Número de arestas = soma dos graus ÷ 2
```

- Soma dos graus: 16
- Divida por 2: 16 ÷ 2 = 8

**Quantas amizades existem no grafo?** 8 amizades.

## 7. Passo a passo: calcule a densidade

A densidade compara as amizades existentes com o total de amizades possíveis.

Para um grafo simples não direcionado:

\[
D = \frac{2 \times E}{V \times (V - 1)}
\]

Em que:

- `D` = densidade;
- `E` = número de arestas;
- `V` = número de vértices.

### Substitua os valores

\[
D = \frac{2 \times 8}{6 \times (6 - 1)}
\]

- Resultado decimal: **0,5333**.
- Total de amizades possíveis: **15**.
- Resultado percentual: **53,33%**.

**Interprete: a rede tem poucas ou muitas das conexões possíveis? Explique com suas palavras.**

A rede possui muitas conexões possíveis. Das 15 amizades totais que poderiam existir entre as pessoas, 8 já foram formadas. Isso indica mais da metade das conexões possíveis.

---

## 8. Passo a passo: represente o grafo em Python

A lista de adjacência registra, para cada usuário, os nomes de seus amigos. Digite o código em Python (por exemplo, no Google Colab ou em outro ambiente disponível).

### Código Python — rede inicial

```python
rede = {
    "Ana": ["Bruno", "Carla"],
    "Bruno": ["Ana", "Carla", "Diego"],
    "Carla": ["Ana", "Bruno", "Elisa"],
    "Diego": ["Bruno", "Elisa", "Felipe"],
    "Elisa": ["Carla", "Diego", "Felipe"],
    "Felipe": ["Diego", "Elisa"]
}

# Quantidade de usuarios
n = len(rede)

# Calcule o grau de cada usuario
for usuario, amigos in rede.items():
    print(usuario, "tem", len(amigos), "conexoes")

# A soma dos graus conta cada amizade duas vezes
soma_graus = sum(len(amigos) for amigos in rede.values())
arestas = soma_graus // 2

print("Total de usuarios:", n)
print("Total de amizades:", arestas)

# Densidade do grafo
densidade = (2 * arestas) / (n * (n - 1))
print(f"Densidade: {densidade:.2%}")
```

### Saída no console

```text
Ana tem 2 conexoes
Bruno tem 3 conexoes
Carla tem 3 conexoes
Diego tem 3 conexoes
Elisa tem 3 conexoes
Felipe tem 2 conexoes
Total de usuarios: 6
Total de amizades: 8
Densidade: 53.33%
```

### Entenda o código

- `rede` guarda os usuários e suas listas de amigos.
- `len(rede)` conta os usuários.
- `len(amigos)` calcula o grau de cada usuário.
- `sum(...)` soma os graus.
- `// 2` divide a soma por dois para contar cada amizade uma única vez.
- A fórmula final calcula a densidade.

## 9. Passo a passo: encontre um caminho

Encontre um caminho de Ana até Felipe. Cada passagem por uma linha corresponde a uma aresta.

**Exemplo de registro:**

`Ana → Bruno → Diego → Felipe`

**Quantas arestas há no caminho?** 3.

**Você encontrou outro caminho com a mesma quantidade de arestas? Qual?**

`Ana → Carla → Elisa → Felipe`

---

## 10. Desafio em grupo

Amplie a rede social:

1. Adicione pelo menos quatro usuários fictícios.
2. Crie no mínimo cinco novas amizades.
3. Atualize a lista de adjacência no Python.
4. Recalcule os graus, o total de arestas e a densidade.
5. Compare a densidade antes e depois da ampliação.
6. Identifique os usuários com mais conexões.
7. Explique como a rede poderia recomendar uma nova amizade.

<img width="459" height="342" alt="WhatsApp Image 2026-11-06 at 11 40 05" src="https://github.com/user-attachments/assets/4d48b9e9-a564-41eb-87cd-c95d5c504b34" />

### Cálculo do grau

| Usuário | Amigos diretos | Grau |
|---|---|:---:|
| Ana | Bruno, Carla, Laura e Irene | 4 |
| Bruno | Ana, Carla e Diego | 3 |
| Carla | Ana, Bruno, Elisa e Gabriel | 4 |
| Diego | Bruno, Felipe e Elisa | 3 |
| Elisa | Carla, Felipe, Diego e Helena | 4 |
| Felipe | Elisa, Diego, João e Marta | 4 |
| Gabriel | Carla, Irene, Amanda, Helena e Silviane | 5 |
| Helena | Elisa, Gabriel, João e Silviane | 4 |
| Irene | Ana, Laura, Gabriel e Amanda | 4 |
| João | Helena, Marta, Felipe e Silviane | 4 |
| Laura | Ana e Irene | 2 |
| Marta | João e Felipe | 2 |
| Amanda | Irene, Silviane e Gabriel | 3 |
| Silviane | Amanda, Helena, João e Gabriel | 4 |

### Amizades da rede ampliada

- Ana — Bruno
- Ana — Carla
- Ana — Laura
- Ana — Irene
- Bruno — Carla
- Bruno — Diego
- Carla — Elisa
- Diego — Elisa
- Diego — Felipe
- Elisa — Felipe
- Carla — Gabriel
- Gabriel — Irene
- Gabriel — Helena
- Gabriel — Silviane
- Irene — Laura
- Helena — João
- Elisa — Helena
- João — Marta
- João — Felipe
- Marta — Felipe
- Amanda — Silviane
- Amanda — Irene
- Amanda — Gabriel
- Silviane — Helena
- Silviane — João

### Nova lista de adjacência em Python

```python
rede = {
    "Ana": ["Bruno", "Carla", "Laura", "Irene"],
    "Bruno": ["Ana", "Carla", "Diego"],
    "Carla": ["Ana", "Bruno", "Elisa", "Gabriel"],
    "Diego": ["Bruno", "Elisa", "Felipe"],
    "Elisa": ["Carla", "Diego", "Felipe", "Helena"],
    "Felipe": ["Diego", "Elisa", "João", "Marta"],
    "Gabriel": ["Carla", "Irene", "Helena", "Amanda", "Silviane"],
    "Helena": ["Gabriel", "João", "Elisa", "Silviane"],
    "Irene": ["Ana", "Laura", "Gabriel", "Amanda"],
    "João": ["Helena", "Marta", "Felipe", "Silviane"],
    "Laura": ["Ana", "Irene"],
    "Marta": ["João", "Felipe"],
    "Amanda": ["Silviane", "Irene", "Gabriel"],
    "Silviane": ["Amanda", "Helena", "João", "Gabriel"]
}

# Quantidade de usuarios
n = len(rede)

# Calcule o grau de cada usuario
for usuario, amigos in rede.items():
    print(usuario, "tem", len(amigos), "conexoes")

# A soma dos graus conta cada amizade duas vezes
soma_graus = sum(len(amigos) for amigos in rede.values())
arestas = soma_graus // 2

print("Total de usuarios:", n)
print("Total de amizades:", arestas)

# Densidade do grafo
densidade = (2 * arestas) / (n * (n - 1))
print(f"Densidade: {densidade:.2%}")
```

### Saída no console

```text
Ana tem 4 conexoes
Bruno tem 3 conexoes
Carla tem 4 conexoes
Diego tem 3 conexoes
Elisa tem 4 conexoes
Felipe tem 4 conexoes
Gabriel tem 5 conexoes
Helena tem 4 conexoes
Irene tem 4 conexoes
João tem 4 conexoes
Laura tem 2 conexoes
Marta tem 2 conexoes
Amanda tem 3 conexoes
Silviane tem 4 conexoes
Total de usuarios: 14
Total de amizades: 25
Densidade: 27.47%
```

### Cálculo do total de arestas e densidade

**Soma dos graus:**

\[
4 + 3 + 4 + 3 + 4 + 4 + 5 + 4 + 4 + 4 + 2 + 2 + 3 + 4 = 50
\]

**Total de arestas:**

\[
50 \div 2 = 25
\]

**Densidade:**

| Grau total | Total de arestas | Densidade |
|---:|---:|---:|
| 50 | 25 | 27,47% |

Após a expansão, a rede se tornou moderadamente esparsa. Das 91 amizades possíveis entre as 14 pessoas, apenas 25 foram formadas (cerca de 27% das possibilidades), o que é um comportamento comum conforme o grupo de pessoas cresce e se formam subgrupos.

### Comparação da densidade antes e depois

Após a ampliação do círculo de amizades, a rede passou a ter 14 participantes e 25 amizades. A densidade diminuiu em relação à rede inicial, passando de **53,33% para 27,47%**. Isso significa que, apesar do aumento no número de participantes e amizades, proporcionalmente existem menos conexões em relação ao total de amizades possíveis. Portanto, a rede cresceu, mas ainda apresenta muitas possibilidades de novas conexões entre os participantes.

### Mais conexões

O usuário com mais conexões é **Gabriel**, que possui grau 5 e está conectado com o maior número de pessoas de forma direta.

### Sugestão de novas amizades

A rede poderia recomendar novas amizades identificando pessoas que ainda não são amigas, mas que possuem amigos em comum. Por exemplo, se dois participantes têm vários amigos em comum, existe a possibilidade de terem interesses ou círculos sociais semelhantes.

Na situação atual, uma recomendação possível é entre **Elisa e Gabriel**, que, apesar de não serem amigos, possuem Carla e Helena como amigos em comum.

---

## 11. Entrega

Entregue:

- desenho do grafo;
- tabela com os graus;
- cálculos de arestas e densidade;
- código Python executável;
- respostas às perguntas e breve conclusão.

## 12. Pergunta de reflexão

**Duas pessoas ainda não são amigas, mas têm três amigos em comum. Como essa informação poderia ser usada para sugerir uma nova conexão? Quais cuidados de privacidade devem ser considerados ao analisar redes sociais?**

A rede poderia utilizar essa informação para recomendar uma amizade, pois ter três amigos em comum indica que as duas pessoas possuem conexões sociais semelhantes e podem ter interesses ou círculos de convivência próximos. Assim, o sistema poderia sugerir que uma conheça a outra, aumentando as possibilidades de novas conexões.

Em relação à privacidade, é importante proteger os dados pessoais dos usuários, solicitar autorização para utilizar suas informações e não compartilhar suas amizades ou atividades sem consentimento. Também é necessário garantir que os dados sejam utilizados de forma segura e responsável, respeitando a privacidade e as escolhas de cada pessoa.

