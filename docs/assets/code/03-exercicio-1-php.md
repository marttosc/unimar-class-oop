# Código do "Passo 3" em PHP

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
