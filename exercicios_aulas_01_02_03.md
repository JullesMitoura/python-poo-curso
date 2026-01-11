# Exercícios - Aulas 01, 02 e 03
## Programação Orientada a Objetos

---

## **Aula 01 - Classes, Objetos e Atributos**

### Exercício 1
Crie uma classe chamada `Livro` com os atributos `titulo`, `autor` e `ano_publicacao`. Crie dois objetos dessa classe e exiba os atributos de cada um.

```python
# Sua resposta aqui
```

### Exercício 2
Crie uma classe chamada `Cachorro` com os atributos `nome`, `raca` e `idade`. Crie um método chamado `latir` que imprime uma mensagem contendo o nome do cachorro. Instancie um objeto e chame o método `latir`.

```python
# Sua resposta aqui
```

### Exercício 3
Crie uma classe chamada `ContaBancaria` com os atributos `numero`, `titular` e `saldo`. O saldo deve ser inicializado com 0. Crie um objeto dessa classe e exiba todas as informações.

```python
# Sua resposta aqui
```

---

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

## **Aula 03 - Atributos e Métodos de Classe**

### Exercício 9
Crie uma classe chamada `Pessoa` com:
- Um atributo de classe `total_pessoas` inicializado com 0
- Um construtor que recebe `nome` e `idade` e incrementa `total_pessoas`
- Um método de classe `quantidade_pessoas()` que retorna o total de pessoas criadas

Teste criando 3 objetos e verificando o total.

```python
# Sua resposta aqui
```

### Exercício 10
Crie uma classe chamada `Produto` com:
- Um atributo de classe `taxa_imposto` inicializado com 0.10 (10%)
- Um construtor que recebe `nome` e `preco`
- Um método de instância `preco_com_imposto()` que retorna o preço com imposto
- Um método de classe `atualizar_imposto(nova_taxa)` que atualiza a taxa de imposto

Teste criando produtos e alterando a taxa de imposto.

```python
# Sua resposta aqui
```

### Exercício 11
Crie uma classe chamada `Funcionario` com:
- Um atributo de classe `empresa` com valor "Empresa XYZ"
- Um atributo de classe `total_funcionarios` inicializado com 0
- Um construtor que recebe `nome` e `cargo`, e incrementa `total_funcionarios`
- Um método de classe `alterar_empresa(novo_nome)` que altera o nome da empresa
- Um método de instância `apresentar()` que imprime nome, cargo e empresa

```python
# Sua resposta aqui
```

### Exercício 12
Crie uma classe chamada `Estudante` com:
- Um atributo de classe `escola` com valor "Escola Python"
- Um atributo de classe `total_estudantes` inicializado com 0
- Um construtor que recebe `nome` e `matricula`, e incrementa `total_estudantes`
- Um método de classe `criar_por_matricula(cls, nome, ano_entrada, sequencial)` que cria um estudante onde a matrícula é no formato "ANO-SEQ" (ex: "2024-001")
- Um método de classe `quantidade_total()` que retorna o total de estudantes

```python
# Sua resposta aqui
```

### Exercício 13
Crie uma classe chamada `Animal` com:
- Um atributo de classe `total_animais` inicializado com 0
- Um atributo de classe `especie_default` com valor "Desconhecida"
- Um construtor que recebe `nome` e `especie` (com valor padrão None). Se especie for None, usa `especie_default`
- Um método de classe `atualizar_especie_default(nova_especie)` que altera a espécie padrão
- Um método de instância `informacoes()` que retorna uma string com nome e espécie

```python
# Sua resposta aqui
```

### Exercício 14
Crie uma classe chamada `Veiculo` com:
- Um atributo de classe `total_veiculos` inicializado com 0
- Um atributo de classe `limite_velocidade` com valor 120
- Um construtor que recebe `marca`, `modelo` e `velocidade_atual` (padrão 0)
- Um método de instância `acelerar(valor)` que aumenta a velocidade respeitando o limite
- Um método de classe `alterar_limite(novo_limite)` que altera o limite de velocidade
- Um método de classe `quantidade_veiculos()` que retorna o total

```python
# Sua resposta aqui
```

### Exercício 15 (Integração)
Crie uma classe chamada `Biblioteca` com:
- Um atributo de classe `nome_biblioteca` com valor "Biblioteca Central"
- Um atributo de classe `total_livros` inicializado com 0
- Um construtor que recebe `titulo`, `autor` e `isbn`, e incrementa `total_livros`
- Um atributo de instância `disponivel` inicializado como `True`
- Métodos de instância `emprestar()` e `devolver()` que alteram o estado de `disponivel`
- Um método de classe `alterar_nome_biblioteca(novo_nome)` que altera o nome da biblioteca
- Um método de classe `total_de_livros()` que retorna o total de livros cadastrados
- Um método de instância `informacoes()` que retorna uma string com todas as informações do livro

```python
# Sua resposta aqui
```

---

## **Respostas**

<details>
<summary>Clique para ver as respostas</summary>

### Resposta Exercício 1
```python
class Livro:
    def __init__(self, titulo, autor, ano_publicacao):
        self.titulo = titulo
        self.autor = autor
        self.ano_publicacao = ano_publicacao

livro1 = Livro("Dom Casmurro", "Machado de Assis", 1899)
livro2 = Livro("1984", "George Orwell", 1949)

print(f"Livro 1: {livro1.titulo}, {livro1.autor}, {livro1.ano_publicacao}")
print(f"Livro 2: {livro2.titulo}, {livro2.autor}, {livro2.ano_publicacao}")
```

### Resposta Exercício 2
```python
class Cachorro:
    def __init__(self, nome, raca, idade):
        self.nome = nome
        self.raca = raca
        self.idade = idade
    
    def latir(self):
        print(f"{self.nome} está latindo: Au au!")

cachorro1 = Cachorro("Rex", "Labrador", 3)
cachorro1.latir()
```

### Resposta Exercício 3
```python
class ContaBancaria:
    def __init__(self, numero, titular, saldo=0):
        self.numero = numero
        self.titular = titular
        self.saldo = saldo

conta1 = ContaBancaria("12345", "João Silva")
print(f"Conta: {conta1.numero}, Titular: {conta1.titular}, Saldo: R$ {conta1.saldo}")
```

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

### Resposta Exercício 9
```python
class Pessoa:
    total_pessoas = 0
    
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade
        Pessoa.total_pessoas += 1
    
    @classmethod
    def quantidade_pessoas(cls):
        return cls.total_pessoas

pessoa1 = Pessoa("João", 25)
pessoa2 = Pessoa("Maria", 30)
pessoa3 = Pessoa("Pedro", 28)

print(f"Total de pessoas: {Pessoa.quantidade_pessoas()}")
```

### Resposta Exercício 10
```python
class Produto:
    taxa_imposto = 0.10
    
    def __init__(self, nome, preco):
        self.nome = nome
        self.preco = preco
    
    def preco_com_imposto(self):
        return self.preco * (1 + self.taxa_imposto)
    
    @classmethod
    def atualizar_imposto(cls, nova_taxa):
        cls.taxa_imposto = nova_taxa

produto1 = Produto("Notebook", 3000.00)
produto2 = Produto("Mouse", 50.00)

print(f"Produto 1 com imposto: R$ {produto1.preco_com_imposto():.2f}")
Produto.atualizar_imposto(0.15)
print(f"Produto 1 com novo imposto: R$ {produto1.preco_com_imposto():.2f}")
```

### Resposta Exercício 11
```python
class Funcionario:
    empresa = "Empresa XYZ"
    total_funcionarios = 0
    
    def __init__(self, nome, cargo):
        self.nome = nome
        self.cargo = cargo
        Funcionario.total_funcionarios += 1
    
    @classmethod
    def alterar_empresa(cls, novo_nome):
        cls.empresa = novo_nome
    
    def apresentar(self):
        print(f"Nome: {self.nome}, Cargo: {self.cargo}, Empresa: {self.empresa}")

func1 = Funcionario("João", "Desenvolvedor")
func1.apresentar()
Funcionario.alterar_empresa("Empresa ABC")
func1.apresentar()
```

### Resposta Exercício 12
```python
class Estudante:
    escola = "Escola Python"
    total_estudantes = 0
    
    def __init__(self, nome, matricula):
        self.nome = nome
        self.matricula = matricula
        Estudante.total_estudantes += 1
    
    @classmethod
    def criar_por_matricula(cls, nome, ano_entrada, sequencial):
        matricula = f"{ano_entrada}-{sequencial:03d}"
        return cls(nome, matricula)
    
    @classmethod
    def quantidade_total(cls):
        return cls.total_estudantes

est1 = Estudante("Ana", "2024-001")
est2 = Estudante.criar_por_matricula("Pedro", 2024, 2)
est3 = Estudante.criar_por_matricula("Maria", 2024, 3)

print(f"Total de estudantes: {Estudante.quantidade_total()}")
```

### Resposta Exercício 13
```python
class Animal:
    total_animais = 0
    especie_default = "Desconhecida"
    
    def __init__(self, nome, especie=None):
        self.nome = nome
        if especie is None:
            self.especie = Animal.especie_default
        else:
            self.especie = especie
        Animal.total_animais += 1
    
    @classmethod
    def atualizar_especie_default(cls, nova_especie):
        cls.especie_default = nova_especie
    
    def informacoes(self):
        return f"Nome: {self.nome}, Espécie: {self.especie}"

animal1 = Animal("Rex")
print(animal1.informacoes())
Animal.atualizar_especie_default("Cachorro")
animal2 = Animal("Felix")
print(animal2.informacoes())
```

### Resposta Exercício 14
```python
class Veiculo:
    total_veiculos = 0
    limite_velocidade = 120
    
    def __init__(self, marca, modelo, velocidade_atual=0):
        self.marca = marca
        self.modelo = modelo
        self.velocidade_atual = velocidade_atual
        Veiculo.total_veiculos += 1
    
    def acelerar(self, valor):
        nova_velocidade = self.velocidade_atual + valor
        if nova_velocidade <= Veiculo.limite_velocidade:
            self.velocidade_atual = nova_velocidade
        else:
            self.velocidade_atual = Veiculo.limite_velocidade
    
    @classmethod
    def alterar_limite(cls, novo_limite):
        cls.limite_velocidade = novo_limite
    
    @classmethod
    def quantidade_veiculos(cls):
        return cls.total_veiculos

veiculo1 = Veiculo("Honda", "Civic")
veiculo1.acelerar(100)
print(f"Velocidade: {veiculo1.velocidade_atual}")
Veiculo.alterar_limite(150)
veiculo1.acelerar(60)
print(f"Velocidade: {veiculo1.velocidade_atual}")
```

### Resposta Exercício 15
```python
class Biblioteca:
    nome_biblioteca = "Biblioteca Central"
    total_livros = 0
    
    def __init__(self, titulo, autor, isbn):
        self.titulo = titulo
        self.autor = autor
        self.isbn = isbn
        self.disponivel = True
        Biblioteca.total_livros += 1
    
    def emprestar(self):
        if self.disponivel:
            self.disponivel = False
            print(f"Livro '{self.titulo}' emprestado.")
        else:
            print(f"Livro '{self.titulo}' já está emprestado.")
    
    def devolver(self):
        if not self.disponivel:
            self.disponivel = True
            print(f"Livro '{self.titulo}' devolvido.")
        else:
            print(f"Livro '{self.titulo}' já está disponível.")
    
    @classmethod
    def alterar_nome_biblioteca(cls, novo_nome):
        cls.nome_biblioteca = novo_nome
    
    @classmethod
    def total_de_livros(cls):
        return cls.total_livros
    
    def informacoes(self):
        status = "Disponível" if self.disponivel else "Emprestado"
        return f"Título: {self.titulo}, Autor: {self.autor}, ISBN: {self.isbn}, Status: {status}, Biblioteca: {self.nome_biblioteca}"

livro1 = Biblioteca("Dom Casmurro", "Machado de Assis", "978-85-359-0277-9")
livro2 = Biblioteca("1984", "George Orwell", "978-85-359-0278-6")

print(livro1.informacoes())
livro1.emprestar()
print(livro1.informacoes())
Biblioteca.alterar_nome_biblioteca("Biblioteca Municipal")
print(f"Total de livros: {Biblioteca.total_de_livros()}")
print(livro2.informacoes())
```

</details>

---

**Bons estudos!**
