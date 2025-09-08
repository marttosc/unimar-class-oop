# Código do "Passo 4" em Python

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
