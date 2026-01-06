# Catálogo de Filmes – Teste Técnico

Aplicação full stack para busca de filmes em API pública, com funcionalidade de favoritar, listar, filtrar e remover filmes.

Projeto separado em backend (API) e frontend.

---

## Tecnologias

### Backend
- PHP 8+
- Laravel
- MySQL
- TMDB API

### Frontend
- Vue 3
- Vite
- Pinia
- Axios

---

## Estrutura

catalogo-filmes/
├── backend/
└── frontend/

---

## Backend (Laravel)

### Requisitos
- PHP 8+
- Composer
- MySQL

### Configuração

Na pasta `backend`, copie `.env.example` para `.env` e configure:

DB_CONNECTION=mysql  
DB_HOST=127.0.0.1  
DB_PORT=3306  
DB_DATABASE=catalogo_filmes  
DB_USERNAME=root  
DB_PASSWORD=1234  

TMDB_API_KEY=SUA_CHAVE_AQUI  

### Executar

Na pasta `backend`:

composer install  
php artisan key:generate  
php artisan migrate  
php artisan serve  

API disponível em:

http://127.0.0.1:8000

### Rotas

Buscar filmes (API pública):

GET /api/tmdb/search?query=nome-do-filme

Listar favoritos:

GET /api/favorites

Filtrar por gênero:

GET /api/favorites?genre=ID_DO_GENERO

Adicionar favorito:

POST /api/favorites

Remover favorito:

DELETE /api/favorites/{id}

---

## Frontend (Vue)

### Requisitos
- Node.js 18+
- npm

### Executar

Na pasta `frontend`:

npm install  
npm run dev  

Aplicação disponível em:

http://localhost:5173

### API

O frontend consome a API Laravel via `/api`, usando proxy configurado no Vite.
