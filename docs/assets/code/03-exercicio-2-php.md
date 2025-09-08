# Código do "Passo 4" em PHP

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
