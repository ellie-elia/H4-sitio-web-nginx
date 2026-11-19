# Sitio Web Estático en Nginx

Respaldo del código fuente HTML desplegado dentro de un contenedor Docker (`nginx:alpine`) sobre una máquina virtual Alpine Linux administrada remotamente vía Tailscale.

## Datos 
* **Universidad:** Universidad Franz Tamayo (UNIFRANZ)
* **Asignatura:** Sistemas Operativos — Paralelo 2
* **Docente:** Ing. Diego Cárdenas S.
* **Estudiante:** Elia Solis Escobar

## Estructura del repositorio
* `sitio_web/index.html`: Página principal personalizada servida en el contenedor `mi-servidor-web` (puerto `8080:80`).
* `sitio_web/50x.html`: Página de respuesta por defecto ante errores del servidor Nginx.

## 🐳 Despliegue rápido con Docker
Para ejecutar este sitio en un entorno Docker con Nginx:

```bash
docker run -d --name mi-servidor-web -p 8080:80 nginx:alpine
docker cp sitio_web/. mi-servidor-web:/usr/share/nginx/html/
