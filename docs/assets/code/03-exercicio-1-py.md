# Código do "Passo 3" em Python

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
