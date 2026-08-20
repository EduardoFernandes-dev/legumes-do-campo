# Legumes do Campo

Aplicação web completa para gestão de uma horta/produção de legumes: catálogo de
legumes, épocas de plantação e informação prática. Projeto académico com backend
Django e frontend React, com dados de exemplo gerados por script.

## Stack

- Backend: Django (Python) com Django REST Framework, apps `store` e `users`
- Frontend: React (Vite)
- Banco de dados: SQLite (local)

## Como correr

Backend:

    cd backend
    python -m venv .venv
    .venv/Scripts/activate          # Windows
    pip install -r requirements.txt
    python manage.py migrate
    python manage.py shell < seed_data.py     # popula a base com dados de exemplo
    python manage.py runserver                # http://localhost:8000

Frontend:

    cd frontend
    npm install
    npm run dev                     # http://localhost:5173

O CORS já permite o frontend em `:5173` falar com a API em `:8000`. O seed cria
um utilizador `admin`. Para usar o painel de administração do Django, define uma
palavra-passe para esse utilizador em primeiro lugar.

## Estrutura

- `backend/`, configuração Django e apps `legumes_do_campo`, `store`, `users`
- `backend/seed_data.py`, script de dados de exemplo (via `manage.py shell`)
- `frontend/`, aplicação React em Vite
- `requirements.txt`, dependências do backend
- `package.json`, dependências do frontend
