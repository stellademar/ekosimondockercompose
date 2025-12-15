# Simon dice – Docker Compose
<img width="846" height="615" alt="image" src="https://github.com/user-attachments/assets/c9add0ad-ef09-414f-b968-7e25348c09c7" />

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
0. Descarga este repo o copia el contenido de docker-compose.yml

1. Crear un archivo `.env` con las siguientes variables, donde este ubicado tu docker-compose.yml

```env
POSTGRES_DB=simon
POSTGRES_USER=simonuser
POSTGRES_PASSWORD=simondbpass
```
2. Posicionate donde tengas el archivo docker-compose.yml, acordate de generar un archivo .env del paso 1.
```
docker compose up -d --build
```
3. Acceder y jugar :D
http://localhost:8080




