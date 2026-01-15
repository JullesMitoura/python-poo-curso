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

# Exercícios - Aula 04

## **Aula 04 - Encapsulamento e Modificadores**

### Exercício 1 — Conta com saldo protegido
Crie uma classe `Conta` com:
- atributo “privado” `__saldo`
- `@property saldo` (getter) e `@saldo.setter` com validação (não permitir saldo negativo)
- métodos `depositar(valor)` e `sacar(valor)` com validação (não permitir valor <= 0; não permitir sacar além do saldo)

```python
# Sua resposta aqui
```

### Exercício 2 — Refatorando a conta “pública”
Recrie o exemplo da aula (saldo público) como `ContaPublica` e mostre, via prints, um caso de estado inválido (saldo negativo).

Depois crie `ContaEncapsulada` corrigindo o problema com `__saldo` e `@property`.

```python
# Sua resposta aqui
```

### Exercício 3 — Base de dados com “name mangling”
Crie uma classe `BaseDados` com atributo “privado” `__dados` no formato:

```python
{"users": []}
```

Implemente:
- `add_user(nome, user_id)` (não permitir IDs repetidos)
- `list_users()` (imprimir usuários)
- `delete_user(user_id)` (remover e retornar `True/False`)

```python
# Sua resposta aqui
```

### Exercício 4 — `@property` somente leitura
Na classe `BaseDados`, crie um `@property total_users` (somente leitura) que retorna a quantidade de usuários cadastrados.

```python
# Sua resposta aqui
```

### Exercício 5 (Desafio) — Atributo “protegido” por convenção
Crie uma classe `Usuario` com:
- atributo `_senha` (uso interno por convenção)
- `@property senha` que ao ler retorna `"***"` (não exponha a senha real)
- método `alterar_senha(nova)` que valida tamanho mínimo (ex.: 8) e atualiza `_senha`

```python
# Sua resposta aqui
```

---

## **Respostas**

<details>
<summary>Clique para ver as respostas</summary>

### Resposta Exercício 1
```python
class Conta:
    def __init__(self, saldo=0.0):
        self.__saldo = 0.0
        self.saldo = saldo  # usa o setter (validação)

    @property
    def saldo(self):
        return self.__saldo

    @saldo.setter
    def saldo(self, valor):
        valor = float(valor)
        if valor < 0:
            raise ValueError("saldo não pode ser negativo")
        self.__saldo = valor

    def depositar(self, valor):
        valor = float(valor)
        if valor <= 0:
            raise ValueError("valor de depósito deve ser positivo")
        self.__saldo += valor

    def sacar(self, valor):
        valor = float(valor)
        if valor <= 0:
            raise ValueError("valor de saque deve ser positivo")
        if valor > self.__saldo:
            raise ValueError("saldo insuficiente")
        self.__saldo -= valor


conta = Conta(100)
conta.depositar(50)
conta.sacar(30)
print(conta.saldo)
```

### Resposta Exercício 2
```python
class ContaPublica:
    def __init__(self, saldo=0.0):
        self.saldo = float(saldo)  # "público": sem controle


# Exemplo de estado inválido (pode acontecer)
cp = ContaPublica(100)
cp.saldo = -500  # ninguém impede
print("ContaPublica saldo inválido:", cp.saldo)


class ContaEncapsulada:
    def __init__(self, saldo=0.0):
        self.__saldo = 0.0
        self.saldo = saldo  # valida

    @property
    def saldo(self):
        return self.__saldo

    @saldo.setter
    def saldo(self, valor):
        valor = float(valor)
        if valor < 0:
            raise ValueError("saldo não pode ser negativo")
        self.__saldo = valor


ce = ContaEncapsulada(100)
try:
    ce.saldo = -500
except ValueError as e:
    print("ContaEncapsulada bloqueou estado inválido:", e)
```

### Resposta Exercício 3
```python
class BaseDados:
    def __init__(self):
        self.__dados = {"users": []}

    def add_user(self, nome, user_id):
        if any(u["id"] == user_id for u in self.__dados["users"]):
            raise ValueError("ID já cadastrado")
        self.__dados["users"].append({"nome": nome, "id": user_id})

    def list_users(self):
        for u in self.__dados["users"]:
            print(f'{u["id"]}: {u["nome"]}')

    def delete_user(self, user_id):
        for i, u in enumerate(self.__dados["users"]):
            if u["id"] == user_id:
                del self.__dados["users"][i]
                return True
        return False


bd = BaseDados()
bd.add_user("Ana", 1)
bd.add_user("Bruno", 2)
bd.list_users()
print("Removeu 2?", bd.delete_user(2))
bd.list_users()
```

### Resposta Exercício 4
```python
class BaseDados:
    def __init__(self):
        self.__dados = {"users": []}

    def add_user(self, nome, user_id):
        if any(u["id"] == user_id for u in self.__dados["users"]):
            raise ValueError("ID já cadastrado")
        self.__dados["users"].append({"nome": nome, "id": user_id})

    def list_users(self):
        for u in self.__dados["users"]:
            print(f'{u["id"]}: {u["nome"]}')

    def delete_user(self, user_id):
        for i, u in enumerate(self.__dados["users"]):
            if u["id"] == user_id:
                del self.__dados["users"][i]
                return True
        return False

    @property
    def total_users(self):
        return len(self.__dados["users"])


bd = BaseDados()
bd.add_user("Ana", 1)
bd.add_user("Bruno", 2)
print("Total:", bd.total_users)
```

### Resposta Exercício 5
```python
class Usuario:
    def __init__(self, senha_inicial):
        self._senha = None
        self.alterar_senha(senha_inicial)

    @property
    def senha(self):
        # nunca expõe a senha real
        return "***"

    def alterar_senha(self, nova):
        if not isinstance(nova, str):
            raise TypeError("senha deve ser string")
        if len(nova) < 8:
            raise ValueError("senha deve ter no mínimo 8 caracteres")
        self._senha = nova


u = Usuario("senhaSuperSegura")
print("Senha visível:", u.senha)
u.alterar_senha("novaSenha123")
print("Senha visível:", u.senha)
```

</details>

---

**Bons estudos!**
