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

# Exercícios - Aula 02

## **Aula 02 - Métodos, Construtores e Estado**

### Exercício 4
Crie uma classe chamada `Lampada` com um atributo `ligada` (inicializado como `False` no construtor). Crie os métodos `ligar()` e `desligar()` que alteram o estado da lâmpada e imprimem uma mensagem informando o novo estado.

```python
# Sua resposta aqui
```

### Exercício 5
Crie uma classe chamada `Calculadora` com um método `somar` que recebe dois números e retorna a soma. Crie também os métodos `subtrair`, `multiplicar` e `dividir`. Teste todos os métodos.

```python
# Sua resposta aqui
```

### Exercício 6
Crie uma classe chamada `Carro` com os atributos `marca`, `modelo` e `velocidade` (inicializada com 0). Crie os métodos:
- `acelerar(valor)`: aumenta a velocidade
- `frear(valor)`: diminui a velocidade (não pode ficar negativa)
- `obter_velocidade()`: retorna a velocidade atual

```python
# Sua resposta aqui
```

### Exercício 7
Crie uma classe chamada `Aluno` com os atributos `nome`, `matricula` e `notas` (uma lista). Crie um método `adicionar_nota(nota)` que adiciona uma nota à lista. Crie também um método `calcular_media()` que retorna a média das notas.

```python
# Sua resposta aqui
```

### Exercício 8
Crie uma classe chamada `ContaCorrente` com os atributos `numero`, `titular` e `saldo` (inicializado com um valor padrão de 0). Crie os métodos:
- `depositar(valor)`: adiciona valor ao saldo
- `sacar(valor)`: subtrai valor do saldo (não permite saldo negativo)
- `consultar_saldo()`: retorna o saldo atual

```python
# Sua resposta aqui
```

---

## **Respostas**

<details>
<summary>Clique para ver as respostas</summary>

### Resposta Exercício 4
```python
class Lampada:
    def __init__(self):
        self.ligada = False
    
    def ligar(self):
        self.ligada = True
        print("Lâmpada ligada!")
    
    def desligar(self):
        self.ligada = False
        print("Lâmpada desligada!")

lampada1 = Lampada()
lampada1.ligar()
lampada1.desligar()
```

### Resposta Exercício 5
```python
class Calculadora:
    def somar(self, a, b):
        return a + b
    
    def subtrair(self, a, b):
        return a - b
    
    def multiplicar(self, a, b):
        return a * b
    
    def dividir(self, a, b):
        if b != 0:
            return a / b
        else:
            return "Erro: divisão por zero"

calc = Calculadora()
print(calc.somar(10, 5))
print(calc.subtrair(10, 5))
print(calc.multiplicar(10, 5))
print(calc.dividir(10, 5))
```

### Resposta Exercício 6
```python
class Carro:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo
        self.velocidade = 0
    
    def acelerar(self, valor):
        self.velocidade += valor
    
    def frear(self, valor):
        self.velocidade -= valor
        if self.velocidade < 0:
            self.velocidade = 0
    
    def obter_velocidade(self):
        return self.velocidade

carro1 = Carro("Toyota", "Corolla")
carro1.acelerar(50)
print(carro1.obter_velocidade())
carro1.frear(20)
print(carro1.obter_velocidade())
```

### Resposta Exercício 7
```python
class Aluno:
    def __init__(self, nome, matricula):
        self.nome = nome
        self.matricula = matricula
        self.notas = []
    
    def adicionar_nota(self, nota):
        self.notas.append(nota)
    
    def calcular_media(self):
        if len(self.notas) == 0:
            return 0
        return sum(self.notas) / len(self.notas)

aluno1 = Aluno("Maria", "2024001")
aluno1.adicionar_nota(8.5)
aluno1.adicionar_nota(9.0)
aluno1.adicionar_nota(7.5)
print(f"Média: {aluno1.calcular_media():.2f}")
```

### Resposta Exercício 8
```python
class ContaCorrente:
    def __init__(self, numero, titular, saldo=0):
        self.numero = numero
        self.titular = titular
        self.saldo = saldo
    
    def depositar(self, valor):
        self.saldo += valor
    
    def sacar(self, valor):
        if self.saldo >= valor:
            self.saldo -= valor
        else:
            print("Saldo insuficiente!")
    
    def consultar_saldo(self):
        return self.saldo

conta1 = ContaCorrente("001", "Ana")
conta1.depositar(1000)
conta1.sacar(300)
print(f"Saldo: R$ {conta1.consultar_saldo()}")
```

</details>

---

**Bons estudos!**
