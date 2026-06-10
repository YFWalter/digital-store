# Digital Store — Contexto del proyecto

> Este archivo lo lee Claude Code automáticamente al abrir una sesión en esta carpeta.
> Sirve para retomar el proyecto desde cualquier máquina.

## Qué es

**Digital Store**: tienda de archivos digitales (el cliente compra y descarga archivos).
Construido con **Laravel 12** sobre **PHP 8.3**.

> Historia: el repo antes se llamaba `manga-store` (Laravel 10, solo scaffold sin código propio).
> El 2026-06-10 se reinició sobre un esqueleto limpio de Laravel 12 y se renombró a `digital-store`.
> El `initial commit` original se conserva en el historial.

## Stack

- PHP 8.2+ (desarrollado con 8.3)
- Laravel 12
- SQLite en desarrollo (`database/database.sqlite`); configurable a MySQL/PostgreSQL vía `.env`
- Vite para assets (Node.js + npm)

## Puesta en marcha en una máquina nueva

```bash
git clone https://github.com/YFWalter/digital-store.git
cd digital-store

# Dependencias PHP (requiere PHP >= 8.2 y Composer 2)
composer install

# Entorno
cp .env.example .env
php artisan key:generate

# Base de datos SQLite + migraciones
#   Linux/macOS:  touch database/database.sqlite
#   Windows PS:   New-Item database/database.sqlite -ItemType File
php artisan migrate

# Front
npm install
npm run dev

# Servidor de desarrollo -> http://localhost:8000
php artisan serve
```

`.env` y `database/database.sqlite` están en `.gitignore`: en cada máquina se generan localmente
(el `php artisan key:generate` crea una `APP_KEY` propia por máquina).

## Estado actual

🚧 **Desarrollo inicial.** Es el esqueleto de Laravel 12 recién creado.
Todavía NO hay dominio propio de la tienda:

- Modelos: solo `User` (default de Laravel)
- Migraciones: solo las default (users, cache, jobs)
- Sin controllers, vistas ni rutas propias de la tienda

## Próximos pasos (roadmap)

Modelar el dominio de la tienda de archivos digitales:

1. **Productos digitales** — modelo + migración (nombre, descripción, precio, archivo, portada)
2. **Categorías** — y relación con productos
3. **Carrito** de compra
4. **Pedidos / checkout**
5. **Entrega del archivo** tras la compra (descarga segura con enlaces temporales/firmados)
6. **Autenticación** de clientes (más allá del `User` base)

## Convenciones / notas

- Nombre del paquete composer: `yfwalter/digital-store`
- Rama principal: `master`
- En entornos Windows con varias versiones de PHP, usar **PHP 8.2+** (Laravel 12 no corre en < 8.2).
- Mantené este archivo actualizado a medida que avance el proyecto (decisiones, estado, próximos pasos).
