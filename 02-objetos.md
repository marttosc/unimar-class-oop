# Objetos, classes, atributos e métodos

Este arquivo aborda os conceitos fundamentais da programação orientada a objetos, incluindo a definição de objetos,
classes, atributos, métodos, instâncias, construtores e modificadores de visibilidade.

Explica como modelar classes a partir de exemplos do cotidiano, como cachorros, gatos e livros, destacando a importância
do contexto na definição de atributos e métodos.

O material também apresenta convenções de nomenclatura nas linguanges Python e PHP e exemplifica a implementação prática
desses conceitos, mostrando como criar e instanciar classes, além de utilizar construtores e controlar o acesso a
atributos e métodos por meio de modificadores de visibilidade.

<p align="right">
    <em>O resumo acima foi gerado por IA.</em>
</p>

---

## Índice

[⬅️ Voltar à página principal](README.md)

- [Objetos, classes, atributos e métodos](#objetos-classes-atributos-e-métodos)
  - [Índice](#índice)
  - [Tudo e todos são objetos, inclusive vocês.](#tudo-e-todos-são-objetos-inclusive-vocês)
  - [Classes](#classes)
    - [Cachorros](#cachorros)
    - [Gatos](#gatos)
    - [O que há em comum?](#o-que-há-em-comum)
  - [Instâncias (de objetos)](#instâncias-de-objetos)
  - [Boas práticas](#boas-práticas)
    - [Convenções sintáticas na programação](#convenções-sintáticas-na-programação)
  - [Para morrer de certeza...](#para-morrer-de-certeza)
    - [Sobre atributos](#sobre-atributos)
    - [Sobre instâncias](#sobre-instâncias)
  - [Construtores](#construtores)
  - [Modificadores de visibilidade](#modificadores-de-visibilidade)
  - [O que é o `this` (ou `self`) e como ele funciona?](#o-que-é-o-this-ou-self-e-como-ele-funciona)

---

## Tudo e todos são objetos, inclusive vocês.

<p align="center">
    <img src="assets/02/img/batman.gif" alt="Batman pensando">
</p>

Fica o questionamento: como trazer esses conceitos para a computação?

Leia sobre a aula 01 para dar sequência a este material.

---

## Classes

Uma **classe (ou tipo)** é a definição do que se tornará um **objeto**. Trata-se de uma representação, portanto não é
concreta\*. Ela serve como um molde contendo todos os atributos e métodos a respeito daquela representação.

É com o uso de classes que ocorre toda a ênfase acerca do paradigma de orientação a objetos.

> _\* Não confundir o conceito de classe com o conceito de abstração, tópico a ser discutido adiante. Aqui nos referimos
> a algo que de fato não existe no mundo real (não é materializado), pois é somente conceitual._

### Cachorros

Observe nas imagens a seguir, respectivamente: **Olegário, o cane corso**, e **Carlito, o caramelo**.

<p align="center">
    <img src="assets/02/img/canecorso.jpg" alt="Olegário, o cane corso" height="250" style="display:inline-block; margin-right:20px; object-fit:contain;">
    <img src="assets/02/img/caramelo.jpg" alt="Carlito, o caramelo" height="250" style="display:inline-block; object-fit:contain;">
</p>

Olegário e Carlito são **objetos** da classe **Cachorro**. Possuem os mesmos métodos, afinal eles são inerentes à
classe, porém os valores para seus atributos são **diferentes**.

Até a existência dos objetos dos cachorros, a classe Cachorro representava apenas uma ideia, uma concepção do que pode
ser um cachorro.

### Gatos

Agora observe **Vanusa** e **Maico**, os gatos, respectivamente.

<p align="center">
    <img src="assets/02/img/gatoheterocromia.jpeg" alt="Vanusa, a gata" height="250" style="display:inline-block; margin-right:20px; object-fit:contain;">
    <img src="assets/02/img/gatolaranja.jpg" alt="Maico, o gato" height="250" style="display:inline-block; object-fit:contain;">
</p>

Vanusa e Maico são **objetos** da classe **Gato**. Possuem os mesmos métodos, afinal eles são inerentes à classe, porém
os valores para seus atributos são **diferentes**.

Até a existência dos objetos dos gatos, a classe Gato representava apenas uma ideia, uma concepção do que pode ser um
gato.

### O que há em comum?

Cachorros possuem os atributos _nome, nascimento, peso, comprimento do corpo, raça, cor do pelo, comprimento do pelo,
cor dos olhos_.

Gatos possuem os mesmos atributos, portanto temos **atributos em comum** (lembram da generalização?).

Cachorros possuem os métodos _dormir, acordar, comer, brincar e **latir**_.

Gatos, por sua vez, possuem os métodos _dormir, acordar, comer, brincar, **miar e ignorar uma pessoa**_.

---

_Dormir, acordar, comer e brincar_ são métodos **comuns** entre as classes Cachorro e Gato. No caso do cachorro,
`latir`, e `miar` e `ignorar uma pessoa` para o gato são **métodos específicos** de cada classe.

Quando existem propriedades em comum entre classes, podemos fazer uso da generalização e aplicar o conceito de
**superclasse (ou classe-mãe)** e **subclasse (ou classe-filha)**.

> Aqui começamos a ver o princípio de Herança sendo aplicado também.

- Superclasse **Mamífero**
  - Atributos:
    - nome
    - nascimento
    - peso
    - comprimento do corpo
    - raça
    - cor do pelo
    - comprimento do pelo
    - cor dos olhos
  - Métodos:
    - dormir
    - acordar
    - comer
    - brincar
  - Subclasses:
    - Classe **Cachorro**:
      - Métodos:
        - latir
    - Clase **Gato**:
      - Atibutos:
        - comprimento das garras
      - Métodos:
        - miar
        - ignorar uma pessoa

A classe Mamífero define a maioria dos atributos e métodos, pois são comuns a todas as subclasses. A declaração desses
atributos e métodos nas subclasses não é necessária, uma vez que a superclasse já os definiu.

Entretanto, a classe **Cachorro** possui o método específico `latir`, bem como a classe **Gato** possui o atributo
`comprimento das garras` e os métodos `miar` e `ignorar uma pessoa`.

## Instâncias (de objetos)

Instanciar é criar algo concreto. Quando um objeto passa a existir, ou seja, passa a ser concreto (materializado), o
chamamos de **instância (de objeto)**.

Dentro do paradigma, uma instância é armazenada dentro de uma variável em memória.

As sentenças `"instância de objeto X"`, `"instância da classe X"` ou `"instância é do tipo X"` são comuns nesse
contexto.

> Portanto, pode-se dizer:
>
> - Olegário e Carlito são instâncias da classe (ou do tipo) **Cachorro**.
> - Vanusa e Maico são instâncias da classe (ou do tipo) **Gato**.

---

## Boas práticas

Como já vimos, **atributos** caracterizam a natureza de uma **classe**, enquanto os **métodos** são responsáveis pelas
ações que são feitas.

Por convenção, usa-se **verbos no infinitivo** para definir o nome do método.

Dentro de uma biblioteca (este é o nosso contexto neste exemplo), um Livro pode ser detalhado (`detalhar`), emprestado
(`emprestar`), devolvido (`devolver`), reservado (`reservar`) etc.

Cada palavra (verbo) destacado acima é um **método válido** para a classe Livro.

É necessário estar ciente do **contexto** que será trabalhado, pois isso impactará diretamente na **modelagem das
classes**, ou seja, na definição de atributos e métodos.

Por exemplo, no **contexto de uma biblioteca universitária**, um Livro pode ser emprestado (`emprestar`), devolvido
(`devolver`) e reservado (`reservar`).

Porém, no **contexto de uma livraria**, um Livro **não** teria essas mesmas ações, mas sim ser vendido (`vender`), ter
seu preço exibido (`exibir preço`) etc.

### Convenções sintáticas na programação

Ao escrever classes, atributos e métodos é importante seguirmos convenções sintáticas para manter o código organizado e
legível:

- **Classes**: Devem ser nomeadas usando o padrão **PascalCase** (cada palavra começa com letra maiúscula, sem espaços
  ou sublinhados). Exemplo: `Livro`, `ContaBancaria`, `AlunoUniversitario`.

- **Atributos e métodos**:

  - Em linguagens como Java, JavaScript e C#, utiliza-se o padrão **camelCase** (a primeira palavra começa com letra
    minúscula e as demais com maiúscula).
    - Exemplo de atributo: `dataNascimento`
    - Exemplo de método: `emprestarLivro()`
  - Em Python, o padrão é **snake_case** (todas as letras minúsculas, palavras separadas por sublinhado).
    - Exemplo de atributo: `data_nascimento`
    - Exemplo de método: `emprestar_livro()`

- **Métodos**: Devem sempre começar com um **verbo no infinitivo**, indicando a ação que realizam. Exemplos:
  `detalharLivro()`, `reservarLivro()`, `devolver_livro()`

Em Python:

```python
class Passaro:
    def __init__(self, cor_penas: str):
        self.cor_penas = cor_penas

    def cantar(self) -> None:
        print("O pássaro está cantando.")
```

Em PHP:

```php
class Passaro {
    private string $corPenas;

    public function __construct(string $corPenas) {
        $this->corPenas = $corPenas;
    }

    public function cantar(): void {
        echo "O pássaro está cantando.";
    }
}
```

---

## Para morrer de certeza...

🚨 Como o contexto impacta na modelagem de classes?

### Sobre atributos

Pra você, o que é um Livro? Quais são as características desse Livro?

Podemos considerar o que segue abaixo:

- **Título**, o nome do livro;
- **Autor(es)**, o(s) nome(s) do(s) autor(es) que escreveu(ram) o livro;
- **ISBN**, código internacional de identificação única;
- **Editora**, a qual publicou o livro;
- **Ano de publicação**, o ano em que o livro foi lançado;
- **Número de páginas**, a quantidade de páginas do livro;
- **Gênero**, o gênero literário ao qual pertence o livro;
- etc.

Havendo os atributos definidos, torna-se necessário tipificá-los, ou seja, definir o tipo do dado daquele atributo. Como
você tipificaria os atributos?

Leia sobre
[Type declarations no PHP](https://www.php.net/manual/en/language.oop5.properties.php#language.oop5.properties.typed-properties)
ou sobre a [PEP 484 no Python](https://peps.python.org/pep-0484/).

---

Em Python:

```python
class Livro:
    titulo: str
    autores: list[str]
    isbn: str
    editora: str
    ano_publicacao: int
    num_paginas: int
    genero: str
```

Em PHP:

```php
class Livro {
    public string $titulo;
    public array $autores;
    public string $isbn;
    public string $editora;
    public int $anoPublicacao;
    public int $numPaginas;
    public string $genero;
}
```

### Sobre instâncias

Usando o contexto de Livro acima, vamos criar instâncias (ou seja, materializá-las) para facilitar a compreensão. Para
criar uma instância da classe `Livro`, você precisa fornecer valores para seus atributos.

Usaremos o livro **1984** de George Orwell como exemplo.

Em **Python**:

```python
livro_1984 = Livro()
livro_1984.titulo = "1984"
livro_1984.autores = ["George Orwell"]
livro_1984.isbn = "978-0451524935"
livro_1984.editora = "Signet Classic"
livro_1984.ano_publicacao = 1950
livro_1984.num_paginas = 328
livro_1984.genero = "Distopia"
```

No exemplo acima, criamos uma variável chamada `livro_1984` que armazena a instância da classe `Livro`. Em Python, basta
chamar o nome da classe seguido de parênteses para criar uma nova instância.

Em **PHP**:

```php
$livro1984 = new Livro();
$livro1984->titulo = "1984";
$livro1984->autores = ["George Orwell"];
$livro1984->isbn = "978-0451524935";
$livro1984->editora = "Signet Classic";
$livro1984->anoPublicacao = 1950;
$livro1984->numPaginas = 328;
$livro1984->genero = "Distopia";
```

No PHP, usamos a palavra-chave `new` para criar uma nova instância da classe. O operador `->` (chamado de "rocket" ou
"seta") é utilizado para acessar os atributos e métodos do objeto instanciado.

## Construtores

Trata-se de um método especial de uma classe que define como uma instância (objeto) é criada. Ele normalmente serve para
inicializar os atributos da classe ao instante da sua materialização.

Em Python, o construtor se chama `__init__`.

```python
class Livro:
    def __init__(self, titulo: str, autor: str):
        self.titulo = titulo
        self.autor = autor

livro1 = Livro("1984", "George Orwell")
```

Em PHP, se chama `__construct`.

```php
class Livro {
    public string $titulo;
    public string $autor;

    public function __construct(string $titulo, string $autor) {
        $this->titulo = $titulo;
        $this->autor = $autor;
    }
}

$livro1 = new Livro("1984", "George Orwell");
```

## Modificadores de visibilidade

Dentro do paradigma de orientação a objetos, os **acessores** (também chamados de **níveis de acesso** ou
**modificadores de visibilidade**) determinam a maneira como atributos e métodos de uma classe podem ser acessados ou
modificados por outras partes do código.

- `public`: O atributo ou método pode ser acessado de qualquer lugar - tanto dentro da classe quanto fora dela,
  inclusive por outras classes.
- `protected`: O acesso é permitido apenas dentro da própria classe e pelas suas subclasses (classes que herdam da
  classe principal).
- `private`: O atributo ou método só pode ser acessado dentro da própria classe, ficando oculto de qualquer outra classe
  ou instância.

Python não possui palavras reservadas (`public`, `protected`, `private`) para controle de acesso, mas existe uma
convenção:

- Público: atributo ou método sem prefixo.
- Protegido: prefixo `_atributo` (underscore simples).
- Privado: prefixo `__atributo` (underscore duplo).

```python
class ContaBancaria:
    def __init__(self, titular: str, saldo: float):
        self.titular = titular         # público
        self._saldo = saldo            # protegido
        self.__senha = "1234"          # privado

    def mostrar_saldo(self):           # público
        print(f"Saldo: {self._saldo}")

    def __mostrar_senha(self):         # privado
        print(f"Senha: {self.__senha}")

```

Entretanto, no PHP há suporte oficial para os três modificadores de acesso.

```php
class ContaBancaria {
    public string $titular;    // público
    protected float $saldo;    // protegido
    private string $senha;     // privado

    public function __construct(string $titular, float $saldo) {
        $this->titular = $titular;
        $this->saldo = $saldo;
        $this->senha = "1234";
    }

    public function mostrarSaldo(): void {
        echo "Saldo: $this->saldo";
    }

    private function mostrarSenha(): void {
        echo "Senha: $this->senha";
    }
}
```

## O que é o `this` (ou `self`) e como ele funciona?

O `this` refere-se ao **objeto atual**, ou seja, à instância da classe que está executando o determinado método. Ele é
necessário para acessar os atributos e métodos pertencentes àquele objeto específico.

- Em Python, utiliza-se `self` (palavra reservada para indicar o objeto corrente dentro dos métodos).
- Em PHP, utiliza-se `$this` (precedido pelo operador seta -> para acessar atributos ou métodos).

Em Python:

```python
class Cachorro:
    def __init__(self, nome: str):
        self.nome = nome

    def latir(self) -> None:
        print(f"{self.nome} está latindo!")  # self.nome se refere ao nome do objeto específico

dog = Cachorro("Olegário")
dog.latir()     # Olegário está latindo!
```

Em PHP:

```php
class Cachorro {
    public string $nome;

    public function __construct(string $nome) {
        $this->nome = $nome;
    }

    public function latir(): void {
        echo "$this->nome está latindo!";
    }
}

$dog = new Cachorro("Olegário");
$dog->latir();  // Olegário está latindo!
```
