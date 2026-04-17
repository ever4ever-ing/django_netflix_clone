# Netflix Clone

Aplicación web estilo Netflix construida con Django.

Incluye:
- Registro e inicio de sesión con django-allauth.
- Perfiles por usuario.
- Catálogo de películas filtrado por perfil y límite de edad.
- Vista de detalle de película.
- Reproductor con soporte para episodios (según videos asociados).
- Carga de contenido multimedia desde Django Admin.

## Tecnologías

- Python
- Django
- django-allauth
- Pillow
- SQLite (por defecto en desarrollo)

## Requisitos previos

- Python 3.10 o superior
- pip
- Entorno virtual recomendado

## Instalación y ejecución

1. Clonar el repositorio y entrar al proyecto.

2. Crear y activar entorno virtual.

En Windows (PowerShell):

	python -m venv venv
	.\venv\Scripts\Activate.ps1

3. Instalar dependencias.

	pip install -r requirements.txt

4. Aplicar migraciones.

	python manage.py migrate

5. Crear usuario administrador (opcional, recomendado para cargar contenido).

	python manage.py createsuperuser

6. Ejecutar servidor de desarrollo.

	python manage.py runserver

7. Abrir en navegador.

	http://127.0.0.1:8000/

## Panel de administración

URL de admin:

	http://127.0.0.1:8000/admin/

Desde el admin puedes cargar contenido en este orden:
1. Crear objetos Video (archivo de película o episodio).
2. Crear objetos Movie y asociar uno o varios Video.
3. Definir type, age_limit, flyer y description.

## Rutas principales

- /accounts/login/
- /accounts/signup/
- /profile/
- /watch/<profile_id>/
- /movie/detail/<movie_id>/
- /movie/play/<movie_id>/

## Estructura base

- django_netflix/: configuración principal del proyecto.
- core/: app principal (modelos, vistas, urls, admin).
- templates/: plantillas HTML.
- static/: archivos estáticos.
- media/: archivos subidos (se crea en ejecución cuando subes contenido).

## Comandos útiles

Verificar estado del proyecto:

	python manage.py check

Crear nuevas migraciones tras cambios en modelos:

	python manage.py makemigrations
	python manage.py migrate

