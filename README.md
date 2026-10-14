# Gestor ADSO

## 1. Nombre y propósito del proyecto

**Nombre del proyecto:** Gestor ADSO

**Propósito:** Preparar y documentar un entorno de desarrollo web utilizando Laravel y MariaDB como parte de las actividades de formación del programa Análisis y Desarrollo de Software (ADSO) del SENA.

Este proyecto permite verificar la instalación de las herramientas necesarias, configurar la conexión a la base de datos, ejecutar las migraciones iniciales y administrar los cambios mediante Git.

## 2. Versiones del entorno

Las versiones identificadas en el entorno de desarrollo son:

- **PHP:** 8.2.12 (versión informada por Composer; pendiente de confirmar directamente con `php -v`).
- **Composer:** 2.10.3.
- **Laravel:** 12.70.0.
- **Git:** 2.55.0.windows.4.
- **Sistema operativo:** Windows, utilizado mediante PowerShell.
- **Servidor de base de datos:** MariaDB, versión pendiente de verificar.

## 3. Requisitos

Para preparar y ejecutar el proyecto se requieren las siguientes herramientas:

- PHP compatible con Laravel y sus dependencias.
- Composer para administrar las dependencias de PHP.
- Laravel para el desarrollo de la aplicación web.
- Git para el control de versiones.
- MariaDB para almacenar la información.
- Extensiones de PHP requeridas por Laravel y sus dependencias.
- Visual Studio Code u otro editor de código.
- Un navegador web para comprobar la ejecución de la aplicación.

## 4. Instalación del proyecto

### 4.1. Ubicación del proyecto

El proyecto se encuentra en la siguiente ruta local:

`C:\Users\melquis\documents\gestor-adso`

Abrir una terminal de PowerShell y acceder a la carpeta:

`cd C:\Users\melquis\documents\gestor-adso`

### 4.2. Instalación de dependencias

Para instalar las dependencias declaradas en el proyecto, ejecutar:

`composer install`

Este comando utiliza Composer para instalar las bibliotecas necesarias definidas en los archivos de configuración del proyecto.

Se recomienda conservar el archivo `composer.lock` en el repositorio para mantener las versiones de dependencias resueltas.

## 5. Configuración del archivo .env

El archivo `.env` contiene la configuración local de la aplicación y los datos necesarios para establecer la conexión con la base de datos.

Si el archivo no existe, se puede crear a partir del archivo de ejemplo:

`Copy-Item .env.example .env`

Las variables principales que se deben configurar son:

- `APP_NAME`
- `APP_ENV`
- `APP_KEY`
- `APP_DEBUG`
- `APP_URL`
- `DB_CONNECTION`
- `DB_HOST`
- `DB_PORT`
- `DB_DATABASE`
- `DB_USERNAME`
- `DB_PASSWORD`

Los valores deben ajustarse a la configuración real del entorno local.

Si es necesario generar la clave de la aplicación, ejecutar:

`php artisan key:generate`

**Seguridad:** el archivo `.env` no debe publicarse en Git porque puede contener contraseñas, claves y otros datos sensibles. Se debe conservar excluido del repositorio.

## 6. Creación y configuración de la base de datos

Para preparar la base de datos:

1. Iniciar el servicio de MariaDB.
2. Abrir phpMyAdmin o la herramienta de administración disponible.
3. Crear una base de datos con el nombre `gestor_adso`.
4. Configurar las variables de conexión en el archivo `.env`.

En una instalación local, el host puede ser `127.0.0.1` y el puerto habitual `3306`, siempre que coincidan con la configuración real de MariaDB.

La conexión se configura mediante el controlador MySQL compatible con MariaDB:

`DB_CONNECTION=mysql`

El usuario, la contraseña, el host y el puerto deben corresponder a los configurados en el servidor local.

## 7. Limpieza de configuración y migraciones

Antes de ejecutar las migraciones, se recomienda limpiar la configuración almacenada en caché:

`php artisan config:clear`

Después, ejecutar:

`php artisan migrate`

Las migraciones permiten crear las tablas definidas por Laravel y por las migraciones incluidas en el proyecto.

Para verificar el resultado, revisar los mensajes de la terminal y consultar las tablas existentes en la base de datos `gestor_adso` mediante phpMyAdmin.

## 8. Ejecución del servidor local

Para iniciar el servidor de desarrollo, ubicarse en la carpeta principal del proyecto y ejecutar:

`php artisan serve`

La terminal mostrará la dirección local del servidor, normalmente:

`http://127.0.0.1:8000`

Abrir esa dirección en el navegador para comprobar que la aplicación responde correctamente.

La terminal debe permanecer abierta mientras se utiliza el servidor de desarrollo.

## 9. Control de versiones con Git

El proyecto utiliza Git para registrar los cambios realizados durante el desarrollo.

Los comandos principales son:

Consultar la versión instalada:

`git --version`

Consultar el estado de los archivos:

`git status`

Agregar los archivos preparados para el seguimiento:

`git add .`

Crear un commit descriptivo:

`git commit -m "Inicializar proyecto Gestor ADSO con Laravel"`

Consultar el último commit:

`git log -1 --oneline`

Antes de agregar archivos, se debe verificar que `.env` esté excluido del repositorio para evitar publicar información sensible.

## 10. Evidencias principales de la Semana 1

La bitácora individual debe incluir las siguientes evidencias del proceso:

1. Verificación de las versiones de PHP, Composer, Laravel y Git.
2. Consulta de las extensiones habilitadas de PHP.
3. Creación del proyecto y verificación de Laravel.
4. Ejecución del servidor local mediante `php artisan serve`.
5. Visualización de la página inicial de Laravel en el navegador.
6. Creación de la base de datos `gestor_adso`.
7. Configuración del archivo `.env` sin exponer contraseñas ni secretos.
8. Ejecución de las migraciones iniciales.
9. Verificación de las tablas creadas en MariaDB.
10. Inicialización del repositorio Git y evidencia del commit.
11. Documentación de las verificaciones técnicas y las dificultades encontradas, si las hubo.

Cada evidencia debe incluir una explicación escrita que indique qué se verificó y cuál fue el resultado obtenido.

## 11. Verificación técnica del entorno

La preparación del entorno contempla la verificación de las herramientas mediante los comandos correspondientes:

- `php -v`: consulta la versión de PHP.
- `composer -V`: consulta la versión de Composer.
- `php artisan --version`: identifica la versión de Laravel utilizada por el proyecto.
- `git --version`: consulta la versión de Git.
- `php -m`: muestra las extensiones habilitadas de PHP.
- `php artisan config:clear`: limpia la configuración almacenada en caché.
- `php artisan migrate`: ejecuta las migraciones pendientes.
- `php artisan serve`: inicia el servidor local de desarrollo.

Los resultados deben contrastarse con las capturas obtenidas durante la actividad para documentar el estado real del entorno.

## 12. Conclusión

La preparación del proyecto Gestor ADSO permite comprender los requisitos básicos para trabajar con Laravel, PHP, Composer, MariaDB y Git.

La configuración del entorno, la ejecución de las migraciones, la comprobación de la aplicación en el navegador y la documentación de las versiones constituyen los pasos fundamentales para establecer una base reproducible de desarrollo.

El archivo README sirve como guía para comprender los requisitos y repetir los procedimientos principales de instalación, configuración y ejecución del proyecto.

