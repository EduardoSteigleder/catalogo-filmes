# Catálogo de Filmes – Teste Técnico

Sistema web para pesquisa de filmes utilizando a API pública do TMDB, permitindo buscar títulos, visualizar informações e gerenciar uma lista de filmes favoritos.

A aplicação foi desenvolvida como teste técnico, com separação clara entre backend (API) e frontend.

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

## Estrutura do Projeto

catalogo-filmes/
|-- backend/
|   |-- app/
|   |   `-- Http/
|   |       `-- Controllers/
|   |           `-- Api/
|   |               |-- FavoriteController.php
|   |               `-- TmdbController.php
|   |-- app/Models/Favorite.php
|   |-- database/migrations/2026_01_03_022905_create_favorites_table.php
|   `-- routes/api.php
|-- frontend/
|   `-- src/
|       |-- api/
|       |   |-- http.js
|       |   |-- tmdb.js
|       |   `-- favorites.js
|       |-- stores/
|       |   `-- favorites.js
|       |-- router/
|       |   `-- index.js
|       `-- views/
|           |-- SearchView.vue
|           `-- FavoritesView.vue
`-- README.md


---

## Backend (Laravel)

### Requisitos
- PHP 8+
- Composer
- MySQL

### Configuração

Na pasta `backend`, copie o arquivo `.env.example` para `.env` e configure:

DB_CONNECTION=mysql  
DB_HOST=127.0.0.1  
DB_PORT=3306  
DB_DATABASE=catalogo_filmes  
DB_USERNAME=root  
DB_PASSWORD=1234  

TMDB_API_KEY=SUA_CHAVE_DO_TMDB  

### Execução

Na pasta `backend`:

composer install  
php artisan key:generate  
php artisan migrate  
php artisan serve  

API disponível em:

http://127.0.0.1:8000

### Rotas da API

Buscar filmes (API pública):

GET /api/tmdb/search?query=nome-do-filme  

Listar favoritos:

GET /api/favorites  

Filtrar favoritos por gênero:

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

### Execução

Na pasta `frontend`:

npm install  
npm run dev  

Aplicação disponível em:

http://localhost:5173

### Integração

O frontend consome a API Laravel via `/api`, utilizando proxy configurado no Vite.

---

## Funcionalidades

- Busca de filmes na API do TMDB
- Exibição de informações dos filmes
- Adicionar filmes aos favoritos
- Listar favoritos
- Filtrar favoritos por gênero
- Remover filmes dos favoritos
- Identificação visual de filmes já favoritados
