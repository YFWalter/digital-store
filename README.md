# Digital Store

Tienda de archivos digitales construida con **Laravel 12** y **PHP 8.3**.

> Antes este repositorio se llamaba `manga-store`. Se reinició sobre un esqueleto limpio de Laravel 12 para arrancar el desarrollo de una tienda de productos digitales (descarga de archivos tras la compra).

## Stack

- PHP 8.2+ (desarrollado con 8.3)
- Laravel 12
- SQLite (por defecto en desarrollo; configurable a MySQL/PostgreSQL)
- Vite para assets

## Requisitos

- PHP >= 8.2 con extensiones: `openssl`, `mbstring`, `pdo`, `tokenizer`, `ctype`, `json`, `fileinfo`
- Composer 2
- Node.js + npm (para los assets del front)

## Puesta en marcha

```bash
# Instalar dependencias PHP
composer install

# Copiar variables de entorno y generar la app key
cp .env.example .env
php artisan key:generate

# Crear la base de datos SQLite y migrar
touch database/database.sqlite
php artisan migrate

# Instalar y compilar assets
npm install
npm run dev

# Levantar el servidor de desarrollo
php artisan serve
```

La app queda disponible en `http://localhost:8000`.

## Estado del proyecto

🚧 En desarrollo inicial — esqueleto de Laravel 12 recién creado. Próximos pasos: modelar el dominio de la tienda (productos digitales, categorías, carrito, pedidos y entrega de archivos).
