## ☁️ Infraestructura Cloud y Computación (GCP)

Para garantizar un entorno de ejecución robusto, escalable y desacoplado, se ha diseñado una arquitectura basada en **Google Compute Engine (GCE)**. En lugar de ejecutar procesos monolíticos, se ha optado por separar las cargas de trabajo de generación de datos en instancias dedicadas, siguiendo el principio de responsabilidad única.

### 1. Instancias de Computación (Virtual Machines)

Se han desplegado instancias separadas para simular los diferentes sistemas transaccionales del negocio. Esta separación evita que un fallo en el sistema de pedidos (`orders-app`) afecte al sistema de logística (`delivery-app`), permitiendo además escalar cada uno de forma independiente según la carga.

Como se observa en la consola de GCP, las instancias se encuentran operativas en la zona `europe-west1-b`, garantizando baja latencia con el resto de servicios (Cloud SQL y BigQuery) ubicados en la misma región.

> **Evidencia de Despliegue:**
>
> *Vista de las instancias activas en Compute Engine. Se observa `orders-app` y `delivery-app` funcionando en paralelo con IPs internas y externas asignadas.*
>
> ![Instancias de VM en GCP](imagenes/instancias-VM.png)

### 2. Estrategia de "Golden Image" (Machine Images)

Para optimizar el despliegue y garantizar la consistencia del entorno (Immutable Infrastructure), no se configuró cada servidor manualmente. En su lugar, se creó una **Imagen de Máquina** maestra (`imagen-maquina`).

Esta imagen actúa como una "snapshot" que contiene:
* El Sistema Operativo base configurado.
* Las dependencias de Python instaladas.
* Las credenciales y configuraciones de red necesarias.

Gracias a esto, las instancias `orders-app` y `delivery-app` se instanciaron a partir de esta imagen base, reduciendo el tiempo de aprovisionamiento y eliminando el riesgo de "configuration drift" (diferencias de configuración entre entornos).

> **Evidencia de Imagen de Máquina:**
>
> *Detalle de la imagen creada a partir de la instancia origen, utilizada como plantilla para el resto de la infraestructura.*
>
> ![Imagen de Máquina en GCP](imagenes/imagen-maquina.png)