# 📖Evaluación 2 DevOps
En esta evaluación busca automatizar un proyecto utilizando un pipelice **CI/CD** implementado en GitHub Actions. El objetivo es incorporar pruebas automatizadas, análisis de seguridad, uso de contenedores, despliegue automatizado y orquestación.

## 📋Componentes necesarios
Los componentes necesarios para la correcta ejecución de este repositorio son:
- **Docker y Docker Compose**🐋
- **Git**🌿

## ⚙️¿Que hace cada pipeline?
- **`Dockerfile`**: Define la construcción de la imagen del proyecto.
- **`docker-compose.yml`**: Orquesta la arquitectura completa, enlazando el contenedor de la app con la base de datos MySQL, asegurando persistencia de datos (`volumes`) y un arranque resiliente mediante controles de salud (`healthcheck`).
- **`ci-cd.yml`**: **Pipeline principal de GitHub Actions** que automatiza todo el ciclo de vida ante cada cambio en la rama `main`.
- **`dependabot.yml`**: Configuración de seguridad pasiva que audita semanalmente el archivo `pom.xml` en busca de dependencias obsoletas o vulnerables.

## 💻 Cómo ejecutar el proyecto
Para la correcta ejecución del proyecto de manera local hay que ejecutar este comando en la terminal de su preferencia:
```bash
docker compose up --build
```
## 🎯¿Cómo se garantiza la calidad y trazabilidad?
 * **Trazabilidad:**
   Se asegura gracias a que cada cambio, versión de la base de datos o actualización queda registrado en el historial de Git. Esto permite revisar el pasado y saber exactamente qué modificamos, cuándo y quién lo hizo.
    

* **Calidad**:
  Está resguardada porque el pipeline funciona como un filtro automático: si el código contiene errores, si no pasa las pruebas unitarias o si **dependabot.yml** detecta alguna falla de seguridad, el despliegue se frena de inmediato. El proyecto no avanza si no está correcto.
