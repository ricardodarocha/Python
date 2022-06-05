# Pyhton

Um repositório para estudar Pyhton do começo  
🚧 **Em construção**  

---

Este material começou com meu interesse pessoal em aprender Pyhton     
Aos poucos, está se tornando um guia para outras pessoas que querem aprender Pyhton

# Prefácio

Se você não tem conhecimento de qualquer linguagem de programação, não se preocupe. Eu recomendo que Python seja sua primeira linguagem de progamação. Sem dúvidas este é um ótimo começo. Você pode por exemplo acompanhar meus exercícios no Jupyter Notebook 

# Intro

Você pode facilmente aprender **Python** na internet, lendo [livros de Python](https://blog.geekhunter.com.br/10-livros-de-python-que-todo-dev-especialista-deve-ler/) , ou acessando a [Documentação](https://docs.python.org/3/)  
Se você possui domínio básico de inglês, Eu recomendo fortemente que você siga este [blog de Python](https://realpython.com/)


# Ambientes

Para exercitar você precisa configurar um ambiente, seja na internet ou no seu computador  
Eu vou ensinar duas formas de configura ambientes, uma através do Jupyter Notebooks, que é mais recomendável para quem está aprendendo Python ou para quem tem interesse em utilizar Python para fins científicos. Ambos estes ambinetes funcionam tanto na nuvem quanto na sua máquina local
[Diversas formas de configurar um ambiente Python]()

# Olá Mundo

A forma mais comum de aprender uma linguagem é começar pelo exemplo _Olá mundo_  


```Python
MESSAGE = "Olá, mundo!"
print(MESSAGE, '\nAcabo de testar meu primeiro programa");
}
```

# Estrutura de um código Python

O Python foi desenhado para ser Limpo.  
Simplicaidade é sempre o objetivo no Python, por isso é necessário respeitar algumas regras para que as coisas funcionem:  

## Indentação

Indentação importa!  
Indentação é o número de espaços que você coloca à esquerda de uma linha de código python  
No Python, a indentação tem dois propósitos:
  Facilitar a leitura por humanos (Formatação)
  Preparar a leitura por computadores (Instrução)

Vamos ver como é em outras linguagens

```Python
# Um exemplo em python
x = 31 % 2
if x == 0:
    print(x,'é par')
else
    print(x,'é ímpar')
```

```C++
// Um exemplo em C++
int d = 31 % 2;
if d == 0 {
  printf("%d é par d", );
} esle {
  printf("%d é par ímpar", );
} 

```
Observe C++ possui `;` ponto e vígula no final de cada linha
Mas no Python isto não é necessário, pois cada linha é uma instrução
Outra diferença sutil, mas muito importante é o símbolo de chaves `{}`  
Em C++ as chaves `{}` indicam o início e o fim de uma instrução. No python isto não é censsário.
Por quê? Devido à indentação. Em Python, sempre que um bloco de código estiver indentando isto irá representar que ele está em uma hierarquia inferior, ou seja, ele pertence ao bloco anterior sem indentação;

```Python
if x == 0:
    print(x,'é par')
```

No código acima apenas será impresso `"31 é par"` se a instrução `if x == 0:` anterior for verdadeira.

Outro símbolo importante são os dois pontos `:`. Este símbolo formaliza que em seguida irá iniciar o bloco 
# Aprendendo de A a Z

🚧 Nesta seção eu organizo os conteúdos por ordem alfabética. Se preferir uma sequência de estudos acompanhe o tutorial a seguir.

# Continuando o tutorial

A sequência de estudo que eu tenho aprimorado para você que está começando do zero é a seguinte. E eu vou tentar explicar a razão disso:

## Ler um arquivo de configurações .env

É comum controlarmos algumas configurações pelo próprio cargo.toml. Como eu expliquei no exemplo hello world, a versão, o autor e outras informações do binário podem ser declaradas explicitamente no arquivo cargo.toml.
Mas é interessante deixar outras informações em um arquivo .env, que você pode ler facilmente com o tutorial a seguir

```Shell
pip install python-dotenv
```

```Python
"""
DOC STRINGS
"""
from dotenv import load_dotenv
config = load_dotenv(".env")
println!("KEY", config["user_name"]);
config["password"] = "unbush84likely8Fdetail42"
```

## Ler os parâmetros da aplicação com args()

Ao executar uma aplicação pela linha de comandos, você pode passar parâmetros para ela
```Shell
c:\App> python myapp.py ricardo
```

Você pode facilmente acessar estes parâmetros através do comando `args()`

```Python
import sys
args = sys.argv
name = args[0]
if name:
    println!("Olá ", name)
else
    println!("Olá mundo!")
```

## Salvar um arquivo localmente

Ao interagir com o seu programa o usuário o alimenta com dados. Muitas vezes é conveniente armazenar estes dados para serem recuperados no futuro, mesmo quando o programa é fechado e após abrí-lo novamente, o usuário pode precisar reutilizar estes dados ou compartilhá-los com outros dispositivos por exemplo. Neste exemplo eu mostro como salvar dados localmente ou em rede.

Vamos continuar nosso exemplo e prepará-lo para exportar a mensagem em um arquivo

```Python
import sys
args = sys.argv
name = args[0]

### Parabéns, você aprendeu a formatar strings
mensagem = f"Olá {name}!"

### E agora vamos salvar nossa mensagem em um arquivo externo
with open('mensagem.txt', 'w') as file:
    file.write(mensagem)
```

## Ler arquivos 

Da mesma forma é necessário ler os dados gravados, ou então em alguns casos você vai querer ler arquivos que foram gerados por outros dispositivos e importá-los no seu sistema.

Há duas formas principais de ler estes arquivos, que eu divido em 

  [Ler um arquivo simples]() A maneir mais prática mas nem sempre resolve.  
  [Ler um arquivo grande no formato de stream]() Esta maneira poderoso permite gerenciar o uso de memória e ler arquivos gigantes. 
  
Veja este exemplo básico

```Python
with open('mensagem.txt', 'w') as file:
    conteudo = file.readlines()
    for linha in conteudo:
        print(linha)
```

## Refatorando em métodos

Em qualquer linguagem de programação é uma boa prática manter o código limpo, e nunca criar funções muito grandes que tenham várias responsabilidades. Isto pode tornar o código confuso. Por isso nós vamos começar a refatorar o nosso código para quebrá-lo em vários métodos.

```Python
import sys

def salvar_no_arquivo(mensagem):
    with open('mensagem.txt', 'w') as file:
        file.write(mensagem)

args = sys.argv
name = args[0]

mensagem = f"Olá {name}!"
salvar_no_arquivo(mensagem)
```

## Utilizando Linguagem Ubíqua

Em primeiro lugar, lendo o código acima, vemos que não é adequado manter blocos de código que estejam em níveis diferentes dentro da hierarquia de procedimentos, isto é, o código precisa fazer sentido como um todo par aquem lê. Isto nos faz um convite relacionado ao idioma, e de agora em diante vamos fazer um esforço para escrever todo o código em português. Por isso vamos encapsular todo o comportamento de setup do programa no método chamado `carregar_parametros`, isto nos permitirá no futuro utilizar um padrão de projetos (_design pattern_) muito interessante chamado **Builder**, que utiliza o conceito de _Fluent Api_. Mas não por enquanto.

```Python

import sys

def pegar_nome_usuario:
    args = sys.argv
    name = args[0]
    return name


def salvar_no_arquivo(mensagem):
    with open('mensagem.txt', 'w') as file:
        file.write(mensagem)

name = pegar_nome_usuario
salvar_no_arquivo(f"Olá {name}!")
```
A linguagem ubíqua é um conceito do DDD que prega ao desenvolvedor utilizar aspectos da língua falada ao escrever seu código, isto é, deve-se utilizar um formato de narrativa que se aproxime da língua dos usuários finais, utilizando inclusive as mesmas palavras que ele utiliza para descrever aquela rotina. Veja que ao utilizar esta técnica o código fica mais fluido, e mais simples de ler, um dos preceitos do código limpo.

## Outras lições da linguagem com este exemplo básico.

Em Python você pode utilizar **return** sempre que quiser realizar um retorno de um ou mais valores dentro de uma função **def**

```Python
def pegar_nome_usuario:
    args = sys.argv
    name = args[0]
    return name
}
```

## Criar aplicativos de Console ou de Linha de Comando CLI

Se você acompanhou o primeiro tutorial já é capaz de compreender que você pode executar um script python passando na frente do nome do arquivo alguns parâmetros

Eu estou desenvolvendo um tutorial mais completo sobre CLI no repo [cli with Python](?)🚧   
No entanto aqui eu vou dar uma breve introdução:

## Criando uma aplicação simples de linha de comando (CLI) 

Neste exemplo nós vamos importar a biblioteca argparse para criar uma aplicação simples de linha de comando

```Shell
pip install argparse
```

Um aplicativo binário compilado pelo Python pode ser facilmente integrado à Interface de Linha de comando de qualquer terminal, seja Linux, Windows ou Plataformas Embarcadas. Você pode chamar `curl aplicativo.exe` e ele será executado. Mas vamos ver o que podemos fazer para torná-lo mais interativo.

A primeira coisa é trabalhar com argumentos, ou parâmetros, como vimos no tutorial anterior.
Outra forma é coletar inputs do usuário, enquanto o programa está em execução.

```
# Import the argparse library
import argparse

import os
import sys

my_parser = argparse.ArgumentParser(name='name of user')

my_parser.add_argument('Path',
                       metavar='path',
                       type=str,
                       help='the path to list')

# Execute the parse_args() method
args = my_parser.parse_args()

input_path = args.Path

if not os.path.isdir(input_path):
    print('The path specified does not exist')
    sys.exit()

print('\n'.join(os.listdir(input_path)))
```
Aprenda o estado da arte com [ARGPARSE](https://realpython.com/command-line-interfaces-python-argparse/)

## Criando interfaces mais amigáveis e melhores

🚧 Se você quer começar logo veja meu tutorial de [Interfaces Amigáveis com Python]()

Aqui nós experimentamos algums recursos básicos de interface. Mesmo utilizando CLI é possível criar boas interfaces. Em seguida avanço um pouco mais criando interfaces "bonitas" com TUI que são interfaces visuais usando ASCII (exclusivo para terminais e aplicações de linhas de comando).

Se pretende criar interfaces mais avançadas como UI do Sistema operacional como Janelas do Windows, componentes Nativos eu também tenho este estudo. [Interfaces Nativas com Python]()

Também estou desenvolvendo este material sobre o Estado da Arte das Interfaces com Python e componentes Web com [Interfaces com Python - Estado da Arte]()

Se você tem interesse por games dê uma olhada nestes [Experimentos com Python - Games]()

# Coletâneas

Nesta série de coletâneas eu vou exibir exemplos mais práticos possíveis. Por conta disso, eu vou poupar entrar em detalhes.

## Envir um e-mail 

```Python
mport smtplib, ssl

port = 465  # For SSL
smtp_server = "smtp.gmail.com"
sender_email = "my@gmail.com"  # Enter your address
receiver_email = "your@gmail.com"  # Enter receiver address
password = input("Type your password and press enter: ")
message = """\
Subject: Hi there

This message is sent from Python."""

context = ssl.create_default_context()
with smtplib.SMTP_SSL(smtp_server, port, context=context) as server:
    server.login(sender_email, password)
    server.sendmail(sender_email, receiver_email, message
```

## Lendo arquivos CSV 

Consulte o tutorial completo do blog [dicasdepython](https://Python-lang-nursery.github.io/Python-cookbook/encoding/csv.html)
```Python
import csv
with open('arquivo.csv', 'rb') as csvfile:
     linhas = csv.reader(csvfile, delimiter=',', quotechar='"')
     for linha in linhas:
         for coluna in linha:
             print(coluna, '|')
         print('\n')
```

## Lendo JSON 

Vamos fazer um programa para ler o seguinte json
```Json
[
  {
    "nome": "José",
    "idade": 25
  },
  {
    "nome": "Maria",
    "idade": 19
  }
]
```

```Python
import json

with open("dados.json", encoding='utf-8') as meu_json:
    dados = json.load(meu_json)

for pessoa in dados:
    print(f"nome: {pessoa.nome} idade: {pessoa.idade}")

```


## Trabalhando com Bancos de dados

Consulte também [psycopg2]([https://docs.rs/postgres/0.15.2/postgres/](https://pypi.org/project/psycopg2/))
Consulte também [PySQLite]([https://docs.rs/sqlite/latest/sqlite/](https://pypi.org/project/pysqlite/))
```Python
import sqlite3

conn = sqlite3.connect('clientes.db')
cursor = conn.cursor()

cursor.execute("""
INSERT INTO clientes (nome, idade, cpf, email, fone, cidade, uf, criado_em)
VALUES ('Aloisio', 87, '11111111111', 'aloisio@email.com', '98765-4322', 'Porto Alegre', 'RS', '2014-06-09')
""")

cursor.execute("""
SELECT * FROM clientes;
""")

for linha in cursor.fetchall():
    print(linha)
    
# alterando os dados da tabela
cursor.execute("""
UPDATE clientes
SET fone = ?, criado_em = ?
WHERE id = ?
""", (novo_fone, novo_criado_em, id_cliente))

conn.commit()

conn.close()
```

### Fazendo Backup

```import sqlite3
import io

conn = sqlite3.connect('clientes.db')

with io.open('clientes_dump.sql', 'w') as f:
    for linha in conn.iterdump():
        f.write('%s\n' % linha)

print('Backup realizado com sucesso.')
print('Salvo como clientes_dump.sql')

conn.close()
```

Nesta seção eu dedico uma parte especial ao SQLite.
Em seguida eu recomendo você experimentar um banco de dados Profissional que suporta grande volume de dados como Postgresql
[Trabalhando com Banco de Dados]

Neste diretório eu reúno um estudo completo de SQL com Python, incluindo discutindo alguns fundamentos de SQL [SQL completo com Python]

# Log

```Python
import logging
logging.basicConfig(filename='example.log', encoding='utf-8', level=logging.DEBUG)
logging.debug('This message should go to the log file')
logging.info('So should this')
logging.warning('And this, too')
logging.error('And non-ASCII stuff, too, like Øresund and Malmö')
```

veja este [tutorial avançado de log](https://docs.python.org/pt-br/dev/howto/logging.html) (Em inglês)

# Api 

Eu recomendo acompanhar a minha trilha de FastApi com Pythn

# A cool progress bar 

Thats library show us why python is a cool language  
```python
from time import sleep
from tqdm import tqdm

for n in tqdm(range(100)):
  sleep(1)
```

this is the result
```bash

20%| ▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒ 
```

The [complete doc](https://github.com/tqdm/tqdm)

# Sumary by Subject

The examples by subject are in \General Folder

## Variables

You can declare variables just write the name of variable following symbol '=' and the value
```Python
name = 'Ricardo'
email = 'ricardodarocha@outlook.com'
```
## Types

Variable in Python are not typed, that means the compiler infer the type of variable on run time.

```Python
number = 1 #Number is a integer number
number = '1' #Now, number is a string
```

## Modules

```Python
from module import some
```

## Loop expressions

Loop is very fun in python  
Take some examples  

```python
for x in range(10){ // starts with 0, 10 is not inclusive
      if x%2==0
         print!(f"{x} is even")}
      if x==5:
         continue;
      print(f"{x}")
      
      if x==5:
         return x //If is a function, returns x
```

Loops in details [](https://github.com/ricardodarocha/Python/blob/main/general/loopExpressions)

## Error Handling

```Python
while True:
     try:
         x = int(input("Please enter a number: "))
         break
     except ValueError:
         print("Oops!  That was no valid number.  Try again...")
     except:
     # If not ValueError, then is a not mapped error kind, I mean an unknown error
         print("Oops!  Unknown Error")
```

Check [erro handling](https://docs.python.org/3/tutorial/errors.html docs

## Writing documentations

Python has full support on docstrings. Docstrings are commets in code you can write to make your code most readable for third consumers and colabs.

All about documentations  
See this Topic [here](https://realpython.com/documenting-python-code/)

## Writing  Tests

Tests are the heart of some software architecture, like TDD  
To write tests you can do something like 

```Python
assert sum([1, 2, 3]) == 6, "Should be 6"
```

Check [testing](https://realpython.com/python-testing/)

That prevines somebody tho change the values of array without checking it's can be changed

# Links

**Realç Python** [testing](https://realpython.com/
