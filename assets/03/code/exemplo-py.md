# Exemplo de código com Herança em Python

[⬅️ Voltar para a página de Herança](../../../03-heranca.md)

```python
"""Considere que toda conta bancária deve ter um titular e um saldo, além de permitir depósito.
Por sua vez, a conta corrente, que É UMA conta bancária, permite receber Pix e por
convenção do Banco Central ela deve possibilitar a exibição do titular e do saldo.
"""


class Pessoa:
    def __init__(self, nome: str, cpf: str):
        self._nome = nome.strip().capitalize()
        self._cpf = cpf

    @property
    def nome(self) -> str:
        return self._nome

    @nome.setter
    def nome(self, nome: str):
        if isinstance(nome, str) and nome:
            self._nome = nome.strip().capitalize()
        else:
            raise ValueError("Nome inválido")

    @property
    def cpf(self) -> str:
        return self._cpf

    @cpf.setter
    def cpf(self, *args):
        raise AttributeError("O CPF não pode ser modificado")


class ContaBancaria:  # superclasse
    def __init__(self, titular: Pessoa, saldo: float = 0.0):
        self._titular = titular
        self._saldo = saldo

    @property
    def titular(self) -> Pessoa:
        return self._titular

    @property
    def saldo(self) -> float:
        return self._saldo

    def _tem_saldo(self, valor: float) -> bool:
        return 0 < valor <= self.saldo

    def _debitar_valor(self, valor: float):
        if self._tem_saldo(valor):
            self._saldo -= valor
        else:
            raise ValueError("Saldo insuficiente")

    def _creditar_valor(self, valor: float):
        if valor > 0:
            self._saldo += valor
        else:
            raise ValueError("Valor inválido")

    def depositar(self, valor: float):
        self._creditar_valor(valor)

    def sacar(self, valor: float):
        self._debitar_valor(valor)


class ContaCorrente(ContaBancaria):  # subclasse
    def transferir(self, valor: float, conta_destino: ContaBancaria):
        if self._tem_saldo(valor):
            self._debitar_valor(valor)  # Faz o débito na conta de origem.
            conta_destino.depositar(valor)  # Faz o crédito na conta de destino.
        else:
            raise ValueError("Valor de transferência inválido")

    def exibir_titular(self):
        print(f"Titular: {self.titular.nome}")
        print(f"CPF: {self.titular.cpf}")

    def exibir_saldo(self):
        print(f"Saldo atual: R$ {self.saldo:.2f}")


joao = Pessoa("João da Silva", "12345678900")
conta_joao = ContaCorrente(titular=joao, saldo=1000)

conta_joao.exibir_titular()
conta_joao.exibir_saldo()

maria = Pessoa("Maria Oliveira", "98765432100")
conta_maria = ContaCorrente(titular=maria, saldo=500)

conta_maria.exibir_titular()
conta_maria.exibir_saldo()

# Transferindo R$ 200 da conta do João para a conta da Maria
conta_joao.transferir(200, conta_maria)

# Exibindo saldos após a transferência.
# João deve ter R$ 800,00 e Maria deve ter R$ 700,00.
conta_joao.exibir_saldo()
conta_maria.exibir_saldo()
```
