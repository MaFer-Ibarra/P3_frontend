# P3 · Desplegar y asegurar la API en la nube

Página web que consume una API REST de productos publicada en Render.
Lista, agrega y elimina productos. La API está protegida con variables de entorno, CORS restringido y token.

> ### Integrantes
> - **Integrante 1:** Ibarra Ibarra Maria Fernanda · 232310080
> - **Integrante 2:** Zavala Anguiano Valeria · 232310080
>
> **Materia:** Programación Web · Grupo 4X7B
> **Práctica:** P3 · Desplegar y asegurar la API en la nube
> **Docente:** Dra. María Guadalupe Flores Luevanos

## Enlaces

| Recurso | URL |
|---|---|
| API en Render | https://p3-api-productos.onrender.com/api/productos |
| Página en GitHub Pages | https://mafer-ibarra.github.io/P3_frontend/ |
| Repositorio de la API | https://github.com/MaFer-Ibarra/P3_api_productos |

> El plan gratuito de Render duerme el servicio cuando no recibe visitas. La primera carga puede tardar cerca de un minuto.

## Medidas de seguridad en la API

- **Variables de entorno:** `API_KEY` y `ORIGEN_PERMITIDO` se guardan fuera del código (`.env` en local, Environment en Render).
- **CORS:** solo las páginas listadas en `ORIGEN_PERMITIDO` pueden usar la API desde el navegador.
- **Token:** las rutas que modifican datos (POST, PUT, DELETE) exigen el header `x-api-key`. Las rutas GET son públicas.

## Rutas de la API

| Método | Ruta | Token | Respuesta correcta |
|---|---|---|---|
| GET | /api/productos | No | 200 |
| GET | /api/productos/:id | No | 200 |
| GET | /api/salud | No | 200 |
| POST | /api/productos | Sí | 201 |
| PUT | /api/productos/:id | Sí | 200 |
| DELETE | /api/productos/:id | Sí | 204 |

Sin token o con token incorrecto, las rutas protegidas responden **401**.
