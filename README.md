# API de Tarefas — Projeto 3

## Descrição

API REST desenvolvida com Django e Django REST Framework para gerenciamento de tarefas pessoais.

O sistema permite cadastrar, listar, editar e excluir tarefas. Cada usuário pode acessar somente suas próprias tarefas, garantindo segurança e privacidade.

## Tecnologias utilizadas

- Python
- Django
- Django REST Framework
- SQLite
- Token Authentication

## Como executar o projeto

1. Clone o repositório.
2. Crie e ative o ambiente virtual:

python -m venv venv

3. Instale as dependências:

pip install -r requirements.txt

4. Execute as migrações:

python manage.py migrate

5. Crie um superusuário:

python manage.py createsuperuser

6. Inicie o servidor:

python manage.py runserver


## Endpoints da API

| Método | Endpoint | Descrição |
|---|---|---|
| POST | /api/login/ | Realizar login e obter token |
| GET | /api/tarefas/ | Listar tarefas |
| POST | /api/tarefas/ | Criar tarefa |
| GET | /api/tarefas/<id>/ | Consultar tarefa |
| PUT | /api/tarefas/<id>/ | Atualizar tarefa |
| PATCH | /api/tarefas/<id>/ | Atualizar parcialmente |
| DELETE | /api/tarefas/<id>/ | Excluir tarefa |

## Filtros

É possível filtrar tarefas por:

- Conclusão: ?concluida=true ou ?concluida=false
- Prioridade: ?prioridade=ALTA, ?prioridade=MEDIA ou ?prioridade=BAIXA

## Autenticação

A API utiliza autenticação por Token.

O token deve ser enviado no cabeçalho:

Authorization: Token SEU_TOKEN

As rotas de tarefas exigem autenticação.

## Segurança

Cada usuário acessa somente suas próprias tarefas.

Tentativas de acessar tarefas pertencentes a outros usuários retornam erro 404.

## Testes automatizados

Para executar os testes:


python manage.py test


Os testes verificam autenticação, criação, listagem, filtros, atualização, exclusão e isolamento entre usuários.

## Autora

Kauanne Letícia da Silva Carvalho

IESB — Construção de Backend — 2026