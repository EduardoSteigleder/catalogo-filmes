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

```
catalogo-filmes/
├── backend/
│   ├── app/
│   │   ├── Http/
│   │   │   └── Controllers/
│   │   │       └── Api/
│   │   │           ├── FavoriteController.php
│   │   │           └── TmdbController.php
│   │   ├── Models/
│   │   │   └── Favorite.php
│   ├── database/
│   │   ├── migrations/
│   │   │   └── *_create_favorites_table.php
│   │   └── seeders/
│   ├── routes/
│   │   └── api.php
│   ├── config/
│   ├── public/
│   ├── .env.example
│   └── artisan
│
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   │   ├── http.js
│   │   │   ├── tmdb.js
│   │   │   └── favorites.js
│   │   ├── stores/
│   │   │   └── favorites.js
│   │   ├── views/
│   │   │   ├── SearchView.vue
│   │   │   └── FavoritesView.vue
│   │   ├── router/
│   │   │   └── index.js
│   │   ├── lib/
│   │   │   └── toast.js
│   │   ├── App.vue
│   │   └── main.js
│   ├── index.html
│   ├── vite.config.js
│   └── package.json
│
├── .gitignore
└── README.md

```

---

## Backend (Laravel)

### Requisitos
- PHP 8+
- Composer
- MySQL

### Configuração

Na pasta `backend`, copie o arquivo `.env.example` para `.env` e configure:

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=catalogo_filmes
DB_USERNAME=root
DB_PASSWORD=1234

TMDB_API_KEY=SUA_CHAVE_DO_TMDB
```

### Execução

Na pasta `backend`:

```
composer install
php artisan key:generate
php artisan migrate
php artisan serve
```

API disponível em:

```
http://127.0.0.1:8000
```

---

## API – Documentação

Base URL:

```
http://127.0.0.1:8000/api
```

### 🔎 TMDB

#### Buscar filmes

```
GET /tmdb/search
```

**Query Params**

| Parâmetro | Tipo   | Obrigatório | Descrição     |
|----------|--------|-------------|---------------|
| query    | string | sim         | Nome do filme |

**Exemplo**

```
GET /api/tmdb/search?query=matrix
```

---

### ⭐ Favoritos

#### Listar favoritos

```
GET /favorites
```

#### Filtrar favoritos por gênero

```
GET /favorites?genre={genre_id}
```

#### Adicionar favorito

```
POST /favorites
```

**Body (JSON)**

```json
{
  "tmdb_id": 603,
  "title": "Matrix",
  "genre_ids": [28, 878],
  "poster_path": "/poster.jpg"
}
```

#### Remover favorito

```
DELETE /favorites/{id}
```

**Exemplo**

```
DELETE /api/favorites/3
```

---

## Frontend (Vue)

### Requisitos
- Node.js 18+
- npm

### Execução

Na pasta `frontend`:

```
npm install
npm run dev
```

Aplicação disponível em:

```
http://localhost:5173
```

---

## Funcionalidades

- Busca de filmes na API do TMDB
- Exibição de informações dos filmes
- Adicionar filmes aos favoritos
- Listar favoritos
- Filtrar favoritos por gênero
- Remover filmes dos favoritos
- Identificação visual de filmes já favoritados

---

## Observações

- Projeto desenvolvido como teste técnico
- Backend e frontend desacoplados
- Estrutura simples, clara e organizada
