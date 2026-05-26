# auditoria-pipeline
Repositorio curso DSS (desarrollo software seguro)

# 🛡️ BookStore Pipeline Audit: AI-First Security & CI/CD Gates

[![Security Architecture](https://img.shields.io/badge/Security-AI--First-2e6f40?style=for-the-badge&logo=google-cloud)](https://github.com)
[![CI/CD Pipeline](https://img.shields.io/badge/CI/CD-Actions_&_K8s-1b365d?style=for-the-badge&logo=github-actions)](https://github.com)
[![Course Audit](https://img.shields.io/badge/Clase_6-Pipeline_Seguro-red?style=for-the-badge)](https://github.com)

Informe técnico de auditoría y propuesta de remediación estratégica para la arquitectura de despliegue de **BookStore**: una tienda de libros en línea potenciada por un asistente de IA con arquitectura RAG *(Retrieval-Augmented Generation)*.

* **Caso de Estudio:** BookStore App
* **Curso:** Clase 6 · Pipeline AI-First Seguro (19 de mayo de 2026)
* **Realizado por:** Viviana Poblete L.

---

## 📈 El Escenario Actual (The Big Picture)

El siguiente flujo ilustra el camino que recorre un cambio de código desde que es escrito por el equipo de desarrollo hasta su puesta en marcha en el entorno productivo:

```text
[ Programador ]             # commit + push a la rama main
       │
       ▼
[ GitHub Actions ]          # Instala dependencias y ejecuta tests unitarios básicos
       │
       ▼
[ Imagen Docker ]           # Construye el contenedor usando la base "node:latest"
       │
       ▼
[ Container Registry ]      # Almacena y distribuye el artefacto con el tag ":latest"
       │
       ▼
[ Producción (K8s) ]        # Despliegue directo en el clúster (3 réplicas en paralelo) ⚠️
