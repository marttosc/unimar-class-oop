# Aula 01 - Fundamentos de Programação Orientada a Objetos

---

## Índice

- [Aula 01 - Fundamentos de Programação Orientada a Objetos](#aula-01---fundamentos-de-programação-orientada-a-objetos)
  - [Índice](#índice)
  - [Paradigmas de Programação](#paradigmas-de-programação)
    - [Visão geral sobre o paradigma Imperativo](#visão-geral-sobre-o-paradigma-imperativo)
      - [Sobre o paradigma procedural](#sobre-o-paradigma-procedural)
    - [Visão geral sobre o paradigma Declarativo](#visão-geral-sobre-o-paradigma-declarativo)
    - [Ok, mas... E o paradigma de orientação a objetos?](#ok-mas-e-o-paradigma-de-orientação-a-objetos)
  - [Paradigma de Orientação a Objetos](#paradigma-de-orientação-a-objetos)
    - [Objeto em si](#objeto-em-si)
      - [Relevância do domínio](#relevância-do-domínio)
      - [Exemplo: Lêmure](#exemplo-lêmure)
      - [Exemplo: Papagaios](#exemplo-papagaios)
  - [Objeto em si (continuação)](#objeto-em-si-continuação)
    - [Generalização](#generalização)
  - [Exercícios](#exercícios)
    - [Lego](#lego)
    - [Abrigo de animais](#abrigo-de-animais)

---

## Paradigmas de Programação

São **quatro** paradigmas principais, sendo estes divididos em **dois** grupos:

- **Imperativo**
  - Procedural
  - **Orientado a Objetos**
- **Declarativo**
  - Funcional
  - Lógico

### Visão geral sobre o paradigma Imperativo

A programação é dada por instruções claras e objetivas sobre como executar alguma tarefa. Podemos compará-la à uma
**receita de bolo**.

Funções (ou _utensílios domésticos_, na analogia do bolo) permitem que determinadas funcionalidades sejam reutilizadas.

Exemplo:

- Dada a existência de ingredientes.
- Dado o preparo para o uso desses ingredientes.
- Dada a massa se formar a partir da mistura desses ingredientes.
- Dado o pré-aquecimento do forno.
- Dada a ação de assar a massa.
- Como resultado teremos o bolo.

#### Sobre o paradigma procedural

A organização do programa é dada por uma sequência de procedimentos e/ou funções.

Cada procedimento é um conjunto de comandos que tem por objetivo executar uma tarefa específica.

**Procedimento 1: Preparar a massa no liquidificador**

**Comandos:**

1. Quebrar 4 ovos.
2. Adicionar 4 colheres de sopa de chocolate em pó.
3. Adicionar 2 colheres de sopa de manteiga.
4. Adicionar 3 xícaras de chá de farinha de trigo.
5. Adicionar 2 xícaras de chá de açúcar.
6. Adicionar 1 xícara de chá de leite.
7. Definir tempo de mistura para 5 minutos.
8. Misturar ingredientes.

**Procedimento 2: Adicionar o fermento à massa**

**Comandos:**

1. Despejar a massa do liquidificador em um recipiente.
2. Adicionar 2 colheres de sopa de fermento.
3. Misturar com uma espátiula delicadamente.

**Procedimento 3: Assar o bolo**

**Comandos:**

1. Pré-aquecer o forno a 180°C.
2. Definir o tamanho da forma como alta.
3. Untar a forma com manteiga.
4. Despejar a massa na forma untada.
5. Colocar a forma no forno.
6. Definir a estimativa para assar em 40 minutos.
7. Aguardar assar o bolo.

Neste exemplo, temos **três procedimentos** para preparar um bolo.

1. Preparar a massa no liquidificador.
2. Adicionar o fermento à massa.
3. Assar o bolo.

Uma vez que todos os procedimentos estiverem concluídos, o bolo estará pronto.

Qualquer erro ou impeditivo em determinado procedimento e comando ocasionará em falha dos comandos e procedimentos
seguintes.

### Visão geral sobre o paradigma Declarativo

Enquanto os paradigmas imperativos procuram descrever **como** algo deve ser alcançado, os paradigmas declarativos
procuram descrever **o quê** deve ser alcançado.

Não é necessário ter uma sequência de procedimentos e comandos, mas sim quais as **propriedades** e **relações** devem
estar presentes no resultados.

Exemplo:

**Objetivo:** Preparar um bolo

**Declaração:** O bolo deve ter um sabor doce, a massa deve ser leve e a calda é opcional. O tamanho da forma dependerá
da quantidade desejada de bolo ao final do processo. A forma deve caber no forno. O forno deve estar pré-aquecido antes
da forma com a massa ser colocada.

**Passos:**

1. Escolher uma forma adequada e untá-la.
2. Pré-aquecer o forno.
3. Misturar os ingredientes da massa, incluindo o fermento.
4. Despejar a massa na forma.
5. Levar a forma ao forno.

---

### Ok, mas... E o paradigma de orientação a objetos?

<p align="center">
    <img src="assets/01/patrick.jpeg" alt="Patrick se perguntando sobre o paradigma que está faltando">
</p>

Vamos trabalhar sobre isso em um tópico específico, afinal este é o objeto de estudo da disciplina.

---

## Paradigma de Orientação a Objetos

### Objeto em si

O que é um objeto? O que define um objeto? Quem define um objeto? Como é um objeto?

Um objeto **representa um elemento no mundo** que possui **relevância para a solução de algum problema**.

Ele pode ser algo físico, como um livro, um celular, uma chave etc.

Também pode ser uma função atribuída à uma pessoa, como um vendedor, um aluno, um gerente etc.

Também pode-se dizer que um objeto pode ser um evento, como uma vcompra, uma ida a um show, uma ligação etc.

Um objeto pode ser um lugar, como uma loja, uma padaria, um cinema etc.

Além disso, um objeto também pode ser uma interação entre outros objetos, como os itens de uma nota fiscal.
**Pergunto-lhes: _Qual é a interação aqui?_**

---

Dentro do paradigma, um objeto é fundamentado com base em princípios como a abstração, a herança, o encapsulamento e o
polimorfismo. Podemos estender a outros não-majoritários, como por exemplo modularização.

Objetos possuem **características**, as quais são inerentes a ele mesmo. Estas são chamadas de **atributos**.

Objetos também possuem um **conjunto de ações**. Este é chamado de **conjunto de métodos**.

---

#### Relevância do domínio

🚨 **Importante!** Os atributos e métodos de um objeto devem ser definidos de acordo com as necessidades impostas pelo
domínio.

Antes de criar um objeto é necessário entender o contexto em que ele será utilizado. O domínio representa o conjunto de
situações, regras e necessidades do problema que estamos tentando resolver. Ao analisar o domínio, conseguimos
identificar quais informações são realmente importantes para cada objeto, ou seja, quais características (atributos) e
comportamentos (métodos) ele deve ter.

Portanto, entender o domínio ajuda a evitar que objetos tenham informações ou ações desnecessárias, tornando o software
mais simples, eficiente e fácil de manter.

> Sempre pense: **"O que é realmente importante para o meu problema?"** Assim, você conseguirá mapear apenas o que faz
> sentido para cada objeto.

---

#### Exemplo: Lêmure

Considere a imagem de Silvio Basílio, o lêmure. **Apenas a imagem** deverá ser suficiente para compreender o domínio e
identificar os atributos e métodos.

<img src="assets/01/lemure.jpg" alt="Silvio Basílio, o lêmure" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

Os possíveis **atributos** que Silvio Basílio pode ter:

- Nome _(o domínio lhe dá esse dado?)_
- Idade _(você consegue dizer a idade do lêmure apenas vendo a imagem?)_
- Cor do pelo _(este dado está presente na imagem?)_
- Cor dos olhos _(você consegue identificar esse dado no domínio)_
- Peso _(você consegue dizer o peso do lêmure apenas vendo a imagem?)_
- Altura _(você consegue dizer a altura do lêmure apenas vendo a imagem?)_

Ao analisarmos, sabemos que **não é possível** determinar idade, peso e altura, portanto considerando a imagem como
domínio, estes três atributos são desnecessários.

#### Exemplo: Papagaios

Considere a imagem do casal de papagaios Sebastião e Deise. **Apenas a imagem** servirá para compreensão do domínio e
identificação de atributos e métodos.

<img src="assets/01/papagaio.jpg" alt="Silvio Basílio, o lêmure" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

Papagaios, além de possuírem atributos diferentes de um lêmure (embora alguns sejam semelhantes, como por exemplo
`cor dos olhos`), possuem **métodos** como:

- Voar
- Parlar
- Comer
- Dormir
- Beber
- etc.

Observe que todo método é um verbo no infinitivo.

---

## Objeto em si (continuação)

É por meio dos **métodos** que interagimos com os objetos. Para alimentar Sebastião, usamos o método `comer`. Para
_falar_ com ele, usamos o método `parlar`.

Assim como a grande a maioria das aves, papagaios podem voar, entretanto lêmures não podem, afinal sequer são aves.
Entretanto há atributos e métodos entre ambos que são semelhantes, mesmo que aplicados de formas diferentes.

Ambos os animais comem, bebem e dormem, além de que ambos possuem os atributos cor dos olhos, nome e tamanho dos olhos,
por exemplo.

Aqui podemos fazer uma **generalização**.

#### Generalização

Generalizar é aninhar em um único objeto características e métodos que façam sentido perante o contexto que estamos
lidando no nosso domínio.

No caso das imagens apresentadas nos exemplos (nosso domínio), podemos chegar a conclusão que há similaridades entre
nossos objetos (lêmure e papagaio). Essa conclusão deve ser respaldada pelo contexto, como se fosse uma _regra de
negócio_.

Sabe-se que tanto lêmures, quanto papagaios são animais, portanto podemos generalizar que **todo animal neste contexto**
possui:

- Atributos:
  - Nome
  - Cor dos olhos
  - Tamanho dos olhos
- Métodos:
  - Comer
  - Beber
  - Dormi

Isso nos permite distinguir, por exemplo, os métodos de cada objeto.

- Lêmure:
  - trinar
- Papagaio:
  - parlar

---

## Exercícios

### Lego

Considerando que você está situado no domínio de Lego, quais os atributos e métodos necessários para definir o objeto
Automóvel?

### Abrigo de animais

A bióloga Cheila precisa catalogar em um sistema os novos animais que chegaram no abrigo em que trabalha.

Ela precisa cadastrar os animais com suas características completas: espécie, tamanho, peso e demais características
essenciais. Vale lembrar que o abrigo recebe somente animais de pequeno porte.

O catálogo de animais resgatados deve ser classificado por classe animal (mamíferos, aves, répteis etc.). Além disso,
cada animal tem um número de identificação único.

Identifique os possíveis objetos com seus respectivos atributos e métodos.
