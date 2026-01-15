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

# Exercícios - Aula 05

## **Aula 05 - Associação, Agregação e Composição**

### Exercício 1 — Associação por parâmetro
Crie as classes `Professor` e `Disciplina`. Faça um método `ministrar(disciplina)` em `Professor` que imprime o nome do professor e o nome da disciplina.

```python
# Sua resposta aqui
```

### Exercício 2 — Associação por atributo
Crie as classes `Curso` e `Aluno` onde `Aluno` recebe um `Curso` no construtor e guarda em um atributo. Crie um método `apresentar()` que mostra aluno e curso.

```python
# Sua resposta aqui
```

### Exercício 3 — Agregação (todo-parte fraca)
Crie as classes `Departamento` e `Funcionario` com as operações:
- `Departamento.adicionar(funcionario)`
- `Departamento.remover(funcionario)`
- `Departamento.listar()`

Depois demonstre que um `Funcionario` pode ser removido de um departamento e adicionado em outro (a “parte” continua existindo).

```python
# Sua resposta aqui
```

### Exercício 4 — Composição (todo-parte forte)
Crie as classes `Pedido` e `ItemPedido` onde:
- `Pedido` **cria** `ItemPedido` internamente via método `adicionar_item(nome, quantidade, preco_unitario)`
- `ItemPedido` possui método `subtotal()`
- `Pedido.total()` soma os subtotais
- `Pedido.resumo()` imprime os itens e o total

```python
# Sua resposta aqui
```

### Exercício 5 — Comparando os relacionamentos
Crie um pequeno texto (3–8 linhas) explicando, com suas palavras, a diferença entre:
- associação
- agregação
- composição

Inclua **1 exemplo** de cada (pode ser usando as classes dos exercícios anteriores).

```python
# Sua resposta aqui (pode ser texto em comentário)
```

---

## **Respostas**

<details>
<summary>Clique para ver as respostas</summary>

### Resposta Exercício 1
```python
class Disciplina:
    def __init__(self, nome):
        self.nome = nome


class Professor:
    def __init__(self, nome):
        self.nome = nome

    def ministrar(self, disciplina):
        print(f"Professor {self.nome} está ministrando {disciplina.nome}")


prof = Professor("Julles")
poo = Disciplina("POO")
prof.ministrar(poo)
```

### Resposta Exercício 2
```python
class Curso:
    def __init__(self, nome):
        self.nome = nome


class Aluno:
    def __init__(self, nome, matricula, curso):
        self.nome = nome
        self.matricula = matricula
        self.curso = curso  # associação por atributo

    def apresentar(self):
        print(f"Aluno: {self.nome} ({self.matricula}) - Curso: {self.curso.nome}")


curso = Curso("Engenharia de Software")
aluno = Aluno("Ana", "2024-001", curso)
aluno.apresentar()
```

### Resposta Exercício 3
```python
class Funcionario:
    def __init__(self, nome, cargo):
        self.nome = nome
        self.cargo = cargo

    def __repr__(self):
        return f"{self.nome} ({self.cargo})"


class Departamento:
    def __init__(self, nome):
        self.nome = nome
        self.funcionarios = []  # agregação: "parte" pode viver fora

    def adicionar(self, funcionario):
        self.funcionarios.append(funcionario)

    def remover(self, funcionario):
        self.funcionarios.remove(funcionario)

    def listar(self):
        print(f"Departamento {self.nome}: {self.funcionarios}")


f1 = Funcionario("Bruno", "Dev")
dev = Departamento("Desenvolvimento")
suporte = Departamento("Suporte")

dev.adicionar(f1)
dev.listar()

dev.remover(f1)      # funcionário continua existindo
suporte.adicionar(f1)
suporte.listar()
```

### Resposta Exercício 4
```python
class ItemPedido:
    def __init__(self, nome, quantidade, preco_unitario):
        self.nome = nome
        self.quantidade = int(quantidade)
        self.preco_unitario = float(preco_unitario)

    def subtotal(self):
        return self.quantidade * self.preco_unitario


class Pedido:
    def __init__(self):
        self.itens = []  # composição: itens são criados/geridos pelo pedido

    def adicionar_item(self, nome, quantidade, preco_unitario):
        item = ItemPedido(nome, quantidade, preco_unitario)
        self.itens.append(item)

    def total(self):
        return sum(i.subtotal() for i in self.itens)

    def resumo(self):
        for i in self.itens:
            print(f"- {i.nome}: {i.quantidade} x R$ {i.preco_unitario:.2f} = R$ {i.subtotal():.2f}")
        print(f"TOTAL: R$ {self.total():.2f}")


pedido = Pedido()
pedido.adicionar_item("Mouse", 2, 50)
pedido.adicionar_item("Teclado", 1, 120)
pedido.resumo()
```

### Resposta Exercício 5
```python
# Associação: relação “usa” sem dependência de vida. Ex.: Professor usa Disciplina
# (prof.ministrar(disciplina)). Nenhum “contém” o outro necessariamente.
#
# Agregação: todo-parte fraca; a parte pode existir fora do todo. Ex.: Departamento
# tem Funcionarios, mas um Funcionario pode sair de um departamento e ir para outro.
#
# Composição: todo-parte forte; a parte depende do todo. Ex.: Pedido cria e mantém
# ItemPedido internamente; ao “sumir” o Pedido, os itens deixam de fazer sentido.
```

</details>

---

**Bons estudos!**
