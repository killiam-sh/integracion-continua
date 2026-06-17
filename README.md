## Herramientas de Integración Continua

El proyecto implementa múltiples herramientas de integración continua para automatizar procesos de validación, construcción y despliegue.

### Docker

Docker permite la contenerización de la aplicación Flask y la base de datos MySQL, garantizando portabilidad y consistencia entre diferentes entornos de ejecución.

### Jenkins

Jenkins se utiliza para automatizar la ejecución de pipelines de integración continua.

Funciones principales:

* Clonación automática del repositorio.
* Verificación de contenedores Docker.
* Validación de conectividad entre servicios.
* Reporte de éxito o fallo del pipeline.

### Travis CI

Travis CI realiza validaciones automáticas sobre el código fuente cada vez que se realiza un cambio en el repositorio.

Funciones principales:

* Verificación de sintaxis Python.
* Validación de dependencias.
* Comprobación de la configuración Docker Compose.

Archivo de configuración:

```text
.travis.yml
```

### Codeship

Codeship complementa el proceso de integración continua ejecutando pruebas automáticas sobre la aplicación contenerizada.

Funciones principales:

* Construcción de imágenes Docker.
* Verificación de servicios.
* Ejecución de pruebas automáticas.

Archivos de configuración:

```text
codeship-services.yml
codeship-steps.yml
```

## Historial de Cambios

| Fecha    | Actividad                         |
| -------- | --------------------------------- |
| Semana 1 | Creación del repositorio GitHub   |
| Semana 2 | Desarrollo de la aplicación Flask |
| Semana 2 | Configuración de MySQL            |
| Semana 3 | Implementación de Docker          |
| Semana 3 | Configuración de Docker Compose   |
| Semana 4 | Integración con Jenkins           |
| Semana 4 | Integración con Travis CI         |
| Semana 4 | Integración con Codeship          |

## Problemas Encontrados y Soluciones

| Problema                               | Solución                                                         |
| -------------------------------------- | ---------------------------------------------------------------- |
| Error en Docker Compose                | Corrección de la estructura YAML                                 |
| Archivo requirements.txt no encontrado | Corrección del nombre y ubicación del archivo                    |
| Git no reconocido por PowerShell       | Instalación y configuración de Git                               |
| Error de autenticación GitHub          | Configuración de credenciales y autenticación mediante navegador |

## Responsabilidades del Equipo

| Integrante   | Responsabilidad                      |
| ------------ | ------------------------------------ |
| Integrante 1 | Configuración Docker                 |
| Integrante 2 | Configuración Jenkins                |
| Integrante 3 | Integración Travis CI                |
| Integrante 4 | Integración Codeship y documentación |

## Opiniones

El uso de Docker facilitó la portabilidad de la aplicación y redujo problemas de configuración entre equipos. Jenkins permitió automatizar tareas de validación y verificación de la aplicación. Travis CI y Codeship complementaron el proceso de integración continua mediante la ejecución de pruebas automáticas y validaciones adicionales.

## Conclusiones

La integración de Docker, Jenkins, Travis CI y Codeship permitió automatizar procesos de validación y despliegue, facilitando la detección temprana de errores y garantizando un entorno consistente para todos los integrantes del equipo. La contenerización mediante Docker simplificó la distribución de la aplicación, mientras que las herramientas de integración continua mejoraron la calidad y mantenibilidad del proyecto.

