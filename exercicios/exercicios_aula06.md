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

# Exercícios - Aula 06

## **Aula 06 - Herança e Reutilização de Código**

### Exercício 1 — Modelando contas (herança + override + `super()`)
Crie uma classe base `ContaBancaria` com:
- atributos `titular` (str) e `saldo` (float)
- método `depositar(valor)`
- método `sacar(valor)` (não permitir sacar mais do que o saldo)

Crie duas subclasses:
- `ContaCorrente`: ao sacar, cobra uma taxa fixa `taxa_saque` (ex.: 2.50). Dica: sobrescreva `sacar()` e use `super()`.
- `ContaPoupanca`: tenha um método `render(juros)` que aumenta o saldo (ex.: juros 0.01 = 1%).

```python
# Sua resposta aqui
```

### Exercício 2 — Polimorfismo
Escreva uma função `resumo(contas)` que receba uma lista contendo `ContaCorrente` e `ContaPoupanca` (misturadas) e imprima `titular` e `saldo` de cada uma.

```python
# Sua resposta aqui
```

### Exercício 3 — `isinstance`/`issubclass`
- Verifique se um objeto de `ContaCorrente` é instância de `ContaBancaria`.
- Verifique se `ContaPoupanca` é subclasse de `ContaBancaria`.

```python
# Sua resposta aqui
```

---

## **Respostas**

<details>
<summary>Clique para ver as respostas</summary>

### Resposta Exercício 1
```python
class ContaBancaria:
    def __init__(self, titular, saldo=0.0):
        self.titular = titular
        self.saldo = float(saldo)

    def depositar(self, valor):
        if valor <= 0:
            raise ValueError("valor de depósito deve ser positivo")
        self.saldo += valor

    def sacar(self, valor):
        if valor <= 0:
            raise ValueError("valor de saque deve ser positivo")
        if valor > self.saldo:
            raise ValueError("saldo insuficiente")
        self.saldo -= valor


class ContaCorrente(ContaBancaria):
    def __init__(self, titular, saldo=0.0, taxa_saque=2.50):
        super().__init__(titular, saldo)
        self.taxa_saque = float(taxa_saque)

    def sacar(self, valor):
        # cobra taxa junto com o saque
        return super().sacar(valor + self.taxa_saque)


class ContaPoupanca(ContaBancaria):
    def render(self, juros):
        if juros < 0:
            raise ValueError("juros não pode ser negativo")
        self.saldo *= (1 + juros)

cc = ContaCorrente("Ana", saldo=100, taxa_saque=2.5)
cc.depositar(50)
cc.sacar(10)  # desconta 10 + 2.5
print(f"{cc.titular}: R$ {cc.saldo:.2f}")

cp = ContaPoupanca("Bruno", saldo=200)
cp.render(0.10)  # 10%
print(f"{cp.titular}: R$ {cp.saldo:.2f}")
```

### Resposta Exercício 2
```python
class ContaBancaria:
    def __init__(self, titular, saldo=0.0):
        self.titular = titular
        self.saldo = float(saldo)

    def depositar(self, valor):
        if valor <= 0:
            raise ValueError("valor de depósito deve ser positivo")
        self.saldo += valor

    def sacar(self, valor):
        if valor <= 0:
            raise ValueError("valor de saque deve ser positivo")
        if valor > self.saldo:
            raise ValueError("saldo insuficiente")
        self.saldo -= valor


class ContaCorrente(ContaBancaria):
    def __init__(self, titular, saldo=0.0, taxa_saque=2.50):
        super().__init__(titular, saldo)
        self.taxa_saque = float(taxa_saque)

    def sacar(self, valor):
        return super().sacar(valor + self.taxa_saque)


class ContaPoupanca(ContaBancaria):
    def render(self, juros):
        if juros < 0:
            raise ValueError("juros não pode ser negativo")
        self.saldo *= (1 + juros)


def resumo(contas):
    for c in contas:
        print(f"{c.titular}: R$ {c.saldo:.2f}")


cc = ContaCorrente("Ana", saldo=100, taxa_saque=2.5)
cp = ContaPoupanca("Bruno", saldo=200)
cp.render(0.05)
resumo([cc, cp])
```

### Resposta Exercício 3
```python
class ContaBancaria:
    def __init__(self, titular, saldo=0.0):
        self.titular = titular
        self.saldo = float(saldo)


class ContaCorrente(ContaBancaria):
    pass


class ContaPoupanca(ContaBancaria):
    pass


cc = ContaCorrente("Ana", saldo=100)

print(isinstance(cc, ContaBancaria))            # True
print(issubclass(ContaPoupanca, ContaBancaria)) # True
```

</details>

---

**Bons estudos!**
