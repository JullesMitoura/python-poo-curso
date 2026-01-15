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

# Exercícios - Aula 01

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

</details>

---

**Bons estudos!**
