# Aula 00 - Apresentação

---

## Índice

[⬅️ Voltar à página principal](README.md)

- [Aula 00 - Apresentação](#aula-00---apresentação)
  - [Índice](#índice)
  - [Sobre mim](#sobre-mim)
    - [Formação](#formação)
    - [Contato](#contato)
  - [Plano de ensino](#plano-de-ensino)
  - [Formato das aulas](#formato-das-aulas)
  - [Avaliação](#avaliação)
  - [Revisão](#revisão)
    - [Código 1](#código-1)
    - [Código 2](#código-2)
    - [Código 3](#código-3)
    - [Código 4](#código-4)

---

## Sobre mim

### Formação

**Prof. Me. Gustavo Marttos.**

- Bacharel em Sistemas de Informação pelo Centro Universitário Eurípides de Marília (Univem), 2018.
- Mestre em Ciência da Informação pela Universidade Estadual Paulista "Júlio de Mesquita Filho" (Unesp), 2020.

### Contato

Você pode me contatar por [e-mail](mailto:gustavomarttos@unimar.br) (preferencial) ou via Moodle.

Também estou no [LinkedIn](https://www.linkedin.com/in/marttosc/).

---

## Plano de ensino

| **Conteúdo**                          | **Carga horária** |
| ------------------------------------- | :---------------: |
| Apresentação e revisão                |      4 horas      |
| Fundamentos de POO                    |     12 horas      |
| Objetos, classes, atributos e métodos |     16 horas      |
| Herança e abstração                   |     16 horas      |
| Encapsulamento e polimorfismo         |     16 horas      |
| Interfaces                            |      8 horas      |
| Avaliações\*                          |      8 horas      |

> _\* A carga horária envolvida para avaliações engloba as duas regimentais (P1 e P2)._

---

## Formato das aulas

- Aula expositiva.
- Exposição de problemas.
- Listas de exercícios.
- Projeto de desenvolvimento de software.

---

## Avaliação

A avaliação consiste em duas notas semestrais, ambas com o valor de zero a dez.

- A **P1** ocorrerá entre 22/09 a 30/09/2025 (projeto parcial).
- A **P2** ocorrerá entre 24/11 a 03/12/2025 (projeto final).

Você estará de exame, se:

$$
4 \leq \frac{\text{P1} + \text{P2}}{2} < 7
$$

Uma vez de exame, o critério para aprovação passa a ser:

$$
\left( \frac{\text{P1} + \text{P2}}{2} + \text{NotaExame} \right) \geq 10
$$

---

## Revisão

O que os códigos abaixem fazem?

### Código 1

Em Python:

```python
n1 = int(input("Digite a nota 1: "))
n2 = int(input("Digite a nota 2: "))

media = (n1 + n2) / 2

print(f"Sua média é {media:.2f}.")
```

Em PHP:

```php
<?php
$n1 = (int) readline("Digite a nota 1: ");
$n2 = (int) readline("Digite a nota 2: ");

$media = ($n1 + $n2) / 2;

echo "Sua média é " . number_format($media, 2) . ".\n";
?>
```

### Código 2

Em Python:

```python
# Aproveitando o código anterior, onde
# n1 = 6, n2 = 8, portanto media = ?

if media >= 7:
    print("Aprovado")
elif media >= 4:
    print("Exame")
else:
    print("Reprovado")
```

Em PHP:

```php
<?php
// Aproveitando o código anterior, onde
// $n1 = 6, $n2 = 8, portanto $media = ?

if ($media >= 7) {
    echo "Aprovado\n";
} elseif ($media >= 4) {
    echo "Exame\n";
} else {
    echo "Reprovado\n";
}
?>
```

### Código 3

Em Python:

```python
nomes = ["João", "Neide", "Carlos", "Micalatéia"]

for nome in nomes:
    mensagem = f"Olá, {nome}!"
    if nome == "Micalatéia":
        mensagem = f"Hmm, {nome}!"
    print(mensagem)
```

Em PHP:

```php
<?php
$nomes = ["João", "Neide", "Carlos", "Micalatéia"];

foreach ($nomes as $nome) {
    $mensagem = "Olá, $nome!";
    if ($nome === "Micalatéia") {
        $mensagem = "Hmm, $nome!";
    }
    echo $mensagem . "\n";
}
?>
```

### Código 4

Em Python:

```python
msg = "Digite um número ou 'q' para sair."

while True:
    num_input = input(msg)
    if num_input.lower().strip() == "q":
        break
    eh_par = int(num_input) % 2 == 0
    print(f"O número {num_input} é par? {eh_par}")
```

Em PHP:

```php
<?php
$msg = "Digite um número ou 'q' para sair.";

while (true) {
    $num_input = readline($msg);
    if (strtolower(trim($num_input)) === "q") {
        break;
    }
    $eh_par = ((int) $num_input) % 2 === 0;
    echo "O número $num_input é par? " . ($eh_par ? "True" : "False") . "\n";
}
?>
```
