<div align="center">

<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" width="80" height="80"/>

<h1>Programação Orientada a Objetos</h1>

<h3>PhD. Julles Mitoura</h3>

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/POO-4A90E2?style=for-the-badge&logoColor=white" alt="POO"/>
</p>

</div>

---

# Exercícios - Aula 07

## **Aula 07 - Polimorfismo e Abstração**

> Objetivo: conseguir **adicionar novas classes** sem mexer nas funções (`notificar`, `total_area`, `processar_pagamentos`).

### Exercício 1 — Notificações (polimorfismo por duck typing)
- Crie classes `Email`, `SMS` e `Push` com método `enviar(mensagem: str) -> str`.
- Crie uma função `notificar(canais, mensagem)` que percorre os canais e imprime o retorno de `enviar`.
- Adicione um novo canal `WhatsApp` sem alterar a função `notificar`.

```python
# Sua resposta aqui
```

### Exercício 2 — Cálculo de área (abstração com ABC)
- Crie uma classe abstrata `Forma` com método abstrato `area() -> float`.
- Implemente `Retangulo(largura, altura)` e `Circulo(raio)`.
- Escreva uma função `total_area(formas)` que soma as áreas.

```python
# Sua resposta aqui
```

### Exercício 3 — Pagamento (reforçando contrato)
- Crie `Boleto(Pagamento)` e implemente `pagar(valor)`.
- Garanta que valores inválidos (zero/negativo) gerem `ValueError`.

```python
# Sua resposta aqui
```

---

## **Respostas**

<details>
<summary>Clique para ver as respostas</summary>

### Resposta Exercício 1
```python
class Email:
    def __init__(self, destino):
        self.destino = destino

    def enviar(self, mensagem: str) -> str:
        return f"Email para {self.destino}: {mensagem}"


class SMS:
    def __init__(self, numero):
        self.numero = numero

    def enviar(self, mensagem: str) -> str:
        return f"SMS para {self.numero}: {mensagem}"


class Push:
    def __init__(self, app):
        self.app = app

    def enviar(self, mensagem: str) -> str:
        return f"Push ({self.app}): {mensagem}"


def notificar(canais, mensagem):
    for c in canais:
        print(c.enviar(mensagem))


# Novo canal adicionado sem alterar a função notificar (duck typing)
class WhatsApp:
    def __init__(self, contato):
        self.contato = contato

    def enviar(self, mensagem: str) -> str:
        return f"WhatsApp para {self.contato}: {mensagem}"


canais = [Email("ana@email.com"), SMS("+55 11 99999-0000"), Push("AppXYZ"), WhatsApp("Ana")]
notificar(canais, "Olá!")
```

### Resposta Exercício 2
```python
from abc import ABC, abstractmethod
from math import pi


class Forma(ABC):
    @abstractmethod
    def area(self) -> float:
        raise NotImplementedError


class Retangulo(Forma):
    def __init__(self, largura, altura):
        self.largura = float(largura)
        self.altura = float(altura)

    def area(self) -> float:
        return self.largura * self.altura


class Circulo(Forma):
    def __init__(self, raio):
        self.raio = float(raio)

    def area(self) -> float:
        return pi * (self.raio ** 2)


def total_area(formas):
    return sum(f.area() for f in formas)


formas = [Retangulo(3, 4), Circulo(1)]
print(total_area(formas))
```

### Resposta Exercício 3
```python
from abc import ABC, abstractmethod


class Pagamento(ABC):
    @abstractmethod
    def pagar(self, valor: float) -> str:
        raise NotImplementedError


class Boleto(Pagamento):
    def __init__(self, codigo_barras):
        self.codigo_barras = codigo_barras

    def pagar(self, valor: float) -> str:
        valor = float(valor)
        if valor <= 0:
            raise ValueError("valor inválido para pagamento")
        return f"Boleto {self.codigo_barras} pago no valor de R$ {valor:.2f}"


b = Boleto("34191.79001 01043.510047 91020.150008 8 12340000010000")
print(b.pagar(100))
```

</details>

---

**Bons estudos!**
