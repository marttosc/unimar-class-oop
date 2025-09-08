# Exemplo de código com Herança em PHP

[⬅️ Voltar para a página de Herança](../../../03-heranca.md)

```php
<?php

/**
 * Considere que toda conta bancária deve ter um titular e um saldo, além de permitir depósito.
 * Por sua vez, a conta corrente, que É UMA conta bancária, permite receber Pix e por
 * convenção do Banco Central ela deve possibilitar a exibição do titular e do saldo.
 */

class Pessoa
{
    private string $nome;
    private string $cpf;

    public function __construct(string $nome, string $cpf)
    {
        $this->setNome($nome);
        $this->setCpf($cpf);
    }

    public function getNome(): string
    {
        return $this->nome;
    }

    public function setNome(string $nome): void
    {
        // Remove espaços em branco do início e do fim.
        $nome = trim($nome);

        // Verifica se o nome não está vazio.
        if (!empty($nome)) {
            // Capitaliza o primeiro caractere e transforma o restante em minúsculas.
            $this->nome = ucfirst(strtolower($nome));
        } else {
            // Lança uma exceção se o nome for inválido.
            throw new InvalidArgumentException("Nome inválido");
        }
    }

    public function getCpf(): string
    {
        return $this->cpf;
    }

    private function setCpf(string $cpf): void
    {
        // Remove espaços em branco do início e do fim.
        $cpf = trim($cpf);

        // Verifica se o CPF não está vazio e possui 11 caracteres.
        if (!empty($cpf) && strlen($cpf) === 11) {
            $this->cpf = $cpf;
        } else {
            throw new InvalidArgumentException("CPF inválido");
        }
    }
}

class ContaBancaria
{
    protected Pessoa $titular;
    protected float $saldo;

    public function __construct(Pessoa $titular, float $saldo = 0.0)
    {
        $this->titular = $titular;
        $this->saldo = $saldo;
    }

    public function getTitular(): Pessoa
    {
        return $this->titular;
    }

    public function getSaldo(): float
    {
        return $this->saldo;
    }

    protected function temSaldo(float $valor): bool
    {
        // Verifica se o valor está dentro dos limites permitidos.
        return $valor > 0 && $valor <= $this->saldo;
    }

    protected function debitarValor(float $valor): void
    {
        if ($this->temSaldo($valor)) {
            $this->saldo -= $valor;
        } else {
            throw new Exception("Saldo insuficiente");
        }
    }

    protected function creditarValor(float $valor): void
    {
        if ($valor > 0) {
            $this->saldo += $valor;
        } else {
            throw new Exception("Valor inválido");
        }
    }

    public function depositar(float $valor): void
    {
        $this->creditarValor($valor);
    }

    public function sacar(float $valor): void
    {
        $this->debitarValor($valor);
    }
}

class ContaCorrente extends ContaBancaria
{
    public function transferir(float $valor, ContaBancaria $contaDestino): void
    {
        if ($this->temSaldo($valor)) {
            $this->debitarValor($valor);
            $contaDestino->depositar($valor);
        } else {
            throw new Exception("Valor de transferência inválido");
        }
    }

    public function exibirTitular(): void
    {
        echo "Titular: " . $this->titular->getNome() . "\n";
        echo "CPF: " . $this->titular->getCpf() . "\n";
    }

    public function exibirSaldo(): void
    {
        echo "Saldo atual: R$ " . number_format($this->saldo, 2, ',', '.') . "\n";
    }
}

// Exemplo de uso:
$joao = new Pessoa("João da Silva", "12345678900");
$contaJoao = new ContaCorrente($joao, 1000);

$contaJoao->exibirTitular();
$contaJoao->exibirSaldo();

$maria = new Pessoa("Maria Oliveira", "98765432100");
$contaMaria = new ContaCorrente($maria, 500);

$contaMaria->exibirTitular();
$contaMaria->exibirSaldo();

// Transferindo R$ 200 da conta do João para a conta da Maria
$contaJoao->transferir(200, $contaMaria);

// Exibindo saldos após a transferência.
$contaJoao->exibirSaldo(); // João deve ter R$ 800,00
$contaMaria->exibirSaldo(); // Maria deve ter R$ 700,00
```
