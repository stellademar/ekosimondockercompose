# Simon dice – Docker Compose

La aplicación implementa el juego clásico **Simon Dice**, distribuido en tres contenedores independientes
- Frontend (nginx,html)
- Apilayer (comunicación con DB)
- DB
---

## Explicación de cada contenedor/servicio

### Frontend
- Servido con **Nginx**.
- Publica la aplicación web estática.
- Expone **únicamente** el puerto `8080` al host.
- Actúa como *reverse proxy* hacia la API.

### API
- Implementada en **Python (Flask + Gunicorn)**
- Contiene la lógica del juego.
- Se comunica únicamente con la base de datos.

### Base de Datos
- **PostgreSQL**.
- Almacena partidas e intentos.
---
 ### Pasos

1. Crear un archivo `.env` con las siguientes variables:

```env
POSTGRES_DB=simon
POSTGRES_USER=simonuser
POSTGRES_PASSWORD=simondbpass
```
2. Levantar
```
docker compose up -d
```
3. Acceder y jugar :D
http://localhost:8080




