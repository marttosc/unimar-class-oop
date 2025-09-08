# Código do "Passo 5" em Python

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

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
