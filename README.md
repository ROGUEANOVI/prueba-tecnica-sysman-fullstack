# Prueba Técnica Full-Stack - SYSMAN

Este repositorio contiene la orquestación de una aplicación full-stack desarrollada como parte de la prueba técnica para SYSMAN. La aplicación se compone de un backend en Spring Boot, un frontend en Angular y una base de datos PostgreSQL, todo containerizado con Docker.

## Tecnologías Utilizadas

- **Orquestación:** Docker & Docker Compose
- **Backend:** Java 17, Spring Boot 3, Spring Security, JWT.
- **Frontend:** Angular 16, Angular Material, TypeScript.
- **Base de Datos:** PostgreSQL 15.
- **Flujo de Trabajo:** Git Flow.

---

## Prerrequisitos

Para levantar el entorno de desarrollo, asegúrate de tener instalado lo siguiente:

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/products/docker-desktop/)
- [Docker Compose](https://docs.docker.com/compose/install/) (generalmente incluido con Docker Desktop)

---

## Puesta en Marcha (Setup)

Sigue estos pasos para configurar y ejecutar el proyecto en tu entorno local.

**1. Clonar los Repositorios**

Este proyecto utiliza 3 repositorios. Clónalos en la misma carpeta raíz:

```sh
# 1. Clona el repositorio principal de orquestación
git clone https://github.com/ROGUEANOVI/prueba-tecnica-sysman-fullstack.git

# 2. Accede a la carpeta principal
cd prueba-tecnica-sysman-fullstack

# 3. Clona el repositorio del backend DENTRO de la carpeta principal
git clone https://github.com/ROGUEANOVI/prueba-tecnica-sysman-backend.git

# 4. Clona el repositorio del frontend DENTRO de la carpeta principal
git clone https://github.com/ROGUEANOVI/prueba-tecnica-sysman-frontend.git
```

**2. Configurar las Variables de Entorno**

La aplicación utiliza un archivo `.env` para gestionar las credenciales de la base de datos.

- Crea una copia del archivo `.env.example` y renómbrala a `.env`.
  ```sh
  cp .env.example .env
  ```
- Abre el archivo `.env` y modifica la contraseña `POSTGRES_PASSWORD` si es necesario.

**3. Levantar los Contenedores**

Una vez clonados los repositorios y configurado el archivo `.env`, levanta toda la aplicación con un solo comando:

```sh
docker-compose up --build -d
```

- `--build`: Fuerza la reconstrucción de las imágenes de Docker. Úsalo la primera vez o después de hacer cambios en el código.
- `-d`: Ejecuta los contenedores en segundo plano (detached mode).

La primera vez, este proceso puede tardar varios minutos mientras Docker descarga las imágenes base y construye los proyectos.

---

## Acceso a la Aplicación

Una vez que los contenedores estén en ejecución, puedes acceder a los diferentes servicios:

- **Aplicación Frontend (Angular):**

  - URL: `http://localhost:4200`

- **API Backend (Spring Boot):**

  - URL Base: `http://localhost:8080`
  - **Documentación Swagger UI:** `http://localhost:8080/swagger-ui.html`

- **Base de Datos (PostgreSQL):**
  - **Host:** `localhost`
  - **Puerto:** `5433`
  - **Usuario:** `sysman`
  - **Contraseña:** (la que especificaste en tu archivo `.env`)
  - **Base de datos:** `sysman_db`

## Detener la Aplicación

Para detener todos los servicios, ejecuta:

```sh
docker-compose down
```
