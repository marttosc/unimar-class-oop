# Princípio da Abstração

---

## Índice

[⬅️ Voltar à página principal](../README.md)

- [Princípio da Abstração](#princípio-da-abstração)
  - [Índice](#índice)
  - [O que é?](#o-que-é)
  - [Qual a sua importância?](#qual-a-sua-importância)
  - [Diferença com o Princípio da Herança](#diferença-com-o-princípio-da-herança)
  - [Exemplos](#exemplos)
    - [Exemplo em Python](#exemplo-em-python)
    - [Exemplo em PHP](#exemplo-em-php)

---

## O que é?

> Analisar observando um ou os muitos aspectos que estão contidos num todo; estudar separadamente suas particularidades
> ou características: abstraia os aspectos do todo.
>
> _Dicionário Online de Português._

A abstração auxilia para entender e compreender problemas considerados **complexos**. Diante disso, o problema complexo
é dividido (**abstraído**) em problemas menores até que uma solução seja encontrada.

Dentro do Princípio da Abstração, os objetos situados no **contexto complexo** são isolados e são representados somente
as características relevantes para o problema em si.

Exemplo: toda pessoa possui cor dos olhos e altura, porém no contexto de um sistema de folha de pagamento essas
informações se tornam **irrelevantes**.

Em suma, este princípio garante que as partes de um problema sejam ponderadas, ou seja, possuam um peso maior ou menor
em relação ao contexto.

Determinados detalhes podem ser ressaltados, enquanto outros são desconsiderados.

## Qual a sua importância?

Focar no que é relevante para o contexto garante **simplicidade** no desenvolvimento.

A **manutenção** torna-se mais fácil, uma vez que alterar uma classe abstrata modificará a herança de todas as suas
subclasses.

Garante o **reuso de código**, isto é, abstrações podem ser utilizadas em diversas partes do desenvolvimento.

## Diferença com o Princípio da Herança

A **abstração** foca em "esconder" os detalhes da implementação. É sobre **o que** o objeto deve fazer.

A **herança** foca em reutilizar código e criar relacionamentos hierárquicos entre classes. É sobre **como** implementar
as funcionalidades compartilhadas em uma hierarquia de classes.

Podemos afirmar o seguinte:

- Para a abstração existir, é necessário que haja subclasses que herdem desta classe abstrata, caso contrário ela será
  inútil.
- Toda classe que herda de outra, não necessariamente está herdando de uma classe abstrata.

## Exemplos

### Exemplo em Python

[Ver código completo aqui](assets/code/04-exemplo-py.md).

### Exemplo em PHP

[Ver código completo aqui](assets/code/04-exemplo-php.md).
