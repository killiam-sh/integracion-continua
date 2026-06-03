# Integración Continua - Proyecto de Software

Proyecto del módulo Énfasis Profesional I (Integración Continua) - Politécnico Grancolombiano.

**Institución:** Politécnico Grancolombiano  
**Módulo:** Énfasis Profesional I - Integración Continua  
**Grupo:** B04 - Subgrupo: 3  
**Tutor:** Msc. Edwar Reyes Corredor

## Descripción

Aplicación web desarrollada con Flask y MySQL, desplegada mediante contenedores Docker y gestionada con Jenkins como herramienta de integración continua.

## Requisitos

- Docker
- Docker Compose
- Git

## Estructura del proyecto

```
integracion-continua/
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
└── README.md
```

## Instrucciones de uso

### 1. Clonar el repositorio

```bash
git clone https://github.com/killiam-sh/integracion-continua
cd integracion-continua
```

### 2. Levantar los contenedores

```bash
docker compose up -d
```

### 3. Configurar Jenkins

Instalar Docker dentro del contenedor de Jenkins:

```bash
docker exec -u root jenkins bash -c "apt-get update && apt-get install -y docker.io"
docker exec -u root jenkins bash -c "curl -L https://github.com/docker/compose/releases/download/v2.24.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose"
docker restart jenkins
```

### 4. Acceder a Jenkins

Abrir en el navegador: http://localhost:8080

Obtener la contraseña inicial:

```bash
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

### 5. Crear el pipeline

- Seleccionar "New Item"
- Nombre: integracion-continua
- Tipo: Pipeline
- Definition: Pipeline script from SCM
- SCM: Git
- Repository URL: https://github.com/killiam-sh/integracion-continua.git
- Branch: main
- Script Path: Jenkinsfile

### 6. Ejecutar el pipeline

Dar clic en "Build Now". El pipeline verificara que los contenedores estan corriendo y que la conexion entre Flask y MySQL es exitosa.

## Servicios

| Servicio | Puerto | Descripcion |
|----------|--------|-------------|
| Flask    | 5000   | Backend de la aplicacion |
| MySQL    | 3306   | Base de datos |
| Jenkins  | 8080   | Gestor de integracion continua |
