# Exemplo de código com Abstração em PHP

[⬅️ Voltar para a página de Abstração](../../04-abstracao.md)

```php
abstract class ContaBancaria
{
    public function exibirSaldo(): void
    {
        echo "mostrar o saldo da conta corrente\n";
    }

    // Método abstrato sacar
    abstract public function sacar(float $valor): void;
}

class ContaCorrente extends ContaBancaria
{
    public function sacar(float $valor): void
    {
        echo "R$ " . number_format($valor, 2, ',', '.') . " serão sacados da conta corrente.\n";
    }
}

class ContaPagamento extends ContaBancaria
{
    public function sacar(float $valor): void
    {
        echo "R$ " . number_format($valor, 2, ',', '.') . " serão sacados da conta pagamento.\n";
    }
}

// Descomente a linha abaixo para testar o erro de instanciação de classe abstrata
// $contaBancaria = new ContaBancaria();

$contaCorrente = new ContaCorrente();
$contaCorrente->exibirSaldo();
$contaCorrente->sacar(100);

$contaPagamento = new ContaPagamento();
$contaPagamento->exibirSaldo();
$contaPagamento->sacar(300);
``
```
