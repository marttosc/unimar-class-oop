# Código do "Passo 6" em Python

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
