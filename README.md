# Stack de Monitoreo con Prometheus, Grafana y cAdvisor

Este proyecto configura un stack de monitoreo utilizando Docker Compose, incluyendo Prometheus, Grafana y cAdvisor para monitorear métricas del sistema y contenedores.

## Requisitos previos

- Docker

- Docker Compose

## Servicios

### Prometheus

Prometheus es un sistema de monitoreo y base de datos de series temporales.

Archivo de Configuración: `./prometheus/prometheus.yml` (montado en `/etc/prometheus/prometheus.yml` dentro del contenedor)

### Grafana

Grafana es una herramienta de visualización y análisis de datos para monitoreo.

- Variables de Entorno:
    - `GF_SECURITY_ADMIN_PASSWORD`: Establece la contraseña de administrador para Grafana (reemplazar `<grafana_password>` con la contraseña deseada).

### cAdvisor

cAdvisor proporciona métricas de uso de recursos y rendimiento de los contenedores.

## Ejecutando el Stack

Para iniciar el stack de monitoreo, ejecutar:
```bash
docker-compose up -d
```
Para detener el stack, usar:

```bash
docker-compose down
```

## Acceso a los Servicios

Prometheus: http://localhost:9090

Grafana: http://localhost:3000 (Ingresar con `admin` y la contraseña definida en `GF_SECURITY_ADMIN_PASSWORD`)

cAdvisor: http://localhost:8080

## Personalización

### Modificar la Configuración de Prometheus

Editar `prometheus.yml` en el directorio `./prometheus` para agregar trabajos de recopilación y configurar objetivos.

## Conclusión

Este setup proporciona un stack de monitoreo básico para aplicaciones en contenedores utilizando Prometheus, Grafana y cAdvisor. Se puede extender agregando reglas de alertas, dashboards y más fuentes de métricas según sea necesario.
