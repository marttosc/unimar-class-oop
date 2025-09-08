# Código do "Passo 6" em PHP

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
