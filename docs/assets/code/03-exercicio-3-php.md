# Código do "Passo 5" em PHP

[⬅️ Voltar para a página de Herança](../../03-heranca.md)

```php
$livro1 = new Livro("O Senhor dos Anéis", 1954, "J.R.R. Tolkien", 1216, "Allen & Unwin");
$livro2 = new Livro("1984", 1949, "George Orwell", 328, "Secker & Warburg");

echo $livro1->exibirDetalhes() . "\n";
echo $livro2->mostrarResumo() . "\n";

$revista1 = new Revista("National Geographic", 2020, "Vários", 1, "Ciência");
$revista2 = new Revista("Time", 2021, "Vários", 2, "Notícias");

echo $revista1->exibirDetalhes() . "\n";
echo $revista2->mostrarArtigoPrincipal() . "\n";

$jornal1 = new Jornal("The New York Times", 2021, "Vários", 1, "Internacional");
$jornal2 = new Jornal("The Guardian", 2021, "Vários", 2, "Nacional");

echo $jornal1->exibirDetalhes() . "\n";
echo $jornal2->mostrarManchete() . "\n";
```
