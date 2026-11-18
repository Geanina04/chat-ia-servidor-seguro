# Chat con IA propia en servidor seguro

## 1. Descripción del proyecto

Aplicación web de chat con inteligencia artificial local, desarrollada con Flask e integrada con Ollama. Permite a los usuarios registrarse, iniciar sesión y realizar consultas al modelo de lenguaje.

## 2. Tecnologías utilizadas

- Ubuntu Server 24.04 LTS
- Python
- Flask
- Gunicorn
- SQLite
- Ollama
- Modelo llama3.2:3b
- Argon2 para el hash de contraseñas
- Flask-WTF para protección CSRF
- Flask-Limiter para limitar solicitudes

## 3. Funcionalidades

- Registro e inicio de sesión.
- Contraseñas protegidas mediante hashes Argon2.
- Roles de usuario y administrador.
- Chat con inteligencia artificial local.
- Historial de conversaciones.
- Panel de administración.
- Protección CSRF.
- Limitación de intentos de inicio de sesión.
- Configuración de cookies de sesión.

## 4. Arquitectura

El sistema utiliza los siguientes componentes:

- Flask: aplicación web.
- Gunicorn: servidor WSGI.
- Ollama: servicio local de inteligencia artificial.
- SQLite: almacenamiento de usuarios y conversaciones.
- systemd: administración de servicios.

## 5. Puertos utilizados

| Servicio | Puerto | Dirección |
|---|---|---|
| Aplicación web | 8000 | 0.0.0.0 |
| Ollama | 11434 | 127.0.0.1 |
| SSH | 22 | Servidor Ubuntu |

## 6. Estructura del proyecto

- `app.py`: código principal.
- `templates/`: páginas HTML.
- `requirements.txt`: dependencias de Python.
- `.gitignore`: archivos excluidos.
- `README.md`: documentación.

## 7. Instalación

Crear el entorno virtual:

```bash
python3 -m venv venv
Activar el entorno virtual:

```bash
source venv/bin/activate
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

## 8. Configuración

La clave secreta se almacena en:

`/srv/ia/app/.secret_key`

La base de datos se encuentra en:

`/srv/ia/db/chat.db`

El modelo configurado es `llama3.2:3b`.

Estos archivos privados no deben publicarse en GitHub.

## 9. Administración de servicios

Consultar el estado de la aplicación:

```bash
sudo systemctl status chatia
```

Consultar el estado de Ollama:

```bash
sudo systemctl status ollama
```

## 10. Integrantes

- Geanina Acosta Perez
- David Sancho Marin

## 11. Estado del proyecto

Este repositorio contiene el código fuente y las dependencias principales de la aplicación. La documentación final debe complementarse con las pruebas de seguridad y los componentes de infraestructura verificados durante la entrega.
