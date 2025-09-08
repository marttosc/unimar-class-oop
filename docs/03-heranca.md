# Princípio da Herança

Este arquivo aborda o conceito de **herança**, explicando sua analogia com a biologia e destacando sua importância para
a reutilização de código e especialização de classes.

São apresentados exemplos práticos, a diferença entre superclasse e subclasse, além das distinções entre herança simples
e múltipla, incluindo o problema do diamante.

O texto enfatiza como a herança contribui para a integridade, consistência e manutenção dos sistemas orientados a
objetos.

<p align="right">
    <em>O resumo acima foi gerado por IA.</em>
</p>

---

## Índice

[⬅️ Voltar à página principal](../README.md)

- [Princípio da Herança](#princípio-da-herança)
  - [Índice](#índice)
  - [O que é?](#o-que-é)
  - [Superclasse e subclasse](#superclasse-e-subclasse)
  - [Herança simples e herança múltipla](#herança-simples-e-herança-múltipla)
  - [Qual a sua importância?](#qual-a-sua-importância)
  - [Exemplos](#exemplos)
    - [Exemplo em Python](#exemplo-em-python)
    - [Exemplo em PHP](#exemplo-em-php)
  - [Exercício](#exercício)
    - [Passo 1: interpretação e identificação](#passo-1-interpretação-e-identificação)
    - [Passo 2: resolução do primeiro requisito](#passo-2-resolução-do-primeiro-requisito)
    - [Passo 3: resolução do segundo requisito](#passo-3-resolução-do-segundo-requisito)
      - [Em Python](#em-python)
      - [Em PHP](#em-php)
    - [Passo 4: resolução do terceiro requisito](#passo-4-resolução-do-terceiro-requisito)
      - [Em Python](#em-python-1)
      - [Em PHP](#em-php-1)
    - [Passo 5: resolução do quarto requisito](#passo-5-resolução-do-quarto-requisito)
      - [Em Python](#em-python-2)
      - [Em PHP](#em-php-2)
    - [Passo 6: resolução do quinta (e último) requisito](#passo-6-resolução-do-quinta-e-último-requisito)
      - [Em Python](#em-python-3)
      - [Em PHP](#em-php-3)
  - [Mais exercícios](#mais-exercícios)
    - [Instruções](#instruções)
    - [Exercício 1](#exercício-1)
    - [Exercício 2](#exercício-2)

---

## O que é?

Na biologia, um filho (Y) **herda** as características genéticas dos pais (X) e, posteriormente, repassa as suas
características (Y) e as dos seus pais (X) para seu filho (Z).

Dentro da POO, esse princípio funciona da mesma forma, permitindo **expandir** e **especializar** (ou evoluir)
determinada característica ou comportamento.

> Faz-se uso da semântica "é um" para determinar a cardinalidade de herança.

- O Mamífero possui pêlos e pode amamentar.
- O Primata, que **é um** Mamífero, possui mãos e pés, além de ser inteligente.
- O Ser Humano, que **é um** Primata, consegue andar ereto e pensar.

Portanto:

> O Ser Humano **é um** Primata, bem como **é um** Mamífero.
>
> Ele possui pêlos, mãos e pés, amamenta, é inteligente, anda ereto e pensa.

No contexto semântico, a preposição inversa também ocorre, porém por meio da expressão "pode ser".

> Considerando a semântica anterior, pode-se dizer que o inverso ocorre por meio da expressão a seguir:
>
> Um Mamífero **pode ser** um Ser Humano.

<p align="center" style="background: #ffffff;">
    <img src="assets/image/03-herancasemantica.png" alt="Estrutura semântica da herança">
</p>

---

Herança, na prática, significa a possibilidade de construir objetos especializados que herdam as características de
objetos mais generalistas (olha a generalização aparecendo aqui novamente, vide [aula 01](01-fundamentos.md)).

Trata-se de um mecanismo fundamental de **reutilização de código**, permitindo que novas classes mais específicas
aproveitem os atributos e métodos de classes já existentes, herdando assim os recursos da classe hierarquicamente
superior e adicionando suas próprias particularidades.

Quanto aos sistemas reais, podemos trazer sobre os sistemas de área da saúde, como a hierarquia dos agentes envolvidos:

- Pessoas
  - Empregados
    - Médicos
    - Enfermeiros
  - Terceirizados
    - Biomédicos
  - Pacientes
    - Paciente particular
    - Paciente conveniado
    - Paciente público (SUS)

Observe como a estrutura formada se assemelha a uma árvore. A sua raiz, portanto, é o que dá origem a todos os demais
agentes envolvidos em um sistema de saúde. Com isso, duas afirmações podem ser feitas:

1. Cada agente herda as características dos seus antecessores.
2. "Pessoas" é uma classe hierarquicamente superior e que dela são herdadas características para a formação de novas
   classes, como Empregados e Pacientes.

---

## Superclasse e subclasse

Partindo da premissa de que tudo é objeto e considerando a hierarquia vista acima, podemos afirmar que Pessoa é uma
superclasse e que Empregados é uma subclasse de Pessoa.

A herança normalmente resulta em subclasses mais especializadas e específicas do que suas respectivas superclasses.

É importante observar que o prefixo "sub" no termo "subclasse" pode gerar um equívoco, sugerindo erroneamente que ela
possua menos recursos que a superclasse.

Na realidade, ocorre exatamente o oposto: uma subclasse herda todos os atributos e métodos da superclasse e ainda pode
adicionar suas próprias características particulares, tornando-se assim mais completa e especializada do que a classe da
qual deriva.

> 🚨 **Importante!** Se você não entendeu a questão semântica, volte lá e leia até entender.

## Herança simples e herança múltipla

Diferente de algumas leis da natureza, onde a herança ocorre quando um objeto herda características de uma superclasse
(**herança simples**), a **herança múltipla** possibilita a um objeto herdar as características de mais uma superclasse.

A **herança múltipla** é um tema controverso, pois pode gerar situações intrincadas e, por vezes, confusas. O ponto
central da discussão reside no fato de que as **subclasses** são naturalmente mais especializadas que suas respectivas
**superclasses**. Assim, herdar características muito específicas de múltiplas classes pode resultar em maior
complexidade do que benefícios práticos.

Embora a herança ofereça um poder considerável na programação orientada a objetos, é importante lembrar que outras
abordagens, como **agregação** e **composição**, também são ferramentas poderosas e podem ser mais adequadas em
determinados contextos.

Um dos problemas clássicos de **ambiguidade e complexidade** associados à herança múltipla é o **problema do diamante**:

<p align="center">
    <img src="assets/image/03-herancadiamante.png" alt="Problema do Diamante" style="width: 50%; height: auto;">
</p>

As classes B e C herdam de A, ou seja, são mais especializadas. Destas duas subclasses é gerada uma nova classe, D, que
herda de B e C. Estranho, mas é possível.

> **Pergunta-se:** se chamamos um método em D, conhecido em A por herança, de onde virá esta herança, de A ou de B?

## Qual a sua importância?

O princípio da Herança garante **reuso de código** e **maior integridade e consistência** das funcionalidades
implementadas.

Quando o comportamento de um método é alterado, todas as classes que a herdam terão seu comportamento igualmente
alterado.

## Exemplos

### Exemplo em Python

[Ver código completo aqui](assets/code/03-exemplo-py.md).

### Exemplo em PHP

[Ver código completo aqui](assets/code/03-exemplo-php.md).

## Exercício

Você foi contratado para modelar um sistema simples de gestão de uma biblioteca. O sistema precisa lidar com diferentes
tipos de materiais, como livros, revistas e jornais. Cada material tem características próprias, mas também compartilham
alguns atributos em comum.

1. Identifique pelo menos 3 atributos e 2 métodos comuns a todos os materiais da biblioteca.
2. Defina uma superclasse, incluindo os atributos e métodos comuns.
3. Crie 3 subclasses. Defina 2 atributos específicos e 1 método específico.
4. Crie 2 instâncias de cada subclasse.
5. Como seriam as definições das classes, se a biblioteca passasse a aceitar e-books?

---

<details>

<summary><em>Resolução do exercício</em></summary>

> Se você abriu essa sessão, assume-se que ao menos você tentou resolver o exercício. 🧐
>
> Se não tentou, então quem perde é somente você. ¯\\\_(ツ)\_/¯

### Passo 1: interpretação e identificação

_Você foi contratado para modelar um sistema simples de `gestão de uma biblioteca [1]`. O sistema precisa lidar com
diferentes tipos de `materiais [2]`, como `livros, revistas e jornais [3]`. Cada material tem
`características próprias [4]`, mas também `compartilham alguns atributos em comum [5]`._

Com base nas seleções, temos:

1. O contexto do problema.
2. O que há de genérico, portanto possibilita a herança.
3. O que há de específico, portanto temos as subclasses.
4. O que caracteriza o que é genérico.
5. O que caracteriza o que é específico.

---

### Passo 2: resolução do primeiro requisito

_Identifique pelo menos 3 atributos e 2 métodos comuns a todos os materiais da biblioteca._

A biblioteca possui livros, revistas e jornais como **materiais**. O que esses três têm de características (atributos)
em comum? Quais métodos têm em comum?

Lembre-se de responder pensando no **contexto**.

> **Pergunte-se**: será que um livro, uma revista ou um jornal pode ser lido ou folheado nesse sistema?
>
> Se a resposta for não, então não é um método válido.
>
> _Entretanto, para fins didáticos, permitiremos que isto ocorra nesse exercício._

Livros, revistas e jornais possuem em comum os atributos `título`, `ano de publicação` e `autor/editor`. Essas
características criam um **Material**.

Com um **Material** é possível: `emprestar`, `devolver`, `exibir detalhes`.

---

### Passo 3: resolução do segundo requisito

_Defina uma superclasse, incluindo os atributos e métodos comuns._

Qual classe pode ser criada com base nos atributos e métodos comuns? Por que?

Como objeto, `Material` não pode se tornar concreto (instância), pois é sabido que há outros que dependem dessa classe,
como Livro, Revista e Jornal, **além de que** o sistema não faria uso de uma instância (materialização) somente de
Material.

Justamente por permitir somente a definição, Material é uma superclasse.

#### Em Python

<details>

<summary>Expandir/Retrair código</summary>

```python
class Material:
    def __init__(self, titulo: str, ano_publicacao: int, autor: str):
        self._titulo = titulo
        self._ano_publicacao = ano_publicacao
        self._autor = autor

    @property
    def titulo(self) -> str:
        return self._titulo

    @property
    def ano_publicacao(self) -> int:
        return self._ano_publicacao

    @property
    def autor(self) -> str:
        return self._autor

    def emprestar(self, quantidade_dias: int) -> None:
        # Precisa implementar o restante.
        pass

    def devolver(self) -> None:
        # Precisa implementar o restante.
        pass

    def exibir_detalhes(self) -> str:
        detalhes = f"Título: {self.titulo}\n"
        detalhes += f"Autor: {self.autor}\n"
        detalhes += f"Ano de publicação: {self.ano_publicacao}\n"

        return detalhes
```

</details>

#### Em PHP

<details>

<summary>Expandir/Retrair código</summary>

```php
class Material {
    private string $titulo;
    private int $anoPublicacao;
    private string $autor;

    public function __construct(string $titulo, int $anoPublicacao, string $autor) {
        $this->setTitulo($titulo);
        $this->setAnoPublicacao($anoPublicacao);
        $this->setAutor($autor);
    }

    public function getTitulo(): string {
        return $this->titulo;
    }

    protected function setTitulo(string $titulo): void {
        $this->titulo = $titulo;
    }

    public function getAnoPublicacao(): int {
        return $this->anoPublicacao;
    }

    protected function setAnoPublicacao(int $anoPublicacao): void {
        $this->anoPublicacao = $anoPublicacao;
    }

    public function getAutor(): string {
        return $this->autor;
    }

    protected function setAutor(string $autor): void {
        $this->autor = $autor;
    }

    public function emprestar(int $quantidadeDias): void {
        // Precisa implementar o restante.
    }

    public function devolver(): void {
        // Precisa implementar o restante.
    }

    public function exibirDetalhes(): string {
        $detalhes = "Título: $this->titulo\n";
        $detalhes .= "Autor: $this->autor\n";
        $detalhes .= "Ano de publicação: $this->anoPublicacao\n";

        return $detalhes;
    }
}
```

</details>

---

### Passo 4: resolução do terceiro requisito

_Crie 3 subclasses. Defina 2 atributos específicos e 1 método específico._

Sabendo que Material é a superclasse, quais seriam as subclasses? Quais atributos e métodos específicos podem ser
criados?

O que Livro tem de específico? O que é possível fazer de específico com o Livro? E a Revista? E o Jornal?

- Livro
  - Atributos
    - número de páginas (inteiro)
    - editora (string)
  - Métodos
    - mostrar resumo
- Revista
  - Atributos
    - edição (inteiro)
    - tema (string)
  - Métodos
    - mostrar artigo principal
- Jornal
  - Atributos
    - data de publicação (string, y-m-d)
    - seção (string)
  - Métodos
    - mostrar manchete

#### Em Python

<details>

<summary>Expandir/Retrair código</summary>

```python
class Livro(Material):
    def __init__(self, titulo: str, ano_publicacao: int, autor: str, numero_paginas: int, editora: str):
        # Inicializa os atributos da superclasse.
        super().__init__(titulo, ano_publicacao, autor)

        # Inicializa os atributos específicos do livro.
        self._numero_paginas = numero_paginas
        self._editora = editora

    @property
    def numero_paginas(self) -> int:
        return self._numero_paginas

    @property
    def editora(self) -> str:
        return self._editora

    def exibir_detalhes(self) -> str:
        # Exibe os detalhes iniciais do material.
        detalhes = super().exibir_detalhes()

        # Adiciona informações específicas do livro.
        detalhes += f"Número de páginas: {self.numero_paginas}\n"
        detalhes += f"Editora: {self.editora}\n"

        return detalhes

    def mostrar_resumo(self) -> str:
        # Mostra um resumo do livro.
        return f"{self.titulo} - {self.autor} ({self.ano_publicacao})"


class Revista(Material):
    def __init__(self, titulo: str, ano_publicacao: int, autor: str, numero_edicao: int, tema: str):
        # Inicializa os atributos da superclasse.
        super().__init__(titulo, ano_publicacao, autor)

        # Inicializa os atributos da revista.
        self._numero_edicao = numero_edicao
        self._tema = tema

    @property
    def numero_edicao(self) -> int:
        return self._numero_edicao

    @property
    def tema(self) -> str:
        return self._tema

    def exibir_detalhes(self) -> str:
        # Exibe os detalhes iniciais do material.
        detalhes = super().exibir_detalhes()

        # Adiciona informações específicas da revista.
        detalhes += f"Número da edição: {self.numero_edicao}\n"
        detalhes += f"Tema: {self.tema}\n"

        return detalhes

    def mostrar_artigo_principal(self) -> str:
        # Mostra o artigo principal da revista.
        return f"Artigo Principal: {self.titulo} - {self.autor} ({self.ano_publicacao})"


class Jornal(Material):
    def __init__(self, titulo: str, ano_publicacao: int, autor: str, secao: str, data_publicacao: str):
        # Inicializa os atributos da superclasse.
        super().__init__(titulo, ano_publicacao, autor)

        # Inicializa os atributos específicos do jornal.
        self._secao = secao
        self._data_publicacao = data_publicacao

    @property
    def secao(self) -> str:
        return self._secao

    @property
    def data_publicacao(self) -> str:
        return self._data_publicacao

    def exibir_detalhes(self) -> str:
        # Exibe os detalhes iniciais do material.
        detalhes = super().exibir_detalhes()

        # Adiciona informações específicas do jornal.
        detalhes += f"Seção: {self.secao}\n"
        detalhes += f"Data de publicação: {self.data_publicacao}\n"

        return detalhes

    def mostrar_manchete(self) -> str:
        # Mostra a manchete do jornal.
        return f"Manchete: {self.titulo} - {self.autor} ({self.ano_publicacao})"
```

</details>

#### Em PHP

<details>

<summary>Expandir/Retrair código</summary>

```php
class Livro extends Material
{
    private int $numeroPaginas;
    private string $editora;

    public function __construct(string $titulo, int $anoPublicacao, string $autor, int $numeroPaginas, string $editora)
    {
        # Chama o construtor da superclasse.
        parent::__construct($titulo, $anoPublicacao, $autor);

        # Define os atributos específicos da subclasse.
        $this->setNumeroPaginas($numeroPaginas);
        $this->setEditora($editora);
    }

    public function getNumeroPaginas(): int
    {
        return $this->numeroPaginas;
    }

    protected function setNumeroPaginas(int $numeroPaginas): void
    {
        $this->numeroPaginas = $numeroPaginas;
    }

    public function getEditora(): string
    {
        return $this->editora;
    }

    protected function setEditora(string $editora): void
    {
        $this->editora = $editora;
    }

    public function exibirDetalhes(): string
    {
        # Obtém os detalhes da superclasse.
        $detalhes = parent::exibirDetalhes();

        # Adiciona os detalhes específicos do livro.
        $detalhes .= "Número de páginas: $this->numeroPaginas\n";
        $detalhes .= "Editora: $this->editora\n";

        return $detalhes;
    }

    public function mostrarResumo(): string
    {
        // Precisa implementar o restante.
        return "";
    }
}


class Revista extends Material {
    private int $edicao;
    private string $tema;

    public function __construct(string $titulo, int $anoPublicacao, string $autor, int $edicao, string $tema)
    {
        parent::__construct($titulo, $anoPublicacao, $autor);
        $this->setEdicao($edicao);
        $this->setTema($tema);
    }

    public function getEdicao(): int
    {
        return $this->edicao;
    }

    protected function setEdicao(int $edicao): void
    {
        $this->edicao = $edicao;
    }

    public function getTema(): string
    {
        return $this->tema;
    }

    protected function setTema(string $tema): void
    {
        $this->tema = $tema;
    }

    public function exibirDetalhes(): string
    {
        $detalhes = parent::exibirDetalhes();
        $detalhes .= "Edição: $this->edicao\n";
        $detalhes .= "Tema: $this->tema\n";

        return $detalhes;
    }

    public function mostrarArtigoPrincipal(): string
    {
        // Precisa implementar o restante.
        return "";
    }
}


class Jornal extends Material
{
    private string $dataPublicacao;
    private string $secao;

    public function __construct(string $titulo, int $anoPublicacao, string $autor, string $dataPublicacao, string $secao)
    {
        parent::__construct($titulo, $anoPublicacao, $autor);
        $this->setDataPublicacao($dataPublicacao);
        $this->setSecao($secao);
    }

    public function getDataPublicacao(): string
    {
        return $this->dataPublicacao;
    }

    protected function setDataPublicacao(string $dataPublicacao): void
    {
        $this->dataPublicacao = $dataPublicacao;
    }

    public function getSecao(): string
    {
        return $this->secao;
    }

    protected function setSecao(string $secao): void
    {
        $this->secao = $secao;
    }

    public function exibirDetalhes(): string
    {
        $detalhes = parent::exibirDetalhes();
        $detalhes .= "Data de publicação: $this->dataPublicacao\n";
        $detalhes .= "Seção: $this->secao\n";

        return $detalhes;
    }

    public function mostrarManchete(): string
    {
        // Precisa implementar o restante.
        return "";
    }
}
```

</details>

---

### Passo 5: resolução do quarto requisito

_Crie 2 instâncias de cada subclasse._

No contexto apresentado, as classes mais próximas da realidade são Livro, Revista e Jornal, portanto elas são as classes
concretas.

A instância é o que **representará o objeto da vida real**, ou seja, é necessário criar instâncias que armazenem dados
reais.

#### Em Python

<details>

<summary>Expandir/Retrair código</summary>

```python
livro1 = Livro("O Senhor dos Anéis", 1954, "J.R.R. Tolkien", 1216, "Allen & Unwin")
livro2 = Livro("1984", 1949, "George Orwell", 328, "Secker & Warburg")

print(livro1.exibir_detalhes())
print(livro2.mostrar_resumo())

revista1 = Revista("National Geographic", 2020, "Vários", 1, "Ciência")
revista2 = Revista("Time", 2021, "Vários", 2, "Notícias")

print(revista1.exibir_detalhes())
print(revista2.mostrar_artigo_principal())

jornal1 = Jornal("The New York Times", 2021, "Vários", 1, "Internacional")
jornal2 = Jornal("The Guardian", 2021, "Vários", 2, "Nacional")

print(jornal1.exibir_detalhes())
print(jornal2.mostrar_manchete())
```

</details>

#### Em PHP

<details>

<summary>Expandir/Retrair código</summary>

```php
$livro1 = new Livro("O Senhor dos Anéis", 1954, "J.R.R. Tolkien", 1216, "Allen & Unwin");
$livro2 = new Livro("1984", 1949, "George Orwell", 328, "Secker & Warburg");

echo $livro1->exibirDetalhes() . "\n";
echo $livro2->mostrarResumo() . "\n";

$revista1 = new Revista("National Geographic", 2020, "Vários", 1, "Ciência");
$revista2 = new Revista("Time", 2021, "Vários", 2, "Notícias");

echo $revista1->exibirDetalhes() . "\n";
echo $revista2->mostrarArtigoPrincipal() . "\n";

$jornal1 = new Jornal("The New York Times", 2021, "Vários", 1, "Internacional");
$jornal2 = new Jornal("The Guardian", 2021, "Vários", 2, "Nacional");

echo $jornal1->exibirDetalhes() . "\n";
echo $jornal2->mostrarManchete() . "\n";
```

</details>

---

### Passo 6: resolução do quinta (e último) requisito

_Como seriam as definições das classes, se a biblioteca passasse a aceitar e-books?_

O que é um e-book? O que mudaria na modelagem de classes criada?

Um e-book é um livro digital e pode ser disponibilizado no **formato** PDF, ePub ou Mobi. O **tamanho do arquivo** em Kb
também é importante.

#### Em Python

<details>

<summary>Expandir/Retrair código</summary>

```python
class Ebook(Material):
    def __init__(self, titulo: str, ano_publicacao: int, autor: str, tamanho_arquivo: int, formato: str):
        super().__init__(titulo, ano_publicacao, autor)
        self.tamanho_arquivo = tamanho_arquivo
        self.formato = formato

    def exibir_detalhes(self) -> str:
        detalhes = super().exibir_detalhes()
        detalhes += f"Tamanho do arquivo: {self.tamanho_arquivo}Kb, Formato: {self.formato}"
        return detalhes

    def baixar(self) -> str:
        return f"Baixando eBook '{self.titulo}' de {self.autor}."


ebook1 = Ebook("Harry Potter e a Pedra Filosofal", 1997, "J.K. Rowling", 500, "PDF")
print(ebook1.baixar())
```

</details>

#### Em PHP

<details>

<summary>Expandir/Retrair código</summary>

```php
class Ebook extends Material
{
    private int $tamanhoArquivoKb;
    private string $formato;

    public function __construct(string $titulo, int $anoPublicacao, string $autor, int $tamanhoArquivoKb, string $formato)
    {
        parent::__construct($titulo, $anoPublicacao, $autor);
        $this->setTamanhoArquivoKb($tamanhoArquivoKb);
        $this->setFormato($formato);
    }

    public function getTamanhoArquivoKb(): int
    {
        return $this->tamanhoArquivoKb;
    }

    protected function setTamanhoArquivoKb(int $tamanhoArquivoKb): void
    {
        $this->tamanhoArquivoKb = $tamanhoArquivoKb;
    }

    public function getFormato(): string
    {
        return $this->formato;
    }

    protected function setFormato(string $formato): void
    {
        $this->formato = $formato;
    }

    public function exibirDetalhes(): string
    {
        $detalhes = parent::exibirDetalhes();
        $detalhes .= "Tamanho do arquivo: $this->tamanhoArquivoKb Kb\n";
        $detalhes .= "Formato: $this->formato\n";

        return $detalhes;
    }

    public function baixar(): string
    {
        return "Baixando eBook: $this->titulo\n";
    }
}

$ebook1 = new Ebook("Harry Potter e a Pedra Filosofal", 1997, "J.K. Rowling", 1024, "PDF");
echo $ebook1->baixar();
```

</details>

</details>

---

## Mais exercícios

### Instruções

Para cada exercício a seguir faça a modelagem de classes seguindo estas instruções:

1. Identifique pelo menos 4 atributos e 3 métodos comuns.
2. Defina uma superclasse, incluindo os atributos e métodos comuns.
3. Crie as subclasses. Defina 3 atributos específicos e 2 métodos específicos.
4. Crie 4 instâncias para cada subclasse.
5. Não se esqueça de tipificar os atributos.

### Exercício 1

Você trabalha em uma grande empresa de locação de veículos. Nesta empresa são locados desde motos, carros e até
caminhões.

Desenvolva uma modelagem de classes que permita reservar os veículos sem burocracia.

### Exercício 2

Uma empresa possui diversos cargos de funcionários, como gerente, desenvolvedor e estagiário e o RH precisa acessar o
cadastro dos funcionários.

O salário do gerente é 6 vezes maior do que um estagiário e 4 vezes maior do que um desenvolvedor, enquanto o
desenvolvedor ganha 3x mais que o estagiário.

Crie a modelagem de dados necessária para esse cenário.
