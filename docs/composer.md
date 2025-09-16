# Composer

## Índice

[⬅️ Voltar à página principal](../README.md)

- [Composer](#composer)
  - [Índice](#índice)
  - [O que é?](#o-que-é)
  - [Instalação](#instalação)
  - [Criando o projeto com composer init](#criando-o-projeto-com-composer-init)
  - [Instalando o que o projeto precisa com composer install](#instalando-o-que-o-projeto-precisa-com-composer-install)
  - [PSR-4: como funciona o autoload](#psr-4-como-funciona-o-autoload)
    - [Exemplo de estrutura + código com PSR-4:](#exemplo-de-estrutura--código-com-psr-4)

## O que é?

Composer é o gerenciador de dependências do PHP: ele lê um arquivo `composer.json` com informações do projeto e
baixa/organiza bibliotecas, além de gerar o autoloader para carregamento automático de classes.

Após instalar as bibliotecas, o Composer gera o `vendor/autoload.php`, que deve ser incluído no código para habilitar o
autoload das classes do projeto e de terceiros.

## Instalação

- Windows: use o instalador oficial ["Composer-Setup"](https://github.com/composer/windows-setup), que configura o
  executável e as variáveis de ambiente para uso no terminal.
- macOS/Linux: siga as instruções de instalação na página oficial
  ["Download Composer"](https://getcomposer.org/download/), podendo instalar localmente (composer.phar) ou globalmente
  (composer no PATH).
- Verificação: após instalar, rode `composer -V` ou `composer` no terminal para checar se o comando está disponível e
  funcionando.

## Criando o projeto com composer init

O comando `composer init` guia um assistente interativo que cria o arquivo composer.json do zero, perguntando nome do
pacote, descrição, licença e (se desejar) mapeamento de autoload. Esse arquivo é o "coração" do projeto para o Composer,
pois descreve metadados e como o autoload deve funcionar, mesmo que ainda não haja bibliotecas externas.

Exemplo do `composer.json` após o init, já com PSR-4 para código em `src/`:

```json
{
  "name": "meu-usuario/minha-aplicacao",
  "description": "Exemplo de projeto com Composer",
  "type": "project",
  "license": "MIT",
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

## Instalando o que o projeto precisa com composer install

O comando `composer install` lê o `composer.json` (e o `composer.lock`, se existir) e instala tudo o que o projeto
descreve, criando a pasta vendor e o autoloader.

Para usar as classes carregadas automaticamente, inclua o arquivo `vendor/autoload.php` no ponto de entrada da
aplicação, como index.php.

```php
<?php

require __DIR__ . '/vendor/autoload.php';

// Aqui já pode usar classes do projeto (PSR-4).
```

## PSR-4: como funciona o autoload

PSR-4 é a recomendação de como mapear nomes de classes (com namespace) para caminhos de arquivos, permitindo ao Composer
localizar e carregar a classe quando ela é usada.

No composer.json, a chave `autoload.psr-4` mapeia um prefixo de namespace para uma pasta, por exemplo, `"App\\": "src/"`
faz `App\Model\Livro` virar o arquivo `src/Model/Livro.php`.

### Exemplo de estrutura + código com PSR-4:

```
composer.json
src/
  Model/
    Livro.php
index.php
```

**src/Model/Livro.php**

```php
<?php

namespace App\Model;

class Livro {
    public function titulo(): string {
        return "1984";
    }
}
```

**index.php**

```php
<?php

require __DIR__ . '/vendor/autoload.php';

use App\Model\Livro;

$livro = new Livro();
echo $livro->titulo();
```

🚨 **Importante!** Atenção ao `\\` no prefixo do namespace e ao caminho relativo correto; o prefixo deve terminar com
barra invertida e nomes são sensíveis a maiúsculas/minúsculas.
